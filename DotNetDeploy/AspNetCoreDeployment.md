# ASP.NET Core Deployment

We use `dotnet publish` command to prepare a package or a directory for deployment.

## ZIP Package

Create a publish profile if you need a ZIP package.

Example of `Properties/PublishProfiles/Package.pubxml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
This file is used by the publish/package process of your Web project. You can customize the behavior of this process
by editing this MSBuild file. In order to learn more about this please visit https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <WebPublishMethod>Package</WebPublishMethod>
    <LastUsedBuildConfiguration>Release</LastUsedBuildConfiguration>
    <LastUsedPlatform>Any CPU</LastUsedPlatform>
    <SiteUrlToLaunchAfterPublish />
    <LaunchSiteAfterPublish>True</LaunchSiteAfterPublish>
    <ExcludeApp_Data>False</ExcludeApp_Data>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <ProjectGuid>691e255b-115c-4a38-98b2-6e4b175bae1d</ProjectGuid>
    <SelfContained>false</SelfContained>
    <_IsPortable>true</_IsPortable>
    <DesktopBuildPackageLocation>Example.Web.zip</DesktopBuildPackageLocation>
    <PackageAsSingleFile>true</PackageAsSingleFile>
    <DeployIisAppPath />
    <PublishDatabaseSettings>
      <Objects xmlns="" />
    </PublishDatabaseSettings>
  </PropertyGroup>
</Project>
```

The main property is `WebPublishMethod` with `Package` value.

Create a package:

```powershell
dotnet publish -c Release "C:\example-backend\Example.Web\Example.Web.csproj" /p:PublishProfile=Package
```

Deploy it:

```powershell
Invoke-WebDeployment -PackagePath 'C:\example-backend\Example.Web\Example.Web.zip' -ServerHost 'web.example.com' -SiteName 'example.com' -Application ''
```

## Publish Directory

Create the `publish` directory with a site content:

```powershell
dotnet publish -c Release "C:\example-backend\Example.Web\Example.Web.csproj"
```

Deploy it:

```powershell
Sync-WebContent -ContentPath 'C:\example-backend\Example.Web\bin\Release\netcoreapp2.1\publish' -ServerHost 'web.example.com' -SiteName 'example.com' -Application ''
```
