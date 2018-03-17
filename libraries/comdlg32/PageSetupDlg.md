<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : PageSetupDlg
Group: Common Dialog Box - Library: comdlg32    
***  


#### The PageSetupDlg function creates a Page Setup dialog box that enables the user to specify the attributes of a printed page.
***  


## Code examples:
[Opening the Page Setup dialog box to specify the attributes of a printed page](../../samples/sample_272.md)  

## Declaration:
```foxpro  
BOOL PageSetupDlg(
  LPPAGESETUPDLG lppsd  // initialization data
);  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER PageSetupDlg IN comdlg32;
	STRING @lppsd  
```  
***  


## Parameters:
```txt  
lppsd
[in/out] Pointer to a PAGESETUPDLG structure that contains information used to initialize the dialog box.  
```  
***  


## Return value:
If the user clicks the OK button, the return value is nonzero. The members of the PAGESETUPDLG structure pointed to by the lppsd parameter indicate the user"s selections.

If the user cancels or closes the Page Setup dialog box or an error occurs, the return value is zero. To get extended error information, use the CommDlgExtendedError function.  
***  


## Comments:
The PSD_RETURNDEFAULT flag allows to retrieve the printer page parameters for the default printer (including its name) without displaying the dialog box.  
  
***  
