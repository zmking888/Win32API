[<img src="../images/home.png"> Home ](https://github.com/VFPX/Win32API)  

# Obtaining provider name for a specific type of network

## Code:
```foxpro  
DECLARE INTEGER WNetGetProviderName IN mpr;
	INTEGER dwNetType, STRING @lpProviderName,;
	INTEGER @lpBufferSize

#DEFINE NO_ERROR 0

#DEFINE WNNC_NET_MSNET      0x00010000
#DEFINE WNNC_NET_LANMAN     0x00020000
#DEFINE WNNC_NET_NETWARE    0x00030000
#DEFINE WNNC_NET_VINES      0x00040000
#DEFINE WNNC_NET_10NET      0x00050000
#DEFINE WNNC_NET_LOCUS      0x00060000
#DEFINE WNNC_NET_SUN_PC_NFS 0x00070000
#DEFINE WNNC_NET_LANSTEP    0x00080000
#DEFINE WNNC_NET_9TILES     0x00090000
#DEFINE WNNC_NET_LANTASTIC  0x000A0000
#DEFINE WNNC_NET_AS400      0x000B0000
#DEFINE WNNC_NET_FTP_NFS    0x000C0000
#DEFINE WNNC_NET_PATHWORKS  0x000D0000
#DEFINE WNNC_NET_LIFENET    0x000E0000
#DEFINE WNNC_NET_POWERLAN   0x000F0000
#DEFINE WNNC_NET_BWNFS      0x00100000
#DEFINE WNNC_NET_COGENT     0x00110000
#DEFINE WNNC_NET_FARALLON   0x00120000
#DEFINE WNNC_NET_APPLETALK  0x00130000
#DEFINE WNNC_NET_INTERGRAPH 0x00140000
#DEFINE WNNC_NET_SYMFONET   0x00150000
#DEFINE WNNC_NET_CLEARCASE  0x00160000
#DEFINE WNNC_NET_FRONTIER   0x00170000
#DEFINE WNNC_NET_BMC        0x00180000
#DEFINE WNNC_NET_DCE        0x00190000
#DEFINE WNNC_NET_DECORB     0x00200000
#DEFINE WNNC_NET_PROTSTOR   0x00210000
#DEFINE WNNC_NET_FJ_REDIR   0x00220000
#DEFINE WNNC_NET_DISTINCT   0x00230000
#DEFINE WNNC_NET_TWINS      0x00240000
#DEFINE WNNC_NET_RDR2SAMPLE 0x00250000

LOCAL lcProvider, lnBufsize, lnResult
lnBufsize = 250
lcProvider = Repli(Chr(0), lnBufsize)

lnResult = WNetGetProviderName (WNNC_NET_MSNET, @lcProvider, @lnBufsize)
IF lnResult = NO_ERROR
	? "Provider name:", SUBSTR(lcProvider, 1, AT(Chr(0),lcProvider)-1)
ELSE
* 1222 -- ERROR_NO_NETWORK
*  234 -- ERROR_MORE_DATA
	? "Error code:", lnResult
ENDIF  
```  
***  


## Listed functions:
[WNetGetProviderName](../libraries/mpr/WNetGetProviderName.md)  
