FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app
COPY . .
RUN dotnet build

FROM mcr.microsoft.com/dotnet/aspnet:3.1
WORKDIR /app
COPY --from=build /app/out
ENTRYPOINT ["dotnet", "PDNCOAH_API.dll"]
