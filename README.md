# Building Custom ROM for Poco F3 (Alioth/Aliothin)

This guide will help you set up your environment and automatically sync all necessary repositories to build GenesisOS for the Poco F3 (Alioth/Aliothin). The steps below ensure that all device dependencies, including the vendor and kernel, are cloned automatically, so you don't have to worry about manual setup.

`NOTE: You can alter this for any other roms/device by editing alioth_manifest.xml to your_device_manifest.xml`

## Step 1: Initialize Your Local Repository

Begin by cloning the local manifests repository. This repository contains all the necessary configuration files to automatically fetch the device-specific sources:

```bash
git clone https://github.com/bntxperses/local_manifests.git -b aosp-14 .repo/local_manifest
```

## Step 2: Sync the Repositories

Next, synchronize the repositories with the following command:

```bash
repo sync --force-sync -j8 --current-branch --no-tags --no-clone-bundle --optimized-fetch --force-broken
```

### Explanation:

- **Initialization:** The `git clone` command initializes the local repository with the `manifest.xml` for your device, which defines the sources that need to be fetched.

- **Syncing:** The `repo sync` command pulls all the required repositories, ensuring that device-specific dependencies (like the vendor, kernel, etc.) are automatically fetched based on the `manifest.xml`.
