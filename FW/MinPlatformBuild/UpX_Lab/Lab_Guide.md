- Open “Git Bash” 
- Linux like commands “/” for dirs.
- Use “/c” to go to C: in Windows, etc.
- Cd to the Work Space: 

```
$ cd /c/fw
$ mkdir UpX
$ cd UpX
```

In the Git Bash command line window Do the following:<br>

**Edk2**
```
$ git clone https://github.com/tianocore/edk2.git
$ cd edk2
$ git submodule update --init
$ cd ..
```
**Edk2-platforms**
```
$ git clone https://github.com/tianocore/edk2-platforms.git
```
**Edk2-non-osi**
```
$ git clone https://github.com/tianocore/edk2-non-osi.git
```
**FSP**
```
$ git clone https://github.com/Intel/FSP.git
```

**Open a Visual Studio Command prompt**<br>
Cd to the Min Platform Build directory
```
$> cd \
$> cd Fw\UpX\edk2-platforms\Platform\Intel
```

Check the python version
```
$> python --version
```
Check for platforms that are MinPlatform capable
```
$> python build_bios.py -l
```
**Build the Up Xtreme**
- note use "`-t VS2017`" at end of next command  if VS is not VS2015
```
$> python build_bios.py -p UpXtreme
```

After the build is complete use dediprog to flash into the Up Xtreme system

**Make a change**<br>
Copy (or use Windows paint to create a logo) Logo.bmp to C:\UpX\edk2\MdeModulePkg\Logo

**Build the Up Xtreme**
```
$> python build_bios.py -p UpXtreme
```

After the build is complete use dediprog to flash into the Up Xtreme system


