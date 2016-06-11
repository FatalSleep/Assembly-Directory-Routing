# Assembly-Directory-Routing
You can route where the .NET runtime loads external assemblies. This is done by modifying the App.config file.

You can modify the App.config file by adding the following code.
```XAML
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
<!--/////////////////////////////////////////////////////////////////////////-->
  <!--information regarding the .NET runtime. -->
  <runtime>
    <!-- Allows you to specify information about assembly version redirection. -->
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <!-- Specifies folders the .NET runtime should scan(probe) for assemblies. -->
      <!-- This'll load assemblies from: *:\.\MyProgram\Dependencies\ -->
      <probing privatePath="Dependencies;"/>
    </assemblyBinding>
  </runtime>
<!--/////////////////////////////////////////////////////////////////////////-->
  <startup> 
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5.2" />
  </startup>
</configuration>
```
NOTE: VS outputs the app.config as appname.exe.config, copy this with your application or the .NET runtime won't recognize the folders it should search for assemblies.
