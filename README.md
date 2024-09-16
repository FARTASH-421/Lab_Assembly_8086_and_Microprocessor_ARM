Exercises of Low Level Programming with 8086 Assembly Lecture, implemented with Emu8086 and DOSBox.

In general, Emu8086 is easier to use, write code and test program. For macOS, since it does not have macOS support, Crossover or directly Wine could be used. But sometimes Emu8086 may not work properly since it just and emulator, remember to check final program in DOSBox.

DOSBox
Installation Windows
Download and install DOSBox under C:\dosbox
Extract files of dosbox_bin.zip into C:\dosbox\bin
Open configuration file C:\dosbox\DOSBox <version> Options and add following configurations at the end of file;
Change paths according to your setup:

[autoexec]
mount c c:\dosbox
mount b c:\dosbox\bin
mount d c:\Users\creat\Documents\GitHub\8086-assembly
PATH=z:\;c:\;b:\;d:\;

d:
cd exe
Installation macOS
Download and install DOSBox under Applications
Extract files of dosbox_bin.zip into ~/dosbox
Open configuration file ~/Library/Preferences/DOSBox <version> Preferences and add following configurations at the end of file;
Change paths according to your setup:

[autoexec]
mount b ~/dosbox
mount d ~/Projects/Personal/8086-assembly
PATH=z:\;b:\;d:\;

d:
cd exe
Compile
Inside DOSBox;

// this will create .obj file from .asm (and .lst if you want)
masm test.asm

// this will create .exe from .obj (and .map if you want)
link test.obj

// linking multiple .obj files;
link test.obj + test2.obj

// if program is in type of com
// this will convert .exe to .com
exe2com test.exe
Debug
Inside DOSBox;

debug test.exe

-r    show registers, flags and next step
-t    run single step
-g    run to offset
-g cs:1e
-d    dump memory 
-d ds:0
-u    unassembly
-u cs:1e
-e    enter data into memory
-e 100 8B 07
-u 100 (see the assembly code)
