<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : GdipLoadImageFromFile
Group: GDI+ Image - Library: gdiplus    
***  


#### Creates an Image object based on a file.
***  


## Code examples:
[Custom GDI+ class](../../samples/sample_450.md)  
[Adding a background image to VFP report (VFP9, ReportListener)](../../samples/sample_562.md)  

## Declaration:
```foxpro  
GpStatus WINGDIPAPI GdipLoadImageFromFile(
	GDIPCONST WCHAR* filename,
	GpImage **image
)
  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER GdipLoadImageFromFile IN gdiplus;
	STRING    filename,;
	INTEGER @ img  
```  
***  


## Parameters:
```txt  
filename
[in] Pointer to a wide-character string that specifies the name of the file.

img
[out] Image handle.  
```  
***  


## Return value:
Returns GpStatus value, 0 means success.  
***  
