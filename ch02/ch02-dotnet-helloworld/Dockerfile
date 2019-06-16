#FROM microsoft/dotnet:1.1-sdk-nanoserver
#找不到1.1，改為2.2，並將範例程式csproj的target改為2.2
FROM mcr.microsoft.com/dotnet/core/sdk:2.2.300-nanoserver-1903

WORKDIR /src
COPY src/ .

# dotnet restore 會出錯
# 從 .NET Core 2.0 SDK 開始，您不需要執行 dotnet restore，因為所有需要進行還原的命令 (例如 dotnet new、dotnet build 和 dotnet run) 都會以隱含方式執行它。
# https://docs.microsoft.com/zh-tw/dotnet/core/tools/dotnet-restore?tabs=netcore2x
#RUN dotnet restore; dotnet build
RUN dotnet build
CMD ["dotnet", "run"]