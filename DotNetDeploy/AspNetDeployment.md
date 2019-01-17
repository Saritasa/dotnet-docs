# ASP.NET Deployment

A traditional ASP.NET application contains MVC controllers, views and static files.

🌐 example.com
- 📁 bin
  - Example.Web.dll
- 📁 Views
    - 📁 Home
        - Index.cshtml
- web.config

To deploy the app, create a Web Deploy package and use PSGallery cmdlets or `msdeploy.exe`.

```powershell
Invoke-WebDeployment -PackagePath 'Example.zip' -ServerHost 'web.example.com' -SiteName 'example.com' -Application ''
```

```bat
msdeploy.exe -source:package='Example.zip' -dest:auto,computerName='https://web.example.com:8172/msdeploy.axd?site=example.com' -verb:sync -setParam:name='IIS Web Application Name',value='example.com/'
```
