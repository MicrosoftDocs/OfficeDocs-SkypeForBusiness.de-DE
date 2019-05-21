---
title: Registration-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Jeder Datensatz steht für ein Benutzer Registrierungs Ereignis.
ms.openlocfilehash: 7dcf96c5cb5b140711590943eb7ae5d2be8704b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295860"
---
# <a name="registration-table"></a>Registration-Tabelle
 
Jeder Datensatz steht für ein Benutzer Registrierungs Ereignis.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserID** <br/> |int  <br/> |Fremd  <br/> |Die Benutzer-ID. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||Eine GUID, um einen Registrierungs Endpunkt zu identifizieren. In der Regel verfügt das Register-Ereignis vom gleichen Computer desselben Benutzers über die gleiche Endpunkt-ID. Unterschiedliche Computer verfügen über eine andere Endpunkt-ID.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Die ID, mit der Registrierungen unterschieden werden, die denselben Benutzer und denselben Endpunkt einbeziehen.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Client Version des aktuellen Benutzers. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**Registrator** <br/> |int  <br/> |Fremd  <br/> |Die ID des Registrierungsservers, der für die Registrierung verwendet wird. Weitere Informationen finden Sie in der [Tabelle Server](servers.md) . <br/> |
|**Pool-Nr** <br/> |int  <br/> |Fremd  <br/> |Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle Pools](pools.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Fremd  <br/> |Edge-Server die Registrierung wird durchlaufen. Weitere Informationen finden Sie [in der Tabelle EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**"IsInternal** <br/> |Bit  <br/> ||Gibt an, ob der Benutzer intern angemeldet ist oder nicht.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Gibt an, ob die UserService verfügbar ist.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Ob Sie sich bei der primären Registrierungsstelle registrieren oder nicht.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Gibt an, ob der Benutzer bei einer Survivable Branch-Appliance registriert ist.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**Registrierung** <br/> |datetime  <br/> ||Registrierungszeit.  <br/> |
|**Registrierung** <br/> |datetime  <br/> ||Zeit für die Registrierung.  <br/> |
|**Response Code** <br/> |int  <br/> ||Antwortcode der Registrierungsanforderung.  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> ||Diagnose-ID der Registrierungsanforderung. Dies gibt an, dass der Typ der diagnostischen Informationen.  <br/> |
|**DeviceID** <br/> |int  <br/> |Fremd  <br/> |Das Gerät, von dem die Registrierungsanforderung stammt. Weitere Informationen finden Sie [in der Tabelle "Geräte" in Skype for Business Server 2015](devices.md) . <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Fremd  <br/> |Der Grund für die Deregistrierung, wie "Benutzer initiiert", "Registrierung abgelaufen", "Client Fehler" und vieles mehr. Weitere Informationen finden Sie in der Tabelle "deregistertype" [in Skype for Business Server 2015](deregistertype.md) . <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Die IP-Adresse des Endpunkts, bei dem der Benutzer registriert ist. Dies kann eine IPv4-Adresse oder eine IPv6-Adresse sein.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

