FROM  mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /src
COPY . ./app/
EXPOSE 5000
EXPOSE 5001


FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src/
COPY . .
RUN dotnet restore
RUN dotnet publish -c release -o /app

FROM base AS final
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "app.dll"]