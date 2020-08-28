
Instructions for adding the serial port terminal library to get console redirect after the shell is loaded


1.	Copy the MinPlatformBuild/UpX/SerialPortTerminalLib  directory to C:/FW/UpX/edk2-platforms/Platform/Intel/BoardModulePkg/Library
```
$> copy MinPlatformBuild\UpX\SerialPortTerminalLib  C:\FW\UpX\edk2-platforms\Platform\Intel\BoardModulePkg\Library 

```

2.	Add this library to BdsDxe driver ,  to add the serial device to ConIn and ConOut variables


In edk2-platforms/Platform/Intel/WhiskeylakeOpenBoardPkg/UpXtreme/OpenBoardPkg.dsc

```
MdeModulePkg/Universal/BdsDxe/BdsDxe.inf{
<LibraryClasses>
  NULL|BoardModulePkg/Library/SerialPortTerminalLib/SerialPortTerminalLib.inf
}

```
3.	Include these 2 drivers to the Up Xtreme’s OpenBoardPkg.dsc and OpenBoardPkg.fdf

-	In dsc  
edk2-platforms/Platform/Intel/WhiskeylakeOpenBoardPkg/UpXtreme/OpenBoardPkg.dsc
```
 MdeModulePkg/Universal/SerialDxe/SerialDxe.inf
 MdeModulePkg/Universal/Console/TerminalDxe/TerminalDxe.inf
```
-	Under [FV.FvUefiBootUncompact] FV in Fdf 
 edk2-platforms/Platform/Intel/WhiskeylakeOpenBoardPkg/UpXtreme/OpenBoardPkg.fdf

```
INF  MdeModulePkg/Universal/SerialDxe/SerialDxe.inf
INF  MdeModulePkg/Universal/Console/TerminalDxe/TerminalDxe.inf
```

