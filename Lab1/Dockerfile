FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
WORKDIR /Lab1
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS runtime
WORKDIR /Lab1
COPY --from=build /app .
ENV ASPNETCORE_URLS=http://+:80
ENTRYPOINT [ "dotnet", "Lab1.dll" ]