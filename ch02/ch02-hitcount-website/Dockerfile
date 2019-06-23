# escape=`
# FROM microsoft/dotnet:2.2-sdk-nanoserver-1903 AS builder
FROM mcr.microsoft.com/dotnet/core/sdk:2.2.300-nanoserver-1903 AS builder

WORKDIR C:\src
COPY src .

USER ContainerAdministrator
RUN dotnet restore && dotnet publish

# app image
# FROM microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1903
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1903

EXPOSE 80
WORKDIR C:\dotnetapp
RUN mkdir app-state

CMD ["dotnet", "HitCountWebApp.dll"]
COPY --from=builder C:\src\bin\Debug\netcoreapp2.2\publish .