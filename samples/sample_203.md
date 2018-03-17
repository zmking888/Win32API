<link rel="stylesheet" type="text/css" href="../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

# Drawing cursors for the classes defined by the system (preregistered): BUTTON, EDIT, LISTBOX etc.

## Code:
```foxpro  
DO decl

= DrawClassCursor ("Button",    100)
= DrawClassCursor ("ComboBox",  140)
= DrawClassCursor ("Edit",      180)
= DrawClassCursor ("ListBox",   220)
= DrawClassCursor ("MDIClient", 260)
= DrawClassCursor ("ScrollBar", 300)
= DrawClassCursor ("Static",    340)

PROCEDURE  DrawClassCursor (lcClassName, Y)
	LOCAL hwnd, hdc, lcWndClass, hCursor
	hwnd = GetActiveWindow()
	hdc = GetWindowDC(hwnd)

	#DEFINE WNDCLASS_SIZE  40
	lcWndClass = Repli(Chr(0), WNDCLASS_SIZE)
	= GetClassInfo (0, lcClassName, @lcWndClass)

	* drawing the cursor on the main VFP window
	hCursor = buf2dword(SUBSTR(lcWndClass, 25,4))
	IF hCursor <> 0
		= DrawIcon (hdc, 40,Y, hCursor)
	ENDIF

	ReleaseDC (hwnd, hdc)
RETURN

FUNCTION  buf2dword (lcBuffer)
RETURN Asc(SUBSTR(lcBuffer, 1,1)) + ;
	Asc(SUBSTR(lcBuffer, 2,1)) * 256 +;
	Asc(SUBSTR(lcBuffer, 3,1)) * 65536 +;
	Asc(SUBSTR(lcBuffer, 4,1)) * 16777216

PROCEDURE  decl
	DECLARE INTEGER GetActiveWindow IN user32
	DECLARE INTEGER GetWindowDC IN user32 INTEGER hwnd
	DECLARE INTEGER ReleaseDC IN user32 INTEGER hwnd, INTEGER hdc

	DECLARE INTEGER GetClassInfo IN user32;
		INTEGER hInstance, STRING lpClassName, STRING @lpWndClass

	DECLARE SHORT DrawIcon IN user32;
		INTEGER hDC, INTEGER X, INTEGER Y, INTEGER hIcon  
```  
***  


## Listed functions:
[DrawIcon](../libraries/user32/DrawIcon.md)  
[GetActiveWindow](../libraries/user32/GetActiveWindow.md)  
[GetClassInfo](../libraries/user32/GetClassInfo.md)  
[GetWindowDC](../libraries/user32/GetWindowDC.md)  
[ReleaseDC](../libraries/user32/ReleaseDC.md)  

## Comment:
Some info on <A Href="http://msdn.microsoft.com/library/default.asp?url=/library/en-us/winui/winclass_4lv7.asp">System Classes</A>.  
  
***  
