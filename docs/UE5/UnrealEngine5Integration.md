# Integration

Gravity Layer Unreal Engine 5 Plugin Integration.

---

Once, you download the plugins zip and copy its content to plugins folder, you can continue with enabling plugins in your projects.

!!! info "Integration Info"

    You need to restart your project if it was open during copying the plugin content.

## Enable Plugins

1. Open your project, and use settings button and open plugins menu. 

![](../..\static\img\openPlugins.png)

2. Search for  `Gravity Layer` and select the tick to enable gravity layer plugin. This will automaticly enable dependency plugins as well.
- **glTFRuntime**

- **VaRest**

![](../..\static\img\enableplugin.png)

    3. Click on `Restart`  button to enable Gravity Layer plugin. After restart you are finished with integrating gravity layer plugin into your game. 

### Show Plugin Content

  To view plugin content and sample map, you need to enable **Show Plugin Content ** from `Content Browser > Settings` menu.

![](../..\static\img\ShowPluginContent.png)

### Access Gravity Layer Plugin

To access gravity layer plugin you need to add gravity layer plugin into your public dependencies. 

1. Open your project solution and go to project's [PROJECT_NAME].Build.cs file and add "Gravity Layer" to your public dependency modules.
   
   ```
           PublicDependencyModuleNames.AddRange(new string[]
           {
               ...
               "GravityLayer"
           });`
   ```
   
   After adding Gravity layer as a dependency to your project,  you can include graravity layer subsystem to your project.

---

Now, You can continue with Example Content for Gravity Layer.

  [Example](UnrealEngine5Example.md){ .md-button .md-button--primary }