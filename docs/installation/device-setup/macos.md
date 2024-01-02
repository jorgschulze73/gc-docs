---
title: macOS
layout: default
parent: Device Setup
grand_parent: Installation
nav_order: 2
---

### Requirements

- Apple Silicon device running Big Sur or above

----

### How To

1. Download latest Exeggute kernel extension and [install] it
2. Download latest Exeggcute binaries for macOS
3. Place your Exeggcute [configuration] file in the same directory
4. Download latest supported Pokémon GO decrypted IPA
5. Launch Exeggcute: `<exeggcute> <extracted_pogo_ipa>/Payload/PokmonGO.app`

----

### How To (Kernel Extension)

1. Boot your device in recovery mode, then open terminal from the `Options` menu
2. Enable third-party kernel extensions: `bputil -k -c`
3. Disable System Integrity Protection: `csrutil disable`
4. Reboot your device normally
5. Install Exeggute's kernel extension: `sudo cp -r <Exeggcute.kext> /Library/Extensions/`
6. Open `System Preferences` and allow Exeggcute's kernel extension
7. Reboot your machine again when prompted to do so
8. Finally, load kernel extension: `sudo kextload /Library/Extensions/Exeggcute.kext`

{: .highlight-title }
> Warning
>
> Loading kernel extensions on macOS requires to reduce the overall security of the operating system; keep this in mind in case you're planning to run Exeggcute on your personal device.

[install]: #how-to-kernel-extension
[configuration]: {% link docs/installation/device-setup/configuration.md %}
