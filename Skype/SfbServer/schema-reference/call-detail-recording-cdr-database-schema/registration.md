---
title: Registrierungstabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.
ms.openlocfilehash: 1ab9c4b80d7bdbbc379c202978d7639e286128fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823115"
---
# <a name="registration-table"></a>Registrierungstabelle
 
Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Fremd  <br/> |Die Benutzer-ID. Weitere Informationen [finden Sie in der Tabelle](users.md) "Benutzer". <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||Eine GUID (Globally Unique Identifier) zur Kennzeichnung eines Registrierungsendpunkts. In der Regel hat jedes Registrierungsereignis vom gleichen Computer des gleichen Benutzers die gleiche Endpunkt-ID. Verschiedene Computer haben unterschiedliche Endpunkt-IDs.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID zum Unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Die Clientversion des aktuellen Benutzers. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**RegistrarId** <br/> |int  <br/> |Fremd  <br/> |Die ID des Registrierungsservers, der für die Registrierung verwendet wird. Weitere Informationen [finden Sie in der Tabelle "Server".](servers.md) <br/> |
|**PoolId** <br/> |int  <br/> |Fremd  <br/> |ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen [finden Sie in der Tabelle "Pools".](pools.md) <br/> |
|**EdgeServerId** <br/> |int  <br/> |Fremd  <br/> |Der Edgeserver, über den die Registrierung läuft. Weitere Informationen finden Sie in der [Tabelle "EdgeServers" in Skype for Business Server 2015.](edgeservers.md) <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Ob der Benutzer von innerhalb angemeldet ist oder nicht.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Ob der Benutzerdienst verfügbar ist oder nicht.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Ob die Registrierung bei der primären Registrierung erfolgt oder nicht.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Gibt an, ob der Benutzer mit einer Survivable Branch Appliance registriert ist.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RegisterTime** <br/> |Datum/Uhrzeit  <br/> ||Der Zeitpunkt der Registrierung.  <br/> |
|**DeRegisterTime** <br/> |Datum/Uhrzeit  <br/> ||Der Zeitpunkt der Aufhebung der Registrierung.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Der Antwortcode der Registrierungsanforderung.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Die Diagnose-ID der Registrierungsanforderung. Diese gibt den Diagnoseinformationstyp an.  <br/> |
|**DeviceId** <br/> |int  <br/> |Fremd  <br/> |Das Gerät, von dem die Registrierungsanforderung stammt. Weitere Informationen [finden Sie in der Tabelle "Geräte" in Skype for Business Server 2015.](devices.md) <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Fremd  <br/> |Der Grund für die Deregistrierung, z. B. "Benutzer initiiert", "Registrierung abgelaufen", "Client-Fehler" und vieles mehr. Weitere Informationen finden Sie in der [Tabelle "DeRegisterType" in Skype for Business Server 2015.](deregistertype.md) <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||IP-Adresse des Endpunkts, mit dem sich der Benutzer registriert hat. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

