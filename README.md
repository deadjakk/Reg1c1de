### Reg1c1de: Windows Registry Privesc Scanner
#### Summary (from help output):
Reg1c1de is a tool that scans specified registry hives and reports on any keys where the user has write permissions
In addition, if any registry values are found that contain file paths with certain file extensions and they are writeable, these will be reported as well.

More information on this tool and it's use can be found in the related github.io article: [here](https://deadjakk.github.io/registry_privesc.html)  

Help output:
```
++++++++++++++Reg1c1de++++++++++++++++
+author: @deadjakk | http://shell.rip+
++++++++++++++++++++++++++++++++++++++


Description:
Reg1c1de is a tool that scans specified registry hives and reports on any keys where the user has write permissions
In addition, if any registry values are found that contain file paths with certain file extensions and they are writeable, these will be reported as well.
These keys should be investigated further as they could potentially lead to a path to privilege escalation or other evil

Arguments: (THESE ARE ALL OPTIONAL!)
-h      show this help message
-vv     enable debug output (more verbose)
-e      scan the entire specified hive, this is disabled by default
-o      filename to write the vulnerable keys to csv, example -o=filename
-k      base key to enumerate from under the hive, default=Software, example -k=Software
-df     disables writeable file checking, in case you don't want to make thousands of access denied file open attempts
-r      four letter shorthand of the root hive to enumerate from, default=HKLM, example -r=HKLM
        Acceptable values are: HKCU, HKLM, HKCR, HKCC, HKU

-writetests     enabling this flag will enable write tests, which will write a dummy registry key and value to every discovered instance of write access to a key.
I DO NOT recommend using this, especially if you cannot make a registry backup, nevertheless it is here.

Example Usage:
Reg1c1de.exe -v -o=outputfile -r=HKLM -e
```
