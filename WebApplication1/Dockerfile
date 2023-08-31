FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app

FROM mcr.microsoft.com/dotnet/aspnet:3.1
COPY . /app
WORKDIR /app
ENTRYPOINT ["dotnet", "PDNCOAH_API.dll"]
