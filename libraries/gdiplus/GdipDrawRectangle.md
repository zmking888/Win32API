<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : GdipDrawRectangle
Group: GDI+ Graphics - Library: gdiplus    
***  


#### Uses a pen to draw a rectangle.
***  


## Code examples:
[Custom GDI+ class](../../samples/sample_450.md)  

## Declaration:
```foxpro  
GpStatus WINGDIPAPI GdipDrawRectangle(
	GpGraphics *graphics,
	GpPen *pen,
	REAL x,
	REAL y,
	REAL width,
	REAL height
)
  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER GdipDrawRectangle IN gdiplus;
	INTEGER graphics,;
	INTEGER gdipen,;
	SINGLE  x,;
	SINGLE  y,;
	SINGLE  width,;
	SINGLE  height  
```  
***  


## Parameters:
```txt  
graphics
[in] Pointer to a Graphics object.

pen
[in] Pointer to a Pen that is used to draw the rectangle.

x
[in] Real number that specifies the x-coordinate of the upper-left corner of the rectangle.

y
[in] Real number that specifies the y-coordinate of the upper-left corner of the rectangle.

width
[in] Real number that specifies the width of the rectangle.

height
[in] Real number that specifies the height of the rectangle.  
```  
***  


## Return value:
If the method succeeds, it returns Ok (0), which is an element of the Status enumeration.  
***  


## Comments:
Create Pen object with GdipCreatePen1, GdipCreatePen2 or GdipClonePen function.  
  
***  
