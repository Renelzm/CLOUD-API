# Usar el SDK de .NET Core para compilar la aplicación
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /app

# Copiar los archivos del proyecto y restaurar dependencias
RUN dotnet restore

# Copiar y construir la aplicación
RUN dotnet publish -c Release -o out

# Utilizar una imagen de ASP.NET Core 3.1 para ejecutar la aplicación
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app/out .

# Punto de entrada para la aplicación
ENTRYPOINT ["dotnet", "PDNCOAH_API.dll"]
