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
Deb package was built in Ubuntu18.04, it can be used above (include) 18.04.<br>
- How to package deb format all the details of AToverMBIMTool_CMD could be found in below:<br>
    1. Create a directory, such as "attool2.0.0.4_cmd", it include "DEBIAN" and "usr" directories.<br>
    2. Edit "DEBIAN"<br>
	(1) "control" file: Introduce the basic name, content, author, version, purpose, etc. of the<br>
	AToverMBIMTool_CMD, which can be filled in according to the situation.<br>
	(2) "postinst" file: The directory to be created during the installation process and the icon configuration file<br>
	to be copied to the specified directory, etc.<br>
	(3) "postrm" file: The deletion process requires deleting directory files, etc.<br>
    3. Edit "usr"<br>
	(1) "bin" file: It will be used to store executable binary program.<br>
	(2) "lib/libattool_foxconn_cmd" file: It will be used to store dynamic libraries that need to be linked to executable binary programs.<br>
    4. `sudo cp /usr/bin/attool-cmd attool2.0.0.4_cmd/usr/bin/`
    5. `sudo cp /usr/libattool_foxconn_cmd/libattool.so attool2.0.0.4_cmd/usr/lib/libattool_foxconn_cmd/`
    6. `dpkg-deb --build attool2.0.0.4_cmd/`

## 3. Uninstall deb package
- If you have an older version tool, you shall uninstall it firstly. The uninstall process of the attool-cmd as below:<br>
    1. `sudo dpkg -P attool-cmd`

## 4. Install deb package
- The install process of the AT over MBIM Command Line Tool.<br>
    1. `sudo dpkg -i --force-overwrite XXX.deb`

# Release history
- attool-cmd version:2.0.0.4<br>
    1. Add SDX72 support to send at commands.<br>
    2. Fixed file of *.txt is empty, printf error information.<br>
    3. Fixed mantis:25131: attool can send blank command.<br>

- attool-cmd version:2.0.0.3<br>
    1. After V2.0.0.3, rename OUT_BIN "attool-cmd".<br>
    2. Use "DealRebootDeviceCommand" to solve misunderstand of at commands that need reboot module.<br>
    3. Use "Compatibility_Check" to distinguish SDX12 after AP001 use another API to send at command.<br>
    4. Filter "\n" of "AppendDataToFile" and "AppendATToFile".<br>

- attool-cmd version:2.0.0.2<br>
    1. Modify FoxGetFwVersion API location and add DmsAtCommandEvent for sdx55.<br>

- attool-cmd version:2.0.0.1<br>
    1. Fixed at commands cannot send after kill mbim-proxy.<br>

- attool-cmd version:2.0.0.0<br>
    1. First version, support MBIM device to send at commands.<br>
