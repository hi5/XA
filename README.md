# XA - Save/Load AutoHotkey Arrays in XML format

**Introduction**

XA was written by **trueski** and the original source can be found here http://www.autohotkey.com/board/topic/85461-ahk-l-saveload-arrays/  
(The code posted there is no longer valid due to errors caused by upgrading the forum software.)

* XA_CleanInvalidChars() has been added to remove invalid characters in XML.
* Note this is for **AutoHotkey UNICODE only**
* A XA version compatible with AHK v2 can be found here https://www.autohotkey.com/boards/viewtopic.php?f=6&t=72997 

## Usage

```ahk
    XA_Save("Array", Path) ; put variable name in quotes
    XA_Load(Path)          ; the name of the variable containing the array is returned
```

```autohotkey
MyArray1:={"a":"aa","b":"bb","c":"cc"}
MyArray2:=["a","b","c"]

XA_Save("MyArray1", "test1.xml" ) ; see 1 below
XA_Save("MyArray2", "test2.xml" ) ; see 2 below
```

result of test1
```xml
<?xml version="1.0" encoding="UTF-8"?>
<MyArray1>
	<a>aa</a>
	<b>bb</b>
	<c>cc</c>
</MyArray1>
```

result of test2
```xml
<?xml version="1.0" encoding="UTF-8"?>
<MyArray2>
	<Invalid_Name id="1" ahk="True">a</Invalid_Name>
	<Invalid_Name id="2" ahk="True">b</Invalid_Name>
	<Invalid_Name id="3" ahk="True">c</Invalid_Name>
</MyArray2>
```


### AutoHotkey forum discussion

https://autohotkey.com/boards/viewtopic.php?f=6&t=34849
