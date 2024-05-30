# Environment
  - Ubuntu18.04<br>

# Building on Ubuntu

## 1. Build
How to compile all the details of AToverMBIMTool_CMD could be found in below:<br>
- Firstly, copy the specified version of libfiisdk.so to the "SourceCode" directory. Then, build as follow:<br>
    1. `pushd SourceCode`
    2. `make`
    3. `sudo make install`
    4. `popd`

## 2. Package deb format
- How to package deb format all the details of AToverMBIMTool_CMD could be found in below:<br>
    1. create a directory, such as "attool2.0.0.4_cmd", it include "DEBIAN" and "usr" directories..<br>
    2. Edit "DEBIAN".<br>
	(1)"control" file:Introduce the basic name, content, author, version, purpose, etc. of the document,<br>
	which can be filled in according to the situation.<br>
    3. `sudo make install`
    4. `popd`

# Release history
## 1. Executable binary program
- FoxFlss version:1.0.1<br>
    1. Write default configuration for platform which has not RF_Files.<br>
    2. Add step reboot the module to take effect after writing RF data.<br>

- FoxFlss version:1.0.0<br>
  first version, add FoxFlss tool to support Fcc unlock and write RF data.<br>

- FccLock version:1.0.0<br>
  first version, add FccLock tool to support Fcc unlock.<br>

## 2. FiiSDK dynamic library
- libfiisdk.so version:2.1.6<br>
    1. Packaging the required interfaces for FoxFlss of DW5932e device.<br>
    2. Write default configuration for platform which has not RF_Files.<br>
    3. Add step reboot the module to take effect after writing RF data.<br>

- libfiisdk.so version:2.1.5<br>
    1. Modify Makefile and main.c to build for the Binary files for FccLock of DW5932e device.<br>

- libfiisdk.so version:2.1.4<br>
    1. Packaging the required interfaces for FccLock of DW5932e device.<br>

- libfiisdk.so version:2.1.3<br>
    1. Solving the PCIE device Send AT Command response and indication time interval may cause program exit.<br>
    2. Using the "DealRebootDeviceCommand" API to Resolve Misjudgment of AT Commands that Requires Device Reboot.<br>
    3. When send at commands such as "ATE", "ATZ" to throw error.<br>

- libfiisdk.so version:2.1.2<br>
    1. Support SingleSKU_Tool of sdx products(SDX62) which need fox service.<br>
    2. Add FoxSetNVPathValue_new to support writing efs files larger than 65535 bytes(64K).<br>
    3. Packaging send at command as SetQtunerStatusOfSingleSKU API for SingleSKU_Tool.<br>

- libfiisdk.so version:2.1.1<br>
    1. Support FccLock of sdx products(SDX62) which need fox service.<br>

- libfiisdk.so version:2.1.0<br>
    1. Support to send at commands.<br>

- libdpr.so version:2.0.1<br>
    1. Fix IMEI missing would lead to unlock bioslock failed issue.<br>

- libdpr.so version:2.0.0<br>
    1. Support for SDX55 Lenovo-wwan-dpr and init commit.<br>
    2. Add new FiiSDK to send qmi command, after V2.0.0, all of APIs is foxconn private interface.<br>
