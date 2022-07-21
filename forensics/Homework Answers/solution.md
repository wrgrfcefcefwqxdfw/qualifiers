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
Github repo: https://github.com/decalage2/oletools.git

```bash
$ oleobj homeans.docx
oleobj 0.60.1 - http://decalage.info/oletools
THIS IS WORK IN PROGRESS - Check updates regularly!
Please report any issue at https://github.com/decalage2/oletools/issues

-------------------------------------------------------------------------------
File: 'homeans.docx'
Found relationship 'oleObject' with external link https://test.gabrielseet.com/office/word/2022/wordprocessingDrawing/th1s.html!
```
