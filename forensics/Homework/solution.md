# Homework

**Challenge Type: Forensics**  


## Challenge

## Solution

1. Run file command to see what file it is </br>
 ```
 $ file homework.doc
 Composite Document File V2 Document
 ```
 
2. Use antiword or Microsoft Word to see what is in the file
```bash
$ antiword homework.doc

Today’s homework

    - 48 hours hackthebox practice

    - 200 CTF challenges
```
Doesn't seem to have anything interesting other than evidence of forced labor

3. Find the readable strings in the document

```bash
$ strings homework.doc

bjbj
Today
s homework
48 hours hackthebox practice
200 CTF challenges
gd>v
[Content_Types].xml
_rels/.rels
theme/theme/themeManager.xml
sQ}#
theme/theme/theme1.xml
"GJK
TcKBc
v[`E
'.Lq
yDQ"Q
Z6/H
ud9c
J{rJ
Q/B)L
lC=h
W!alf
AXl:X
PxzSq]y<u
n6      m
;B=s!
q5;3
BU`M
b!e9#i
`571
W       0xn?G
theme/theme/_rels/themeManager.xml.rels
6?$Q
K(M&$R(.1
[Content_Types].xmlPK
_rels/.relsPK
theme/theme/themeManager.xmlPK
theme/theme/theme1.xmlPK
theme/theme/_rels/themeManager.xml.relsPK
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<a:clrMap xmlns:a="http://schemas.openxmlformats.org/drawingml/2006/main" bg1="lt1" tx1="dk1" bg2="lt2" tx2="dk2" accent1="accent1" accent2="accent2" accent3="accent3" accent4="accent4" accent5="accent5" accent6="accent6" hlink="hlink" folHlink="folHlink"/>
Gabriel Seet
Normal.dotm
Gabriel Seet
Microsoft Office Word
Title
Project
rstd
ole>
\G{00020
430-
0046}#
2.0#0#C:
\Windows
\System3
e2.tlb
#OLE Aut
omation
ENormal
! Offic
!G{2DF8
D04C-5BF
A-101B-BHDE5
gram
 Files\C ommon
crosoft 
Shared\O
FFICE16\
MSO.DLL#
M 16.0 
 LibrXary
hisDocum@entG
u@Ie
*\CNormalrU
ThisDocument
Project
C:\Program Files\Common Files\Microsoft Shared\VBA\VBA7.1\VBE7.DLL
C:\Program Files\Microsoft Office\root\Office16\MSWORD.OLB
Word
C:\Windows\System32\stdole2.tlb
stdole
C:\Program Files\Common Files\Microsoft Shared\OFFICE16\MSO.DLL
Office
Document
Document_Open
Execute
VBE7.DLL
winmgmts:\\
\root\cimv2
Win32_ProcessStartup 
winmgmts:\\
\root\cimv2:Win32_Process
powershell.exe -encoded JABmAGwAYQBnACAAPQAgACIARgBMAEEARwB7AHcAMAByAGQAIgA7ACAAJAB3AHMAaABlAGwAbAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAALQBDAG8AbQBPAGIAagBlAGMAdAAgAFcAcwBjAHIAaQBwAHQALgBTAGgAZQBsAGwAOwAgACQAdwBzAGgAZQBsAGwALgBQAG8AcAB1AHAAKAAiAEgAZQBsAGwAbwAgAFcAbwByAGwAZAAiACwAMAAsACIAOgBEACIALAAwAHgAMQApADsAIABpAHcAcgAgAGgAdAB0AHAAcwA6AC8ALwBuAHkAcABjAGcAYwBxAHUAYQBsAHMALgBjAG8AbQAvAF8AcAAwAHcAMwByADsAIAAkAHMAIAA9ACAAIgBzAGgAZQBsAGwAfQAiADsAIAAkAGEAIAA9ACAAJABzAC4AcgBlAHAAbABhAGMAZQAoACIAZQAiACwAIAAiADMAIgApAA==
Attribut
e VB_Nam
e = "Thi
sDocumen
1Normal
VGlobal!
Spac
Crea
tabl
Pre decla
BExp
Temp
lateDeri
$Custom,iz
_Open
        nd 
Publ
ic Funct
ion 
As Varia
Cons
t HIDDEN
_WINDOW
strCom
Set obj
WMIServi
GetObje
ct("winm
gmts:\\"
 & 
& "\
root\cimhv2"
@ O"
tartup
("Win3
2_Proces>sD
@Afi
@Gance_
.Show
1H^:
 "powers
hell.exe
 -encod
JABmAGwA
YQBnACAA
PQAgACIA
RgBMAEEA
RwB7AHcA
MAByAGQA0IgA7
HMAaABl
D0AIA
BOAGUAdw
AtAE8AYg
YwB0
LQBDAG8A
bQBPAGIADag
cAcwBjAH
QBwAHQA
LgBTAGgA
ZQBs
cAB1AHAA@KAAiAE
AsA!
OgBE
gAMQApPADsA
wA6AC8AL
wBuAHkA
 jAGcA
AvAF8
/zA0C4Ac
bA BhAGM
6pAA=="
, Null,AuA
X, int
DlVE
Word
Win16
Win32
Win64x
VBA6
VBA7
Project1
stdole
Project-
ThisDocument<
_Evaluate
Normal
Office
Documentj
Document_Open
ExecuteY
HIDDEN_WINDOW   n
strComputer
objWMIService
GetObjectz
objStartup
objConfigE
SpawnInstance_a
ShowWindowJk
objProcess
Create
intProcessIDH
_B_var_strComputerD
_B_var_objWMIService}G
_B_var_objStartup
_B_var_objConfig
_B_var_objProcess
_B_var_intProcessID
ID="{88B446DD-E87A-4F9B-8072-3006866CDD41}"
Document=ThisDocument/&H00000000
Name="Project"
HelpContextID="0"
VersionCompatible32="393222000"
CMG="5A58868C3A903A903A903A90"
DPB="1210CE548755875587"
GC="CAC8161CCF1DCF1D30"
[Host Extender Info]
&H00000001={3832D640-CF90-11CF-8E43-00A0C911005A};VBE;&H00000000
[Workspace]
ThisDocument=0, 0, 0, 0, C
ThisDocument
Microsoft Word 97-2003 Document
MSWordDoc
Word.Document.8

```
4. An interesting thing can be found in one of the lines

```bash
powershell.exe -encoded JABmAGwAYQBnACAAPQAgACIARgBMAEEARwB7AHcAMAByAGQAIgA7ACAAJAB3AHMAaABlAGwAbAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAALQBDAG8AbQBPAGIAagBlAGMAdAAgAFcAcwBjAHIAaQBwAHQALgBTAGgAZQBsAGwAOwAgACQAdwBzAGgAZQBsAGwALgBQAG8AcAB1AHAAKAAiAEgAZQBsAGwAbwAgAFcAbwByAGwAZAAiACwAMAAsACIAOgBEACIALAAwAHgAMQApADsAIABpAHcAcgAgAGgAdAB0AHAAcwA6AC8ALwBuAHkAcABjAGcAYwBxAHUAYQBsAHMALgBjAG8AbQAvAF8AcAAwAHcAMwByADsAIAAkAHMAIAA9ACAAIgBzAGgAZQBsAGwAfQAiADsAIAAkAGEAIAA9ACAAJABzAC4AcgBlAHAAbABhAGMAZQAoACIAZQAiACwAIAAiADMAIgApAA==
```
This looks like powershell code encoded in base64

5. Decode in base64
```bash
echo "JABmAGwAYQBnACAAPQAgACIARgBMAEEARwB7AHcAMAByAGQAIgA7ACAAJAB3AHMAaABlAGwAbAAgAD0AIABOAGUAdwAtAE8AYgBqAGUAYwB0ACAALQBDAG8AbQBPAGIAagBlAGMAdAAgAFcAcwBjAHIAaQBwAHQALgBTAGgAZQBsAGwAOwAgACQAdwBzAGgAZQBsAGwALgBQAG8AcAB1AHAAKAAiAEgAZQBsAGwAbwAgAFcAbwByAGwAZAAiACwAMAAsACIAOgBEACIALAAwAHgAMQApADsAIABpAHcAcgAgAGgAdAB0AHAAcwA6AC8ALwBuAHkAcABjAGcAYwBxAHUAYQBsAHMALgBjAG8AbQAvAF8AcAAwAHcAMwByADsAIAAkAHMAIAA9ACAAIgBzAGgAZQBsAGwAfQAiADsAIAAkAGEAIAA9ACAAJABzAC4AcgBlAHAAbABhAGMAZQAoACIAZQAiACwAIAAiADMAIgApAA==" | base64 -d
```
Output
```
$flag = "FLAG{w0rd"; $wshell = New-Object -ComObject Wscript.Shell; $wshell.Popup("Hello World",0,":D",0x1); iwr https://nypcgcquals.com/_p0w3r; $s = "shell}"; $a = $s.replace("e", "3")
```

6. Understand the powershell script <br />
The $flag variable gives the first part of the flag `FLAG{w0rd` <br />
From the next two commands gives a popup box saying hello world <br />
More information here: <br />
https://devblogs.microsoft.com/scripting/powertip-use-powershell-to-display-pop-up-window/ <br />
Next command is an invoke web request command. Since it is not hosted, running the powershell script will give us an Invoke-WebRequest error <br />
However the end of the link is interesting, which is the second part of the flag `_p0w3r` <br />
The next two commands initialised a variable s and a. A is the variable to replace the letter 'e' with '3' in s <br />
Hence the last part of the flag is `sh3ll}`

7. Piece the flag together </br>
`FLAG{w0rd_p0w3rsh3ll}`


