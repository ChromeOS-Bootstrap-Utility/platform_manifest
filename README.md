# ChromeOS Bootstrap Utility - Official Manifest #


Getting started
---------------

To get started with this tool, first, you need to get familiar with [Git](https://source.android.com/setup/develop).

Sync 
---------------
```bash

# First of all, initialize the tool in a working directory of your choice
cros-bootstrap.sh --init https://github.com/ChromeOS-Bootstrap-Utility/platform_manifest.git -b <your desired ChromeOS & Brunch version number>-<the scope codename>

# For example, if you want to make a bootable Brunch Framework-based ChromeOS image based on ChromeOS v97, just type
cros-bootstrap.sh --init https://github.com/ChromeOS-Bootstrap-Utility/platform_manifest.git -b 97-ultra-legacy

# To sync, just type
cros-bootstrap.sh --sync
```

Build
---------------

```bash

# To start the build process, just type
$ . wrapping_up/crosbuild_envsetup.sh

# Choose the target CPU flavor (that is, the overall CPU specs like codename, generation, brand and sub-brand (like Atom, Celeron, Pentium or Intel Core, or Stoney Ridge/Bristol Ridge/Ryzen if AMD CPU is provided) desired ChromeOS & Brunch Framework version (must be a supported ChromeOS & Brunch Framework version in the chosen target CPU flavor) and scope codename 
$ cros-bootstrap.sh --lunch # if you want to choose from a generated list
$ cros-bootstrap.sh --lunch ivy-bridge-v97-ultra-legacy

# Finally, to start building process, type
$ cros-bootstrap.sh --mix ivy-bridge-v97-ultra-legacy

```
With this last command, Brunch Framework official chromeos-install.sh script is launched, with proper arguments so the ChromeOS image can start to be built according to desired options. When image building is done, built image will appear in /out/target/product/(CPU flavor)-(desired ChromeOS version)-(scope codename)/chromeos.img

In the previous example, image output dir will be: /out/target/product/ivy-bridge-v97-ultra-legacy/chromeos.img.

If you want a dual-boot installation, if provided so, when image finishes building, in terminal will also appear the corresponding GRUB bootloader code to the corresponding ChromeOS boot types (normal, debug mode). At the end, script will pop up the GRUB bootloader entries, but also will create 2 text files in the /out/target/product directory, containing the GRUB bootloader entries. Save them in a safe place as you will need those codes in order to add ChromeOS entries to GRUB4DOS or the corresponding GRUB bootloader.

What are "scope codenames"?
---------------
Scope codenames are custom codenames provided to distinguish released Brunch Framework versions from r89 to r121, ChromeOS versions from v89 to v121, and also to assign supported Brunch Framework & ChromeOS versions to Intel CPU families and AMD CPU families.
It's kinda like a way to know up to which version is your CPU supported by ChromeOS & Brunch Framework.

There are 3 scope codenames: `ultra-legacy`, `legacy` and `updated`.
- The `ultra-legacy` scope codename is commonly assigned to CPUs who Brunch Framework used to support from 2021-2022, where latest version used to be around r97.
  The CPUs who usually fits this scope codename are:
  - Intel Core CPUs with Sandy Bridge/Ivy Bridge (2nd and 3rd Gen) platform or codename, up to Kaby Lake/Coffee Lake (9th Gen) platform or codename
  - Intel Core CPUs with Rocket Lake (10th Gen) platform/codename, Alder Lake (11th Gen) platform/codename and Raptor Lake (12th Gen) platform/codename
  - Intel Atom, Celeron & Pentium processors from 2nd and 3rd Gen onwards
  - AMD CPUs with Stoney Ridge/Bristol Ridge platform/codename
  - AMD Ryzen CPUs
  - 


How can I be maintainer?
---------------
```bash

Make a pull request at https://github.com/ResurrectionRemix/Resurrection_packages_apps_Settings/blob/Q/res/values/resurrection_device_maintainers_strings.xml

Make the commit like this by including device in fragment https://github.com/ResurrectionRemix/Resurrection_packages_apps_Settings/commit/9686023738c3b09feaa547cb3658d6c2bda737e1

With your name. Choose any device you want to maintain for but in the pull request please post with an xda thread (optional),  device source and kernel source as the commit message

It will be reviewed and changes will be approved if everything is fine


Approved maintainers will gain access to RR device repo and RR OTA server
Credentials will be given in a separate group created for maintainers
```

Translations 
---------------
```bash

We don't have crowdin at the moment so you can merge a pull request in our repos which require translations. Please validate your XMLs first. We will review them and merge them as soon as possible.
```

Lastly 
---------------
```bash
Remember to give credits where necessary
```


### That's all for now. ###

Happy building
---------------
```bash


### - RR Team ###

