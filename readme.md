# Just a compiled version of Masscan for windows

View Masscan project 

[https://github.com/hubert3/masscan](https://github.com/hubert3/masscan "Here")

**How to use it:**

**1.Download capable executable file:**

[https://github.com/Arryboom/MasscanForWindows/blob/master/masscan64.exe](https://github.com/Arryboom/MasscanForWindows/blob/master/masscan64.exe?raw=true "64 Bit")
[https://github.com/Arryboom/MasscanForWindows/blob/master/masscan32.exe](https://github.com/Arryboom/MasscanForWindows/blob/master/masscan32.exe?raw=true "32 Bit")

**2.Install Winpcap**

[https://www.winpcap.org/](https://www.winpcap.org/ "Winpcap.org")

**3.Run executable file in command shell**:

```
masscan --help
```

see if you can got echo back like this:

```
	MASSCAN is a fast port scanner. The primary input parameters are the
	IP addresses/ranges you want to scan, and the port numbers. An example
	is the following, which scans the 10.x.x.x network for web servers:
	 masscan 10.0.0.0/8 -p80
	The program auto-detects network interface/adapter settings. If this
	fails, you'll have to set these manually. The following is an
	example of all the parameters that are needed:
	 --adapter-ip 192.168.10.123
	 --adapter-mac 00-11-22-33-44-55
	 --router-mac 66-55-44-33-22-11
	Parameters can be set either via the command-line or config-file. The
	names are the same for both. Thus, the above adapter settings would
	appear as follows in a configuration file:
	 adapter-ip = 192.168.10.123
	 adapter-mac = 00-11-22-33-44-55
	 router-mac = 66-55-44-33-22-11
	All single-dash parameters have a spelled out double-dash equivalent,
	so '-p80' is the same as '--ports 80' (or 'ports = 80' in config file).
	To use the config file, type:
	 masscan -c <filename>
	To generate a config-file from the current settings, use the --echo
	option. This stops the program from actually running, and just echoes
	the current configuration instead. This is a useful way to generate
	your first config file, or see a list of parameters you didn't know
	about. I suggest you try it now:
	 masscan -p1234 --echo
```

**If not:**

You got any error like losing **packet.dll**,**wpcap.dll**,or 0x00000007,then you should search file packet.dll or wpcap.dll on your system folder,they usually showed in C:\Windows\system32\ or C:\Windows\Syswow64,found the right bit dll and copy they to the masscan folder then rerun again.

**Compiled with :** 

- VS2013

  for successful compiled the source code from orignal project with VS2013,you'll need to add follow code in \misc\string_s.h below the VS2010 section:

  ```
	#if defined(_MSC_VER) && (_MSC_VER == 1800)
	/*Visual Studio 2013*/
	# include <stdio.h>
	# include <string.h>
	# define strcasecmp     _stricmp
	# define memcasecmp     _memicmp
	# ifndef PRIu64
	#  define PRIu64 "llu"
	#  define PRId64 "lld"
	#  define PRIx64 "llx"
	# endif
  ```

**File info:** 

- File: masscan64.exe
- Size: 236544 bytes
- Modified: 04-09-2018,17\:36\:42
- MD5: 712CDF0F9CE90680B36AA85FC09DDA59
- SHA1: BAF6B7AA4F5E74F1046BCB4B44908A0761E91D0D
- CRC32: 45824682  

***
- File: masscan32.exe
- Size: 206848 bytes
- Modified: 04-09-2018,17\:36\:39
- MD5: 62C4D1333FE99C35EB805649E4B685B8
- SHA1: 04A18913664450206D38549BF30BAD51D4131080
- CRC32: 5B7B5348

Thanks **hubert3** takes so many sharp tools for us!