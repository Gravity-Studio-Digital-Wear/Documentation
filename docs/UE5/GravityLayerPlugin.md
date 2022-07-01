# Get NFT Process

To download nfts and display on your project:

1) Configure Metaverse SDK

2) Download NFT Inventory 

3) Get NFTs of Account 

4) Gravity Layer API Call

5) Gravity Layer Actor
   
   &emsp; 5.1) Gravity Layer Actor Component
   
   &emsp; 5.2) Gravity Layer File Load Component

---

## Configure Metaverse SDK

To configure metaverse sdk open gravity layer  `GravityLayer::Configure()` function and set sdk configuration parameters of account, api url and secret. 

On Configure function gravity layer plugin, Metaverse entry point is configured to have update events on NFT responses. It will listen stock, wardrobe and wardrobe services update events.

```
GLMetaverseEntryPoint->GetStock()->OnStockUpdated.AddDynamic(this, &UGravityLayer::OnStockUpdate);
GLMetaverseEntryPoint->GetWardrobe()->OnWardrobeUpdated.AddDynamic(this, &UGravityLayer::OnWardrobeUpdate);
GLMetaverseEntryPoint->GetWardrobeServices()->OnWearableMetadataUpdate.AddDynamic(this, &UGravityLayer::OnWearableServiceUpdate);
```

## Download NFT Inventory

To download NFT inventory, `UGravityLayer::GetAllInteroperableWearables()`should be called. This function will send a request to metaverse interface to download inventory with restfull cals. Results will be distributed  through `OnStockUpdated` event. `UGravityLayer::OnStockUpdate` will be called when this update events fired. 

## Get NFTs of Account

To download user NFTs' GetUserInteroperableWearables method should be used. 

```
void UGravityLayer::GetUserInteroperableWearables(const FString& Account)
```

Responses to this function wil be called to `UGravityLayer::OnWardrobeUpdate()` function.

## Gravity Layer API Call

Gravity Layer Module is responsible for starting up the plugin. Entry point of Gravity Layer Plugins is GravityLayer subsystem. To access gravity layer subsystem you should include ` "GravityLayer.h"  `header and call get engine subsystem.

```
// Include gravity layer header to access gravity layer subsystem

\#include "GravityLayer.h"

...

UGravityLayer* GLSubSystem = GEngine->GetEngineSubsystem<UGravityLayer>();
```

## Gravity Layer Actor

Gravity Layer actor is used to download and diplay NFT's on the level.  It has two Components : Skeletal Mesh component and Gravity Layer Component. 

![](../..\static\img\PB_GLActor_.png)

!!! note ""

    Skeletal mesh component  will be overriden by Gravity layer component

Animation component should be selected to animate actor.

![](../..\static\img\SelectAnimationBP.png)

### 

### Gravity Layer Actor Component

Gravity Layer Actor Component is used for displaying nfs on levels as an object. It will get NFT model from Gravity Layer system  with contact address and tokenId and set gravity layer actors skeletal mesh to Gravity Layer Actor's skeletal mesh.



!!! note ""

    Select Avatar skeleton mesh from selection box.


![](../..\static\img\selectavatarskeleton.png)

### Gravity Layer File Load Component

Gravity Layer File Load Component is used to test runtime asset delivery system. It will load glb files from local disk and display on level as an object.

![](../..\static\img\LoadFromFile.png)