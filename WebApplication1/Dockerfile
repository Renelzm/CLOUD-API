# Utiliza una imagen base que incluye el runtime y el SDK de .NET Core 3.1
FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app


# Copiar los archivos del proyecto y restaurar dependencias
COPY . ./
RUN dotnet publish -c Release -o out

# Etapa final de ejecución
FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app
COPY --from=build /app/out .

# Punto de entrada para la aplicación
ENTRYPOINT ["dotnet", "TuArchivo.dll"]
