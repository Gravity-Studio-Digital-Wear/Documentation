# Get NFT Process

To download nfts and display on your project:

1) Configure Metaverse SDK

2) Download NFT Inventory 

3) Display NFT Items 

4) Gravity Layer API Call

5) Gravity Layer Actor

---

## Configure Metaverse SDK

To configure metaverse sdk open gravity layer `GravityLayer::Configure()` function and set sdk configuration parameters of account, api url and secret. 

On Configure function gravity layer pluging

```

```

## Download NFT Inventory

To Download NFT inventory, `UGravityLayer::GetAllInteroperableWearables()`should be called. This function will send a request to metaverse interface to download inventory with restfull cals. Results will be called to through events. 

## Gravity Layer API Call

Gravity Layer Module is responsible for starting up the plugin. Entry point of Gravity Layer Plugins is GravityLayer subsystem. To access gravity layer subsystem you should include ` "GravityLayer.h"  `header and call get engine subsystem.

```
// Include gravity layer header to access gravity layer subsystem

\#include "GravityLayer.h"

...

UGravityLayer* GLSubSystem = GEngine->GetEngineSubsystem<UGravityLayer>();
```

---

### Getting Started

To enable NFT wearable features, download our lates version of Gravity Layer Unreal Engine 5.0 plugin from our download page. 

  [Download](UnrealEngine5Download.md){ .md-button .md-button--primary }

!!! info "Compatibility Info"

    Gravity Layer plugin is only compatible with Unreal Engine 5.0 and higher.

After downloading plugin, it should be enabled from unreal plugins. 

  [Integration](UnrealEngine5Integration.md){ .md-button .md-button--primary }

After Integration Gravity Layer Plugin, Example project can be run and NFT wearables can be displayed on Unreal Engine 5.0 Level.

  [Example](UnrealEngine5Example.md){ .md-button .md-button--primary }

If you have any questions about the plugin you can check troubleshoot section.

  [Troubleshoot](UnrealEngine5Troubleshoot.md){ .md-button .md-button--primary }

### Dependencies

- glTFRuntime

- VaRest

All dependencies are in Gravity Layer plugin repository. All required plugin files can be found on the zip file.

For further information:

-  **glTFRuntime** plugin, you can find their documentation [here](https://github.com/rdeioris/glTFRuntime-docs/blob/master/README.md).

-  **VaRest** plugin, you can find their documentation [here]([Notion – The all-in-one workspace for your notes, tasks, wikis, and databases.](https://www.notion.so/VaRest-UE4-Plugin-40b98c54fc184033b60a42e0e4753536)).

### Acknowledgments

A big thank you to [Roberto De Ioris](https://www.unrealengine.com/marketplace/en-US/profile/Roberto+De+Ioris) for providing this amazing **glTFRuntime** plugin for free and also providing support to all the users. We encourage anybody using this plugin to consider purchasing [glTFRuntime](https://www.unrealengine.com/marketplace/en-US/product/gltfruntime) from the **Unreal Marketplace** and help support its development.

A big thank you to [Vladimir Alyamkin](https://www.unrealengine.com/marketplace/en-US/profile/Vladimir+Alyamkin) for providing this amazing **[VaRest](https://www.unrealengine.com/marketplace/en-US/product/varest-plugin)** plugin for free and also providing support to all the users. 