This repo will be used to store `*.tar.xz` files from OBS for Leap[1] and Tumbleweed[2] which can be updated for use with:

```
wsl --install <distro name from `wsl -l -o` output> --web-download
```

via PR to [#gh/microsoft/WSL](https://github.com/microsoft/WSL/pulls) as part of the "ModernDistributions" section of [DistributionInfo.json](https://github.com/microsoft/WSL/blob/master/distributions/DistributionInfo.json).

### [Distribution manifest details](https://learn.microsoft.com/en-us/windows/wsl/build-custom-distro#distribution-manifest-details)

```
"ModernDistributions": {
"<flavor>": [
    {
    "Name": "<version name>",
    "FriendlyName": "<friendly name>",
    "Default": true | false,
    "Amd64Url": {
        "Url": "<tar url>",
        "Sha256": "<tar sha265 hash>"
        },
    "Arm64Url": {
        "Url": "<tar url>",
        "Sha256": "0x<tar sha265 hash>"
        }
    }
}
```

### Example

```
{
    "ModernDistributions": {
        "openSUSE": [
            {
                "Name": "openSUSE-Tumbleweed",
                "FriendlyName": "openSUSE Tumbleweed",
                "Default": false,
                "Amd64Url": {
                    "Url": "https://github.com/openSUSE/WSL-instarball/releases/download/v20250110.0/openSUSE-Tumbleweed-20250108.x86_64-7.31-Build7.31.tar.xz",
                    "Sha256": "0x8c89f858145e2ff778eb061817d91d31ee5bee3b2797af7e4000d236553872b0"
                }
            },
            {
                "Name": "openSUSE-Leap-15.6",
                "FriendlyName": "openSUSE Leap 15.6",
                "Default": false,
                "Amd64Url": {
                    "Url": "https://github.com/openSUSE/WSL-instarball/releases/download/v20250110.0/openSUSE-Leap-15.6-15.6.x86_64-7.19-Build7.19.tar.xz",
                    "Sha256": "0x81d1abf44ab438e5333ff7da09baa101a7c9b64873bb37cfeaf5bf5f0cbed57a"
                }
            }
        ]
    }
}
```

### Reference Links

* [1] https://download.opensuse.org/repositories/Virtualization:/WSL:/instarball/openSUSE_Leap_15.6_images/
* [2] https://download.opensuse.org/repositories/Virtualization:/WSL:/instarball/openSUSE_Tumbleweed_images/
