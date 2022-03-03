FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["DockerDotNet.csproj", ""]
RUN dotnet restore "DockerDotNet.csproj"
COPY . .
WORKDIR "/src/."
RUN dotnet build "DockerDotNet.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "DockerDotNet.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "DockerDotNet.dll"]
