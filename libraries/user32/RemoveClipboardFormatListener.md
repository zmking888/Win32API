<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : RemoveClipboardFormatListener
Group: Clipboard - Library: user32    
***  


#### Removes the given window from the system-maintained clipboard format listener list.
***  


## Code examples:
[Monitoring clipboard content changes (VFP9)](../../samples/sample_601.md)  

## Declaration:
```foxpro  
BOOL WINAPI RemoveClipboardFormatListener(
  _In_  HWND hwnd
);
  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER RemoveClipboardFormatListener IN user32;
	INTEGER hWindow  
```  
***  


## Parameters:
```txt  
hwnd [in]
Type: HWND
A handle to the window to remove from the clipboard format listener list.  
```  
***  


## Return value:
Returns TRUE if successful, FALSE otherwise. Call GetLastError for additional details.  
***  


## Comments:
When a window has been removed from the clipboard format listener list, it will no longer receive WM_CLIPBOARDUPDATE (0x031D) messages.  
  
See also: AddClipboardFormatListener, ChangeClipboardChain, SetClipboardViewer   
  
***  
