# Aquantia-macOS-Patches
These patches allow `AppleEthernetAquantiaAqtion` to work properly in Monterey, Ventura, Sonoma, Sequoia, and Tahoe when AppleVTD is not available. They were created for AMD platforms, but work equally well on Intel platforms when AppleVTD is not enabled.

There are 11 patches in the `.plist`. The first nine belong to **Set 1**. The last two belong to **Set 2**. Either Set 1 or Set 2 patches may be used depending on your preference. Do not enable both Set 1 and Set 2 patches at the same time. All patches from a set must be enabled in order to operate the Aquantia 10GbE card properly.

Notes:
1. Set 2 patches make use of OpenCore's `Mask` and `ReplaceMask` features[^1].
2. OpenCore's kernel quirk `ForceAquantiaEthernet` needs to be **enabled**.
3. These patches have been tested with **AQC-107** and **AQC-113** running under Monterey, Ventura, Sonoma, Sequoia, and Tahoe.
4. These patches should not be used in Big Sur or Monterey 12.0, 12.1 and 12.2. The patches apply only to Monterey 12.3 and later.

An easy way to import the patches into *config.plist* is by using `OpenCore Configurator`. Navigate to the **Kernel --> Patch** section and right-click to select `Import set of patches` from the pop-up menu:

![Screen Shot 2022-12-03 at 8 40 18 AM](https://user-images.githubusercontent.com/48335376/205451692-7b40fd63-aa6a-4126-b7e7-b0dface3c79b.png)

Then select the `.plist` file downloaded from this repository. The result will look something like this:

<img width="1888" alt="Screenshot 2023-06-24 at 12 38 42 PM" src="https://github.com/CaseySJ/Aquantia-macOS-Patches/assets/48335376/cd73a43d-c447-4dad-bc36-18455b1436e8">

---
**Sonoma/Sequoia/Tahoe Patches have not yet been added to OCAT**

The patches are also available directly from within `OCAT` (OpenCore Auxiliary Tools). Navigate to the **Kernel --> Patch** section and right-click to select `Preset` from the pop-up menu:

![Screen Shot 2022-12-03 at 8 44 53 AM](https://user-images.githubusercontent.com/48335376/205451855-e9be71c5-bd65-490c-880c-ba8d5e82436b.png)

Then select either `Aquantia Compact Patches` (Set 2) or `Aquantia Patches` (Set 1):

![Screen Shot 2022-12-03 at 8 54 08 AM](https://user-images.githubusercontent.com/48335376/205452518-755fbafe-71ef-4303-9ef3-d549f5fe29c6.png)

The result will look something like this:

![Screen Shot 2022-12-03 at 8 54 41 AM](https://user-images.githubusercontent.com/48335376/205452409-d67c27fa-d51c-4cb7-a65d-fb1794bb79b3.png)

While it's perfectly okay to add both sets of patches to `config.plist`, **only one set** should be enabled at a time. Do **not** enable both Set 1 and Set 2 at the same time. 

[^1]: _OCValidator_ may raise a warning that may be ignored.
