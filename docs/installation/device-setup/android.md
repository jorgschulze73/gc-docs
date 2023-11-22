---
title: Android
layout: default
parent: Device Setup
grand_parent: Installation
nav_order: 3
---

Exeggcute supports both 32 and 64 bit Android devices

{: .highlight-title }
> Warning
>
> Niantic has previously indicated 32-bit architecture support will be dropped in future releases[^1]

### Requirements

- Android 8 or above
- Device needs to be rooted
- Device needs to pass [SafetyNet] and [Play Integrity] basic attestation

{: .highlight-title }
> Warning
>
> Niantic has dropped support for Android 7 with release 285.0[^2]

----

### How To

1. Install latest Exeggcute apk
2. Install latest supported Pokémon GO apk
3. Enable `Magisk Hide` for Pokémon GO if necessary
4. Place your Exeggcute [configuration] file at `/data/local/tmp/config.json`
5. Run Exeggcute once and grant it root permissions
6. Relaunch Exeggcute, it will now take care of keeping Pokémon GO alive

{: .highlight-title }
> Warning
>
> Running 32-bit Pokémon GO on a 64-bit device is not supported: you need to install 64-bit apk

{: .note }
> You can check if your device passes SafetyNet using [this](https://play.google.com/store/apps/details?id=com.scottyab.safetynet.sample) app
>
> You can check if your device passes Play Integrity using [this](https://play.google.com/store/apps/details?id=gr.nikolasspyr.integritycheck) app

----

### eMagisk (optional)

TODO

----

### Logging

Exeggcute uses the standard Android logging framework. To gather logs you can use:

{% highlight bash %}
adb logcat -s "Exeggcute"
# or
logcat -s "Exeggcute"
{% endhighlight %}

----

### Android TVs

Android TVs (ATVs) are particularly suitable for mapping as they're affordable and easy to root.

The following is a list of ATV devices confirmed to work with Exeggcute:

| Model        | CPU               | OS    |
|:-------------|:------------------|:------|
| ...          | ...               | ...   |

[^1]: [Discontinued Support for 32-Bit Android Devices](https://niantic.helpshift.com/hc/en/6-pokemon-go/faq/2572-discontinued-support-for-32-bit-android-devices)
[^2]: [Discontinued Support for Android 7](https://niantic.helpshift.com/hc/pl/6-pokemon-go/faq/4302-discontinued-support-for-android-7-1695761816/)
[SafetyNet]: https://developer.android.com/training/safetynet
[Play Integrity]: https://developer.android.com/google/play/integrity
[configuration]: {% link docs/installation/device-setup/configuration.md %}
