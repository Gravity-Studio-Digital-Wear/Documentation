# Example

Gravity Layer Unreal Engine 5 Plugin Example.

---

!!! causion inline end "Project Info"

    To open Gravity Layer example level, you should enable "Show Plugin Content" under Content Drawer > Settings > Show Plugin Content.

## Open Example Level

To how the sample integration process, you can find example level for out plugin under `Plugins \ Gravity Layer Content \ Level` folder. Open level and press play button to see 3 characters. Left most avatar is loaded from fbx file to test the original model. Character on the middle will be added to level after few seconds which will be loaded from Gravity Layer servers. Right most character will be loaded from glb files to test the model. 

![](../..\static\img\examplelevel.png)

A few seconds after the level starts, you will see three characters. 

![](../..\static\img\DifferentCharacters.png)

## Outliner

In the outliner, there are 3 different actors:

- BP_GL_LoadFromFileActor : loads character form glb file.

- BP_GravityLayer : loads character from Gravity layer server.

- BP_Sample_FBX : fbx file to test.

![](../..\static\img\outliner.png)

## Gravity Layer Chracter

You should select avatar skeleton for your characters skeleton system.

![](../..\static\img\SkeletalSelection.png)