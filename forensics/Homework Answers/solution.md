# Homework Answers

**Challenge Type: Forensics**  


## Challenge
John sent me his homework answers but its not very helpful, Could he be trying a new exploit on me again D:

DISCLAIMER: Please analyze the file in your Linux Machine

## Solution
Use file command to determine what file we are working with
```bash
$ file homeans.docx
homeans.docx: Microsoft OOXML
```
There are two ways in which this can be solved, using cyberchef and python oletools

## CyberChef method

```bash

```


## Python oletools method
Github repo: https://github.com/decalage2/oletools.git </br>

First, use oleid to see if document contains VBA Macros 
```bash
$ oleid homeans.docx 
XLMMacroDeobfuscator: pywin32 is not installed (only is required if you want to use MS Excel)
oleid 0.60.1 - http://decalage.info/oletools
THIS IS WORK IN PROGRESS - Check updates regularly!
Please report any issue at https://github.com/decalage2/oletools/issues

Filename: homeans.docx
--------------------+--------------------+----------+--------------------------
Indicator           |Value               |Risk      |Description               
--------------------+--------------------+----------+--------------------------
File format         |MS Word 2007+       |info      |                          
                    |Document (.docx)    |          |                          
--------------------+--------------------+----------+--------------------------
Container format    |OpenXML             |info      |Container type            
--------------------+--------------------+----------+--------------------------
Encrypted           |False               |none      |The file is not encrypted 
--------------------+--------------------+----------+--------------------------
VBA Macros          |No                  |none      |This file does not contain
                    |                    |          |VBA macros.               
--------------------+--------------------+----------+--------------------------
XLM Macros          |No                  |none      |This file does not contain
                    |                    |          |Excel 4/XLM macros.       
--------------------+--------------------+----------+--------------------------
External            |1                   |HIGH      |External relationships    
Relationships       |                    |          |found: oleObject - use    
                    |                    |          |oleobj for details        
--------------------+--------------------+----------+--------------------------

```
What we see is that there are no vba macros, but there is an external relationships </br>
For this case, we can use oleobj

```bash
$ oleobj homeans.docx
oleobj 0.60.1 - http://decalage.info/oletools
THIS IS WORK IN PROGRESS - Check updates regularly!
Please report any issue at https://github.com/decalage2/oletools/issues

-------------------------------------------------------------------------------
File: 'homeans.docx'
Found relationship 'oleObject' with external link https://test.gabrielseet.com/office/word/2022/wordprocessingDrawing/th1s.html!
```
