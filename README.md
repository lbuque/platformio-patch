PlatformIO-Patch
=================

PlatformIO Package Manager automatically installs pre-built packages (Frameworks, toolchains, libraries) required by development Development Platforms and build process. Sometimes you need to override original files with own versions: configure custom GPIO, do changes to built-in LD scripts, or some patching to installed library dependency.[^1]

``PlatformIO-Patch`` was created to solve this problem.

[^1]: This instruction is from https://docs.platformio.org/en/latest/scripting/examples/override_package_files.html

Example
--------

platformio.ini

```ini
[patch]
root_dir = ../..
patches = 0001.patch
          0002.patch

[env:my_env]
extra_scripts = pre:pio_patch.py
custom_patch_section = patch
```

``custom_patch_section``: Specifies the section used by PlatformIO-Patch
``root_dir``: specify root directory for applying patch
``patches``: patch list

Application
------------

https://github.com/Xinyuan-LilyGO/T-Wristband/blob/master/examples/T-Wristband-DRV2605/platformio.ini

Suggestion
-----------

Any useful suggestions are welcome!
