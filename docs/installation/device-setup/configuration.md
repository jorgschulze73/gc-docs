---
title: Configuration File
layout: default
parent: Device Setup
grand_parent: Installation
nav_exclude: true
---

Once you're done installing and setting up all the [pre-required] software, you can finally move onto configuring Exeggcute itself.

The expected configuration is in JSON format and looks like this:

```
{
    "api_key": "<exeggcute_api_key>",
    "device_name": "<device_name>",
    "rotom_url": "ws://<rotom_url:port>",
    "rotom_secret": "<rotom_secret>",
    "workers_count": <workers_count>,
    "remote_attestations": <remote_attestations>
}
```

Depending on the platform and deployment model you're following for your devices, this configuration might need to be placed in one or another directory; usually you wouldn't need to bother with this yourself as the process is often automated by specific tools or scripts.

### API Key

The field `api_key` is supposed to hold your Exeggcute API key, that you can get by following instructions in the Discord server.

### Device name
The field `device_name` is an optional string field that you can use to override the device name that Exeggcute posts to both Rotom and Dragonite.

{: .note }
> Starting with iOS16, third-party apps won't be able to access the real device name anymore.[^1]
>
> You will have to fill this property if you want your devices to have a human-readable name in your Rotom and Dragonite dashboards.

### Rotom URL
The field `rotom_url` should point to your [Rotom] installation. The default port is `7070`.

### Rotom secret
The field `rotom_secret` is an optional string field that you should set in case your [Rotom] installation has been configured to validate client connections.

### Workers count
The field `workers_count` is an optional integer field that you can use to override the number of mapping workers that Exeggcute will run on a single device _simultaneously_.

{: .note }
> The default value is `0` and the upper limit is `50`

### Remote attestations
The field `remote_attestations` is an optional boolean flag available on Android that you can use to redirect SafetyNet and Play Integrity attestations to some other devices.

This is particularly useful in case you want to run Exeggcute on targets that are not able to pass attestations by themselves, such as emulators and virtual devices.

[pre-required]: {% link docs/installation/installation.md %}
[^1]: [com.apple.developer.device-information.user-assigned-device-name](https://developer.apple.com/documentation/bundleresources/entitlements/com_apple_developer_device-information_user-assigned-device-name)
[Rotom]: https://github.com/UnownHash/Rotom
