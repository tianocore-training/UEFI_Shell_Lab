---?image=assets/images/gitpitch-audience.jpg
@title[Platform Build Lab]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### UEFI Shell Lab - OVMF with QEMU  or MinnowBoard MAX/Turbot

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  UEFI Shell Application

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->

 @fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell  (QEMU or MAX/Turbot)</span><br><br>
 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell Commands</span><br><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell Scripts</span> <br>
 

---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Shell Lab QEMU Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Shell Lab w/ QEMU</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Skip if continuing with  &nbsp;<a href="https://gitpitch.com/Laurie0131/UEFI_Shell_Lab/master#/6">MinnowBoard MAX / Turbot @fa[angle-right gp-bullet-cream]</a></span>



---?image=/assets/images/slides/Slide4.JPG
@title[QEMU Running OVMF]
<p align="right"><span class="gold" >QEMU Running OVMF</span></p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<span style="font-size:0.5em" ><font color="gray">See Platform Build lab for "RunQemu.sh" script</font></span>


Note:

see Platform Build lab for "RunQemu.sh" script

RunQemu.sh:
- Create a Linux shell script to run the QEMU from the run-ovmf directory

`bash$ gedit RunQemu.sh`
<br>
`qemu-system-x86_64 -pflash bios.bin -hda fat:rw:hda-contents -net none     -debugcon file:debug.log -global isa-debugcon.iobase=0x402 `
<br>
Save and Exit


---?image=/assets/images/slides/Slide6.JPG
@title[QEMU Running OVMF cont]
<p align="right"><span class="gold" >QEMU Running OVMF</span></p>


Note:


---?image=/assets/images/slides/Slide8.JPG
@title[QEMU boot to UEFI Shell]
<p align="right"><span class="gold" >QEMU boot to UEFI Shell</span></p>

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

<span style="font-size:0.5em" >skip to UEFI Shell Commands : &nbsp;&nbsp; <a href=""> @fa[angle-right gp-bullet-cream]</a></span>


Note:

---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Shell Lab Max/Turbot Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Shell Lab w/ Max/Turbot</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Skip if continuing with QEMU &nbsp;<a href="https://gitpitch.com/Laurie0131/UEFI_Shell_Lab/master#/9"> @fa[angle-right gp-bullet-cream]</a></span>

---?image=/assets/images/slides/Slide11.JPG
@title[Max Test System 02]
### <p align="right"><span class="gold" >Setup MinnowBoard Max Test System</span></p>


Note:

- Open Terminal Prompt (Cnt-Alt-T)
```
bash$ dmesg                     	#(to check which USB port is assigned)
bash$ sudo chmod 666 /dev/ttyUSBn	#(where n is the FTDI number)
```
- dmesg command  shows which - ttyUSBn


---?image=/assets/images/slides/Slide13.JPG
@title[Power on MinnowBoard MAX]
### <p align="right"><span class="gold" >Power on MinnowBoard MAX</span></p>


Note:
- Connect the Power supply cable to the MinnowBoard  MAX
```
bash$ screen /dev/ttyUSBn 115200
```
- MinnowBoard MAX should boot to the UEFI Shell in the Terminal – Screen .

- While in screen  Cnt-A then D goes back to terminal
```
 bash$ screen –r #(returns to screen)
```
- Note: Cnt-H for Backspace

**Warning do not use any other power supply than 5V or the board will Fry


---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Shell Lab Commands Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Shell Commands </span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Commands from the Command Line Interface</span>


---?image=/assets/images/slides/Slide16.JPG
@title[Common Shell Commands ]
### <p align="right"><span class="gold" >Common Shell Commands For Debugging</span></p>


Note:

Next for this lab there are a few shell commands that will help us with debugging. For example if you are writing a driver, you would want to get familiar with these shell commands. Each of these commands will have a help option to give you further information about these commands.

We are not going to go all were these in detail but just to make you aware of the shell commands.


---?image=/assets/images/slides/Slide18.JPG
@title[Shell Help Command ]
### <p align="right"><span class="gold" >Shell Help</span></p>


Note:

Next let’s just try the help shell command. So once you reach the shell go ahead and type: “help –b”
And what you will see is the list of all the shell commands built into this platform followed by a one liner information about each command.
To exit, this emulation simply type: “reset”


---?image=/assets/images/slides/Slide20.JPG
@title[Shell mm Command ]
### <p align="right"><span class="gold" >Shell "mm"</span></p>


Note:


---?image=/assets/images/slides/Slide22.JPG
@title[Shell mm -?   Command ]
### <p align="right"><span class="gold" >Shell "mm"</span></p>


Note:


---?image=/assets/images/slides/Slide24.JPG
@title[Shell mem Command ]
### <p align="right"><span class="gold" >Shell "mem"</span></p>


Note:


---?image=/assets/images/slides/Slide26.JPG
@title[Shell memmap Command ]
### <p align="right"><span class="gold" >Shell "memmap"</span></p>


Note:


---?image=/assets/images/slides/Slide28.JPG
@title[Shell drivers Command ]
### <p align="right"><span class="gold" >Shell "drivers"</span></p>


Note:



