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
4. Download latest supported [Pokémon GO decrypted IPA], rename it to zip and extract it
5. Launch Exeggcute: `<exeggcute> <extracted_pogo_ipa>/Payload/PokmonGO.app`

----

### How To (Kernel Extension)

1. Boot your device in recovery mode, then open terminal from the `Options` menu
2. Enable third-party kernel extensions: `bputil -k -c`
3. Disable System Integrity Protection: `csrutil disable`
4. Reboot your device normally
5. Disable codesign enforcement: `sudo nvram boot-args="cs_enforcement_disable=1 amfi_get_out_of_my_way=1"`
6. Install Exeggute's kernel extension: `sudo cp -r <Exeggcute.kext> /Library/Extensions/`
7. Open `System Preferences` and allow Exeggcute's kernel extension
8. Reboot your machine again when prompted to do so
9. Finally, load kernel extension: `sudo kextload /Library/Extensions/Exeggcute.kext`

{: .highlight-title }
> Warning
>
> Loading kernel extensions on macOS requires to reduce the overall security of the operating system; keep this in mind in case you're planning to run Exeggcute on your personal device.

{: .note }
> If you're experiencing apps crashing after disabling System Integrity Protection, you can try adding this additional boot-arg: `ipc_control_port_options=0`

----

### Running multiple instances

As Exeggcute runs in headless mode, it's totally possible to launch multiple instances:

{% highlight bash %}
  ./exeggcute {OPTIONS} app_bundle
  OPTIONS:
      -h, --help                             Display this help menu
      -i[instance], --instance=[instance]    Instance number                (default: 1)
      -w[workers], --workers=[workers]       Override workers number        (optional)
      app_bundle                             Path to the PokmonGO.app bundle
{% endhighlight %}

For example, the following commands can be used to launch 2 different Exeggcute instances that will be automatically restarted in case of crashes:

{% highlight bash %}
# Run instance 1 with number of workers specified in config.json
pm2 start "<exeggcute> --instance=1 <extracted_pogo_ipa>/Payload/PokmonGO.app" --name "Alpha"

# Run instance 2 with a custom number of workers
pm2 start "<exeggcute> --instance=2 --workers=50 <extracted_pogo_ipa>/Payload/PokmonGO.app" --name "Beta"
{% endhighlight %}

[install]: #how-to-kernel-extension
[configuration]: {% link docs/installation/device-setup/configuration.md %}
[Pokémon GO decrypted IPA]: https://armconverter.com/decryptedappstore/us/pokemon%20go
