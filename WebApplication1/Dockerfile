FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app
COPY . .
RUN dotnet build

FROM mcr.microsoft.com/dotnet/aspnet:3.1
WORKDIR /app
COPY --from=build /app/bin/Debug/netcoreapp3.1 .
ENTRYPOINT ["dotnet", "run"]