---?image=/assets/images/slides/Slide30.JPG
@title[Shell devices Command ]
### <p align="right"><span class="gold" >Shell "devices"</span></p>


Note:


---?image=/assets/images/slides/Slide32.JPG
@title[Shell devtree Command ]
### <p align="right"><span class="gold" >Shell "devtree"</span></p>


Note:


---?image=/assets/images/slides/Slide34.JPG
@title[Shell handle Database Command ]
### <p align="right"><span class="gold" >Shell handle database - "dh"</span></p>


Note:


---?image=/assets/images/slides/Slide36.JPG
@title[Shell Load Command ]
### <p align="right"><span class="gold" >Shell "load"</span></p>


Note:




---?image=/assets/images/slides/Slide38.JPG
@title[Shell Stall Command ]
### <p align="right"><span class="gold" >Shell "stall"</span></p>


Note:



---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Shell Lab Scripts Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Shell Scripts</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Use Scripting with UEFI Shell</span>

---
@title[UEFI Shell Scripts ]
### <p align="right"><span class="gold" >UEFI Shell Scripts</span></p>
<br>
<span style="font-size:0.9em" >The UEFI Shell can execute commands from a file, which is called a batch script file (<font face="Courier New"><b>.nsh</b></font> files). </span>
<br>
<br>
<span style="font-size:0.8em" ><b>Benefits:</b> These files allow users to simplify routine or repetitive tasks. <br>
- <span style="font-size:0.7em" >Perform basic flow control. </span>
- <span style="font-size:0.7em" >Allow branching and looping in a script. </span>
- <span style="font-size:0.7em" >Allow users to control input and output and call other batch programs (known as script nesting). </span>

Note:
The UEFI Shell can execute commands from a file, which is called a batch script file (.nsh files). 
<br>
Benefits: These files allow users to simplify routine or repetitive tasks. <br>
- Perform basic flow control. 
- Allow branching and looping in a script. 
- Allow users to control input and output and call other batch programs (known as script nesting). 

---?image=/assets/images/slides/Slide42.JPG
@title[Writing UEFI Shell Scripts]
### <p align="right"><span class="gold" >Writing UEFI Shell Scripts </span></p>

Note:

With the UEFI shell There is an editor included. This is a very simple editor but can help if running on the target system without an OS "Nice" editor available.

SHell editor help  menu - Cnt W

At the shell prompt

Shell> fs0:

FS0:\> edit HelloScript.nsh 

Type : echo “Hello World“



Press “F2”- Enter Press “F3” to exit

---?image=/assets/images/slides/Slide44.JPG
@title[Hello World Script]
### <p align="right"><span class="gold" >Hello World Script</span></p>


Note:

In the shell, type HelloScript for the following result:

```
HelloScript.nsh
```

Close the QEMU (not necessary on MAX/ Turbot)

---?image=/assets/images/slides/Slide46.JPG
@title[UEFI Shell Nested Scripts ]
### <p align="right"><span class="gold" >UEFI Shell Nested Scripts </span></p>



Note:

QEMU: Copy the Scripts from the ~/FW/LabSampleCode/ShellScripts to the run-ovmf directory  ~/run-ovmf/hda-contents

MAX/Turbot: Copy the Scripts from the ~/FW/LabSampleCode/ShellScripts to
USB Thumb Drive

---
@title[UEFI Shell Script Example]
<br>
<p align="center"><span class="gold" >UEFI Shell Script Example</span></p>

<span style="font-size:0.8em"><font color="yellow">Script1.nsh</font></span>
```shell
# Simple UEFI Shell script file
echo  -off
script2.nsh
if exist %cwd%Mytime.log then
     type Mytime.log
endif
echo "%HThank you.” “%VByeBye:) %N"
```
<span style="font-size:0.8em"><font color="yellow">Script2.nsh</font></span>
```shell
# Show nested scripts
time > Mytime.log
for %a run (3 1 -1)
    echo %a counting down
endfor
```

Note:
walk through the script calling the second script
- if
- for loop
  - %a counting down...
  
---?image=/assets/images/slides/Slide49.JPG
@title[Run UEFI Shell Scripts ]
### <p align="right"><span class="gold" >Run UEFI Shell Scripts</span></p>



Note:
QEMU: Run the RunQemu.sh from the terminal (Cnt-Alt-T)<br>
`   bash$ cd ~run-ovmf`<br>
`    bash$ . RunQemu.sh`

<br>
BOTH: At the Shell prompt Type  
<br>
`Shell> fs0:`<br>
`FS0:\> Script1`
<br>
`FS0:\> Edit Script1.nsh`

 
---?image=/assets/images/slides/Slide51.JPG
@title[Run UEFI Shell Scripts cont ]
### <p align="right"><span class="gold" >Run UEFI Shell Scripts</span></p>



Note:
- Remove the “#” on the first line


- Press “F2”
- Enter
- Press “F3” to exit
- Type 
- FS0:\> Script1


---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<br>
 @fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell  (QEMU or MAX/Turbot)</span><br>
 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell Commands</span><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Run UEFI Shell Scripts</span> <br>

 

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/Questions.png =10x) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```
