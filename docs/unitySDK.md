---
name: Unity SDK
route: /unity-sdk
---

# Unity SDK

In order to show wearables in a game (scene) you need to do the next steps.

1. Connect to a user’s Metamask wallet on Polygon chain.

2. Authorize a user in Gravity API.

3. Fetch user’s wearables

4. Equip selected wearable.

Flow scheme:

<img src="/gravity-docs/UnityGravitySDKScheme.png" alt="Flow scheme" />

A single entry point for Gravity SDK is the class `GravityLayerEntryPoint`.

## Connection to Metamask

To connect to a Metamask wallet, call `Web3Connect()` method from `Assets/Plugins/GravityLayer/Example/Scripts/WebLogin.cs`.

After successful logging in the user’s address will be available at `PlayerPrefs.GetString("Account")`.

[Example](https://github.com/Gravity-Studio-Digital-Wear/UnitySDK-WebGL-example/blob/main/Plugins/GravityLayer/Example/Scripts/WebLogin.cs#L21). See `Assets/Plugins/GravityLayer/Example/Scenes/WebLogin.unity`.

## Authorization

The method `EstablishConnection()` from `Assets/Plugins/GravityLayer/CoreAsync/Utils/Connection.cs` authorizes users in Gravity API. 

It asks the user to sign a message via Metamask and if successful saves an authorization token for further requests.

[Example](https://github.com/Gravity-Studio-Digital-Wear/UnitySDK-WebGL-example/blob/main/Plugins/GravityLayer/Example/Scripts/GLayerManager.cs#L25). See `GravitySDK` game object and attached `GLayerManager.cs` script in `Assets/Plugins/GravityLayer/Example/Scenes/ExampleGravitySDK.unity` scene.

## Fetching wearables

To fetch wearables call `FetchWearables()` method from `Assets/Plugins/GravityLayer/CoreAsync/Wearables/Wardrobe.cs`. 

It will fill in the public variable `List<Wearable> Wearables`.

[Example](https://github.com/Gravity-Studio-Digital-Wear/UnitySDK-WebGL-example/blob/main/Plugins/GravityLayer/Example/Scripts/Inventory/CustomizedInventory.cs#L47). See `FetchGLayerWearables()` method in `Assets/Plugins/GravityLayer/Example/Scripts/CustomizedInventory.cs` script in `Assets/Plugins/GravityLayer/Example/Scenes/ExampleGravitySDK.unity` scene.

## Equipping wearables

To equip a wearable call `DownloadAvatar()` method from the `Downloader` class.

[Example](https://github.com/Gravity-Studio-Digital-Wear/UnitySDK-WebGL-example/blob/main/Plugins/GravityLayer/Example/Scripts/Inventory/ItemWearable.cs#L23). See `DownloadAvatar()` method in `Assets/Plugins/GravityLayer/Example/Scripts/Inventory/ItemWearable.cs` script in `Assets/Plugins/GravityLayer/Example/Scenes/ExampleGravitySDK.unity` scene.