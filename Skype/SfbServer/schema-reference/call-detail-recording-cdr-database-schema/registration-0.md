---
title: Registrierungs Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: In der Registrierungs Ansicht werden Informationen zur Benutzerregistrierung gespeichert. Diese Ansicht wurde in lync Server 2013 eingeführt.
ms.openlocfilehash: 0ee19d4addae9ee7318828c4ab294dc15bd72f86
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814953"
---
# <a name="registration-view"></a>Registrierungs Ansicht
 
In der Registrierungs Ansicht werden Informationen zur Benutzerregistrierung gespeichert. Diese Ansicht wurde in lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Registrierung** <br/> |datetime  <br/> |Zeitpunkt, zu dem die Registrierung erfolgte.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI des registrierten Benutzers.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des registrierten Benutzers. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des registrierten Benutzers. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, bei dem registriert ist.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner, der zur Unterscheidung von Registrierungen verwendet wird, die denselben Benutzer und denselben Endpunkt einbeziehen.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Zeitpunkt, zu dem die Registrierung erfolgte.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Grund für die Deregistrierung.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem registrierten Benutzer verwendet wurde.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Der Client, der von dem registrierten Benutzer verwendet wird. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Die Kategorie des Clients, der von dem registrierten Benutzer verwendet wird.  <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> |Die IP-Adresse, bei der der Benutzer registriert ist. Dies kann eine IPv4-oder IPv6-Adresse sein.  <br/> |
|**Dialogfeld-Nr** <br/> |varstring (775)  <br/> |SIP-Dialogfeld-ID. Das Format des is:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> |
|**Response Code** <br/> |int  <br/> |SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> |Vom SIP-Header erfasste Diagnose-ID.  <br/> |
|**Registrierungsstelle** <br/> |nvarchar(256)  <br/> |FQDN der Registrierungsstelle.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Der FQDN des Edge-Servers, der von dem registrierten Benutzer verwendet wird.  <br/> |
|**"IsInternal** <br/> |bit  <br/> |Gibt an, ob sich der Benutzer vom internen Netzwerk anmeldet.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Gibt an, ob die UserService zur Registrierungszeit verfügbar war.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Gibt an, ob die Registrierung bei der primären Registrierungsstelle erfolgte.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Mac-Adresse des registrierten Geräts.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Hersteller des registrierten Geräts. Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Hardware Version des registrierten Geräts. Weitere Informationen finden Sie [in der Tabelle HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
   

