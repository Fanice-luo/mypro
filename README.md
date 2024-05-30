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
    1. Create a directory, such as "attool2.0.0.4_cmd", it include "DEBIAN" and "usr" directories.<br>
    2. Edit "DEBIAN"<br>
	(1) "control" file: Introduce the basic name, content, author, version, purpose, etc. of the AToverMBIMTool_CMD,<br>
	which can be filled in according to the situation.<br>
	(2) "postinst" file: The directory to be created during the installation process and the icon configuration file<br>
	to be copied to the specified directory, etc.<br>
	(3) "postrm" file: The deletion process requires deleting directory files, etc.<br>
    3. Edit "usr"<br>
    4. `popd`
