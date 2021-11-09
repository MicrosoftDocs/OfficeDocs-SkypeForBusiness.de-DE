---
title: Registrierungstabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.
ms.openlocfilehash: 45aa007b242d2a85aa8f19f35571fc367e298433
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859812"
---
# <a name="registration-table"></a>Registrierungstabelle
 
Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Ausländisch  <br/> |Die Benutzer-ID. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**EndpointId** <br/> |Uniqueidentifier  <br/> ||Eine GUID (Globally Unique Identifier) zur Kennzeichnung eines Registrierungsendpunkts. In der Regel hat jedes Registrierungsereignis vom gleichen Computer des gleichen Benutzers die gleiche Endpunkt-ID. Verschiedene Computer haben unterschiedliche Endpunkt-IDs.  <br/> |
|**EndpointEra** <br/> |Uniqueidentifier  <br/> ||ID zum Unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Die Clientversion des aktuellen Benutzers. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**RegistrarId** <br/> |int  <br/> |Ausländisch  <br/> |Die ID des Registrierungsservers, der für die Registrierung verwendet wird. Weitere Informationen finden Sie in der [Tabelle "Server".](servers.md) <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle "Pools".](pools.md) <br/> |
|**EdgeServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der Edgeserver, über den die Registrierung läuft. Weitere Informationen finden Sie in der [EdgeServers-Tabelle in Skype for Business Server 2015.](edgeservers.md) <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Ob der Benutzer von innerhalb angemeldet ist oder nicht.  <br/> |
|**IsUserServiceAvailable** <br/> |Bit  <br/> ||Ob der Benutzerdienst verfügbar ist oder nicht.  <br/> |
|**IsPrimaryRegistrar** <br/> |Bit  <br/> ||Ob die Registrierung bei der primären Registrierung erfolgt oder nicht.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |Bit  <br/> ||Gibt an, ob der Benutzer mit einer Survivable Branch Appliance registriert ist.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RegisterTime** <br/> |Datum/Uhrzeit  <br/> ||Der Zeitpunkt der Registrierung.  <br/> |
|**DeRegisterTime** <br/> |Datum/Uhrzeit  <br/> ||Der Zeitpunkt der Aufhebung der Registrierung.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Der Antwortcode der Registrierungsanforderung.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Die Diagnose-ID der Registrierungsanforderung. Diese gibt den Diagnoseinformationstyp an.  <br/> |
|**Deviceid** <br/> |int  <br/> |Ausländisch  <br/> |Das Gerät, von dem die Registrierungsanforderung stammt. Weitere Informationen finden Sie in der [Tabelle "Geräte" in Skype for Business Server 2015.](devices.md) <br/> |
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |Ausländisch  <br/> |Der Grund für die Aufhebung der Registrierung, z. B. "Vom Benutzer initiiert", "Registrierung abgelaufen", "Clientfehler" und vieles mehr. Weitere Informationen finden Sie in der [Tabelle "DeRegisterType" in Skype for Business Server 2015.](deregistertype.md) <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||IP-Adresse des Endpunkts, mit dem sich der Benutzer registriert hat. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

