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

I saw an article on how you can use cyberchef to extract URLs from it</br>
https://isc.sans.edu/diary/CyberChef%3A+Analyzing+OOXML+Files+for+URLs/27020</br>
The original cyberchef recipe is this: </br></br>
https://gchq.github.io/CyberChef/#recipe=Unzip('',false)Extract_URLs(false,false,false)Filter('Line%20feed','http://schemas%5C%5C.openxmlformats%5C%5C.org/',true)Filter('Line%20feed','http://schemas%5C%5C.microsoft%5C%5C.com/',true)Filter('Line%20feed','http://purl%5C%5C.org/',true)Filter('Line%20feed','http://www%5C%5C.w3%5C%5C.org/',true)Defang_URL(true,true,true,'Valid%20domains%20and%20full%20URLs')</br>
but I found that the defang thing at the end is not needed.

What it does is that it unzip the OOXML file, because OOXML are zip file containers, then you extract all the urls from the embeded files. The filtering is used to filter out all the https://schemas and other links that we may not need. </br>
By using the recipe, we extracted an URL from the OOXML file. </br>
https://test.gabrielseet.com/office/word/2022/wordprocessingDrawing/th1s.html


## Python oletools method
Github repo: https://github.com/decalage2/oletools.git </br>

First, use oleid. From its help page, it is said that oleid is used to analyze OLE files such as MS Office documents (e.g. Word, Excel), to detect specific characteristics that could potentially indicate that the file is suspicious or malicious, in terms of security (e.g. malware). or example it can detect VBA macros, embedded Flash objects, fragmentation. The results is displayed as ascii table (but could be returned or printed in other formats like CSV, XML or JSON
in future).
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
What we see is that there are no vba macros, which is usually the case, but there is an external relationship found. </br>
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
Here we can see that the document has a relationship with a external link, which is bad as this could invoke malicious code. But in this case, it could be our flag. </br>
https://test.gabrielseet.com/office/word/2022/wordprocessingDrawing/th1s.html </br>

## How to get the flag
Since the link is not hosted, you need to open a ticket with the boss</br>
