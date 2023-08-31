# Build stage
FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app

# Copy and restore project dependencies
COPY *.csproj ./
RUN dotnet restore

# Copy and build the application
COPY . ./
RUN dotnet publish -c Release -o /app


FROM mcr.microsoft.com/dotnet/core/sdk:3.1
COPY --from=build /app
WORKDIR /app
ENTRYPOINT ["dotnet", "PDNCOAH_API.dll"]

