<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : JetCreateDatabase
Group: Extensible Storage Engine (ESE, Jet Blue) - Library: esent    
***  


#### Creates and attaches a database file to be used with the ESE database engine.
***  


## Code examples:
[Extensible Storage Engine class library](../../samples/sample_532.md)  

## Declaration:
```foxpro  
JET_ERR JET_API JetCreateDatabase(
  __in          JET_SESID sesid,
  __in          JET_PCSTR szFilename,
  __in_opt      JET_PCSTR szConnect,
  __out         JET_DBID* pdbid,
  __in          JET_GRBIT grbit
);  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER JetCreateDatabase IN esent;
	INTEGER sesid,;
	STRING szFilename,;
	INTEGER szConnect,;
	INTEGER @pdbid,;
	INTEGER grbit  
```  
***  


## Parameters:
```txt  
sesid
The database session context to use for the API call.

szFilename
The name of the database to be created.

szConnect
Reserved for future use. Set to NULL.

pdbid
Pointer to a buffer that, on a successful call, contains the identifier of the database. On failure, the value is undefined.

grbit
A group of bits specifying zero or more of predefined options.
  
```  
***  


## Return value:
This function returns the JET_ERR datatype with one of predefined return codes.  
***  


## Comments:
Currently, up to seven databases can be created per instance. JetCreateDatabase will implicitly open the database. It is not necessarily to subsequently call JetOpenDatabase.  
  
See also: JetAttachDatabase, JetOpenDatabase, JetCloseDatabase   
  
***  
