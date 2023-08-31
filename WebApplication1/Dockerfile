FROM mcr.microsoft.com/dotnet/sdk:3.1.4-alpine AS build
WORKDIR /app
COPY . .
RUN dotnet build

FROM mcr.microsoft.com/dotnet/aspnet:3.1.4-alpine
WORKDIR /app
COPY --from=build /app/bin/Debug/netcoreapp3.1 .
ENTRYPOINT ["dotnet", "run"]
