<div align="center">

## Easy method of Writing And Reading Small Text File


</div>

### Description

Easy method of Writing And Reading Small Text Files
 
### More Info
 
In a production application, every time you want to access a file for reading or writing, you have to retrieve a free handle using the FreeFile() function to make sure that you do not overwrite an existing handle. Not only this, but you have to remember to close the file after you are done with it.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mike\-Ejeet 9t9](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mike-ejeet-9t9.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__1-1.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mike-ejeet-9t9-easy-method-of-writing-and-reading-small-text-file__1-4918/archive/master.zip)





### Source Code

```
I wrote the following two functions to go between strings and text files in my apps:
public Function ReadFile(FileName as string) as string
  Dim i as Integer
  i = FreeFile
  on error GoTo ErrorTrap
  Open FileName for input as #i
  ReadFile = input(LOF(i), i)
  Close #i
  Exit Function
ErrorTrap:
  ReadFile = ""
End Function
public Sub WriteFile(FileName as string, Contents as string)
  Dim i as Integer
  i = FreeFile
  Open FileName for Output as #i
  print #i, Contents
  Close #i
End Sub
***Once these functions are in your project, you have a quick way of reading and writing text files. For example, the following code is a weird way of copying text files:
Call WriteFile("c:\b.txt", ReadFile("c:\a.txt"))
```

