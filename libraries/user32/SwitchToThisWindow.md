<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : SwitchToThisWindow
Group: Window - Library: user32    
***  


#### The function is called to switch focus to a specified window and bring it to the foreground. 
***  


## Code examples:
[Accessing Adobe Reader 7.0 main menu from VFP application](../../samples/sample_495.md)  
[How to control Adobe Reader 9.0 (SDI mode) from VFP application](../../samples/sample_550.md)  

## Declaration:
```foxpro  
VOID SwitchToThisWindow(
	HWND hWnd,
	BOOL fAltTab
);  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE SwitchToThisWindow IN user32;
	INTEGER hWindow,;
	INTEGER fAltTab  
```  
***  


## Parameters:
```txt  
hWnd
[in] Handle to the window being switched to.

fAltTab
[in] A TRUE for this parameter indicates that the window is being switched to using the Alt/Ctl+Tab key sequence.  
```  
***  


## Return value:
None.  
***  


## Comments:
Requires Windows XP/2K. You can access this function by using LoadLibrary and GetProcAddress combined in Microsoft Windows versions prior to Windows XP.  
  
MSDN: This function is deprecated and not intended for general use. It is recommended that you do not use it in new programs because it might be altered or unavailable in subsequent versions of Windows.   
  
* * *  
To bring the FoxPro window to the front, in VFP version 7+:<code><font color=#0000a0>  
DECLARE SwitchToThisWindow IN user32;  
	INTEGER hWindow, INTEGER fAltTab  
= SwitchToThisWindow(_Screen.HWND, 0)  
</font></code>  
In older VFP versions:<code><font color=#00a000>  
* save the value on app start<font color=#0000a0>  
DECLARE INTEGER GetActiveWindow IN user32  
hScreen = GetActiveWindow()<font color=#00a000>  
* ... later ...<font color=#0000a0>  
DECLARE SwitchToThisWindow IN user32;  
	INTEGER hWindow, INTEGER fAltTab  
= SwitchToThisWindow(m.hScreen, 0)  
</font></code>  
  
***  
