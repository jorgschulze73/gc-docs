---
title: Android
layout: default
parent: Device Setup
grand_parent: Installation
nav_order: 3
---

Exeggcute supports 64 bit Android devices

{: .highlight-title }
> Warning
>
> Niantic has dropped support for 32-bit Android devices with release 0.369.0[^1]

### Requirements

- Android 9 or above
- Device needs to be rooted
- Device needs to pass [Play Integrity] basic attestation

----

### How To

1. Install latest Exeggcute apk
2. Install latest supported Pokémon GO apk
3. Enable `Magisk Hide` for Pokémon GO if necessary
4. Place your Exeggcute [configuration] file at `/data/local/tmp/config.json`
5. Run Exeggcute once and grant it root permissions
6. Relaunch Exeggcute, it will now take care of keeping Pokémon GO alive

{: .note }
> You can check if your device passes Play Integrity using [this](https://play.google.com/store/apps/details?id=gr.nikolasspyr.integritycheck) app

----

### Logging

Exeggcute uses the standard Android logging framework. To gather logs you can use:

{% highlight bash %}
adb logcat -s "Exeggcute"
# or
logcat -s "Exeggcute"
{% endhighlight %}

[^1]: [Discontinued Support for 32-Bit Android Devices](https://niantic.helpshift.com/hc/en/6-pokemon-go/faq/2572-discontinued-support-for-32-bit-android-devices)
[Play Integrity]: https://developer.android.com/google/play/integrity
[configuration]: {% link docs/installation/device-setup/configuration.md %}
