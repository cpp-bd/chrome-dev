## Chrome Windows Build

* Run cmd as administrator
* fetch interruption => ` gclient runhooks `

* Environment Variable
```sh
set vs2019_install=C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise
set GYP_MSVS_VERSION=2019
```

* Installing Debugging Tools Windows
```sh
If the Windows SDK is already installed, open Settings, navigate to Apps & features, 
select Windows Software Development Kit, and then 
click Modify to change the installation to add Debugging Tools for Windows.
```

* Duplicate Folder:
```sh
xcopy chromium chromium-backup /O /X /E /H /K
```

* Project File Generation
```sh
gn gen --ide=vs out\Default --args="is_component_build = true is_debug = true"
devenv out\Default\all.sln
```

* Build
```sh
autoninja -C out\Default chrome
```
