This repo will be used to store `*.tar.xz` files from IBS for SLE[1] which can be updated for use with:

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
        "SUSE": [
            {
                "Name": "SUSE-Linux-Enterprise-15-SP5",
                "FriendlyName": "SUSE Linux Enterprise 15 SP5",
                "Default": false,
                "Amd64Url": {
                    "Url": "https://github.com/SUSE/WSL-instarball/releases/download/<tag>/<distro-name>.wsl",
                    "Sha256": "0x<.wsl file hash>"
                }
            },
            {
                "Name": "SUSE-Linux-Enterprise-15-SP6",
                "FriendlyName": "SUSE Linux Enterprise 15 SP6",
                "Default": true,
                "Amd64Url": {
                    "Url": "https://github.com/SUSE/WSL-instarball/releases/download/<tag>/<distro-name>.wsl",
                    "Sha256": "0x<.wsl file hash>"
                }
            }
        ]
    }
}
```

### Reference Links

* [1] to be added later
