---
title: Registration-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Jeder Datensatz stellt ein benutzerregistrierungsereignis dar.
ms.openlocfilehash: 1dd8f623799753e078d112d08de960076618dfac
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212845"
---
# <a name="registration-table"></a>Registration-Tabelle
 
Jeder Datensatz stellt ein benutzerregistrierungsereignis dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Ausländisch  <br/> |Die Benutzer-ID. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||Eine GUID zum Identifizieren eines Endpunkts Registrierung. Das Register-Ereignis aus dem gleichen Computer derselbe Benutzer wird in der Regel die gleiche Endpunkt-ID besitzen. Andere Computer verfügen, eine anderen Endpunkt-ID.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID zum unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Client-Version des aktuellen Benutzers. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**RegistrarId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Registrar-Servers für die Registrierung verwendet. Finden Sie weitere Informationen der [Server-Tabelle](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in der die Sitzung erfasst wurde. Finden Sie weitere Informationen der [Pools-Tabelle](pools.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Ausländisch  <br/> |Edge-Server die Registrierung wird durchgehen. [EdgeServers-Tabelle in Skype für Business Server 2015](edgeservers.md) Weitere Informationen finden Sie. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Gibt an, ob der Benutzer von innerhalb oder nicht angemeldet ist.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Gibt an, ob der Benutzerdienst verfügbar ist.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Gibt an, ob mit der primären Registrierung registrieren Sie oder nicht.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Gibt an, ob der Benutzer mit einer survivable Branch Appliance registriert ist.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Zeitpunkt der Registrierung.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Aufheben der Registrierung Zeit.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Der Antwortcode der registrierungsanforderung.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Diagnose-ID der registrierungsanforderung. Dies gibt dieses Typs Diagnoseinformationen an.  <br/> |
|**Geräte-ID** <br/> |int  <br/> |Ausländisch  <br/> |Das Gerät, dem die Register-Anforderung stammt. [Devices-Tabelle in Skype für Business Server 2015](devices.md) Weitere Informationen finden Sie. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Ausländisch  <br/> |Der Grund des De-register, beispielsweise 'Benutzer initiiert', 'Registrierung abgelaufen', 'Client Fail' und mehr. Finden Sie unter der [DeRegisterType-Tabelle in Skype für Business Server 2015](deregistertype.md) für Weitere Informationen. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||IP-Adresse des Endpunkts der Benutzer registriert sind. Dies kann eine IPv4-Adresse oder eine IPv6-Adresse sein.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

