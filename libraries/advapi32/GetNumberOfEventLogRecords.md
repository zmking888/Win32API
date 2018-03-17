<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : GetNumberOfEventLogRecords
Group: Event Logging - Library: advapi32    
***  


#### Retrieves the number of records in the specified event log.
***  


## Code examples:
[Reading entries from Event logs](../../samples/sample_524.md)  
[Writing entries to custom Event Log](../../samples/sample_564.md)  

## Declaration:
```foxpro  
BOOL GetNumberOfEventLogRecords(
	HANDLE hEventLog,
	PDWORD NumberOfRecords
);  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER GetNumberOfEventLogRecords IN advapi32;
	INTEGER hEventLog,;
	LONG @NumberOfRecords  
```  
***  


## Parameters:
```txt  
hEventLog
[in] A handle to the open event log. This handle is returned by the OpenEventLog or OpenBackupEventLog function.

NumberOfRecords
[out] A pointer to a variable that receives the number of records in the specified event log.  
```  
***  


## Return value:
If the function succeeds, the return value is nonzero.   
***  


## Comments:
<div class="precode">hLog = OpenEventLog(NULL, "Application")  
  
IF hLog <> 0  
	STORE 0 TO nReccount, nRecno  
  
	= GetNumberOfEventLogRecords(m.hLog, @nReccount)  
	= GetOldestEventLogRecord(m.hLog, @nRecno)  
  
	? nReccount, nRecno  
  
	= CloseEventLog(hLog)  
ENDIF  
</div>  
  
***  
