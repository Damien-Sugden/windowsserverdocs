---
title: Ipxroute
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3a30304f-655e-43d2-a4ac-7568abf8975c
author: jaimeo
---
# Ipxroute
Displays and modifies information about the routing tables used by the IPX protocol. Used without parameters,  **ipxroute** displays the default settings for packets that are sent to unknown, broadcast, and multicast addresses. For examples of how this command can be used, see [Examples](assetId:///c6d43992-8243-4f0a-8605-3152c8a8fe9a#BKMK_Examples).  
  
## Syntax  
  
```  
ipxroute servers [/type=X]  
ipxroute ripout <Network>  
ipxroute resolve {guid | name} {GUID | <AdapterName>}  
ipxroute board= N [def] [gbr] [mbr] [remove=xxxxxxxxxxxx]  
ipxroute config  
```  
  
### Parameters  
  
|Parameter|Description|  
|-------------|---------------|  
|servers\[ \/type\=X\]|Displays the Service Access Point \(SAP\) table for the specified server type.  **X** must be an integer. For example, **\/type\=4** displays all file servers. If you do not specify **\/type**, **ipxroute servers** displays all types of servers, listing them by server name.|  
|ripout Network|Discovers if *Network* is reachable by consulting the IPX stack's route table and sending out a rip request if necessary.  *Network* is the IPX network segment number.|  
|resolve{ GUID&#124; name} { GUID&#124; AdapterName}|Resolves the name of the GUID to its friendly name, or the friendly name to its GUID.|  
|board\= *N*|Specifies the network adapter for which to query or set parameters.|  
|def|Sends packets to the ALL ROUTES broadcast. If a packet is transmitted to a unique Media Access Card \(MAC\) address that is not in the source routing table, **ipxroute** sends the packet to the SINGLE ROUTES broadcast by default.|  
|gbr|Sends packets to the ALL ROUTES broadcast. If a packet is transmitted to the broadcast address \(FFFFFFFFFFFF\), **ipxroute** sends the packet to the SINGLE ROUTES broadcast by default.|  
|mbr|Sends packets to the ALL ROUTES broadcast. If a packet is transmitted to a multicast address \(C000xxxxxxxx\), **ipxroute** sends the packet to the SINGLE ROUTES broadcast by default.|  
|remove\= *xxxxxxxxxxxx*|Removes the given node address from the source routing table.|  
|config|Displays information about all of the bindings for which IPX is configured.|  
|\/?|Displays help at the command prompt.|  
  
## <a name="BKMK_Examples"></a>Examples  
To display the network segments that the workstation is attached to, the workstation node address, and frame type being used, type:  
  
```  
ipxroute config  
```  
  
## Additional references  
  
-   [Command-Line Syntax Key](Command-Line-Syntax-Key.md)  
  
