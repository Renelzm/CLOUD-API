# Primera etapa: Construir la aplicación
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /app

# Copiar los archivos del proyecto y restaurar dependencias
COPY *.csproj ./
RUN dotnet restore

# Copiar y construir la aplicación
COPY . ./
RUN dotnet publish -c Release -o /app/out

# Segunda etapa: Ejecutar la aplicación en una imagen ASP.NET Core
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app/bin/Release/netcoreapp3.1/ .

# Punto de entrada para la aplicación
ENTRYPOINT ["dotnet", "out/PDNCOAH_API.dll"]
