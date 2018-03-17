<link rel="stylesheet" type="text/css" href="../../css/win32api.css">  
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

## Functionname : PlaySound
Group: Windows Multimedia - Library: winmm    
***  


#### Plays a sound specified by the given file name, resource, or system event.
***  


## Code examples:
[Playing WAV files on InteractiveChange](../../samples/sample_594.md)  

## Declaration:
```foxpro  
BOOL PlaySound(
	LPCTSTR pszSound,
	HMODULE hmod,
	DWORD fdwSound
);  
```  
***  


## FoxPro declaration:
```foxpro  
DECLARE INTEGER PlaySound IN winmm;
	STRING pszSound,;
	INTEGER hmod,;
	LONG fdwSound  
```  
***  


## Parameters:
```txt  
pszSound
A string that specifies the sound to play. The maximum length, including the null terminator, is 256 characters.

hmod
Handle to the executable file that contains the resource to be loaded. This parameter must be NULL unless SND_RESOURCE is specified in fdwSound.

fdwSound
Flags for playing the sound.
  
```  
***  


## Return value:
Returns TRUE if successful or FALSE otherwise.  
***  


## Comments:
For playing system sounds rather than sounds stored in WAV files, it is better to declare this function as follows:  
<div class="precode">DECLARE INTEGER PlaySound IN winmm;  
	LONG pszSound, INTEGER hmod, LONG fdwSound  
</div>  
Below is FoxPro equivalent to sndAlias("S", "W") macro (SND_ALIAS_SYSTEMWELCOME) :  
<div class="precode">nSoundId = BITOR(buf2dword(PADR("S",4,CHR(0))),;  
	BITLSHIFT(buf2dword(PADR("W",4,CHR(0))),8)) <span style="color: green;">&& returns 22355</span>  
</div>  
This will play the SND_ALIAS_SYSTEMWELCOME sound:  
<div class="precode">= PlaySound(22355, 0, BITOR(SND_ALIAS_ID, SND_ASYNC))  
</div>  
See also: sndPlaySound   
  
***  
