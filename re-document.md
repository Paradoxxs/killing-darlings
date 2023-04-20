# RE document

## Rich text file (RTF)

RTF is supported by multiple text editor, It allow attackers to embed files as OLE1 objects and other binary contents. That gets executed when the user opens the file. It an very old text format, very rarely seen today.\
It properly for the best if you block all RTF files as they are not used by anyone beside threat actor.

RTF are plaintext document with control words, groups and objects.\
Control worlds tell the text editor how the text needs be formatted and how to display the characters. Group are encloses elements inside {} delimiters and specifies the text affected by the group and its formatting, Groups can be nested. Objects are binary contents that embedded as serialized hex string.

_Example rtf_

```
{\rtf1 {object ... {\*\objdata 340004902342049200000234203420340...}} ...}
```

### tools

| tool       | description                         |
| ---------- | ----------------------------------- |
| rtfdump.py | Overview of RTF groups and objects. |

## PDF

Dump object stream to file

Another important pdf component is objects that containing a stream that, embeds other objects. This construct is called an object stream. You can use pdf-parser.py identify them using the _--type /ObjStrm_ switch. I

```
pdf-parser.py file.pdf -f -w -d 
```
