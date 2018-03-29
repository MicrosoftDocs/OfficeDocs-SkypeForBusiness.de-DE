---
title: Registration-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: Registration-Ansicht werden Informationen zur benutzerregistrierung gespeichert. Diese Ansicht wurde in Lync Server 2013 eingeführt.
ms.openlocfilehash: e116c2609f1f26268eaaa3413c3a4491da096585
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="registration-view"></a>Registration-Ansicht
 
Registration-Ansicht werden Informationen zur benutzerregistrierung gespeichert. Diese Ansicht wurde in Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Die Zeit in der Registrierung aufgetreten ist.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI der registrierten Benutzer.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Typ der URI der registrierten Benutzer. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers registriert. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers registriert sind.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner zum unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Zeitpunkt, an dem die Registrierung aufgehoben wurde.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Grund für die Aufhebung der Registrierung.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version des Client des Benutzers registriert.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Client des Benutzers registriert. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie des Clients des Benutzers registriert.  <br/> |
|**IP-Adresse** <br/> |nvarchar(256)  <br/> |IP-Adresse der Benutzer registriert sind. Dies kann eine IPv4 oder IPv6-Adresse sein.  <br/> |
|**Dialog-ID** <br/> |varstring(775)  <br/> |SIP-Dialog-ID. Das Format der ist:  <br/> Dialogfeld; aus Tag; -tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die sitzungseinladung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Diagnose-ID vom SIP-Header.  <br/> |
|**Registrierung** <br/> |nvarchar(256)  <br/> |FQDN der Registrierung.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edge-Servers, von der registrierten Benutzer.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer aus dem internen Netzwerk angemeldet.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Gibt an, ob der Benutzerdienst zum Zeitpunkt der Registrierung verfügbar war.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Gibt an, ob die Registrierung mit der primären Registrierung durchgeführt wurde.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |MAC-Adresse des registrierten Geräts.  <br/> |
|**Einträge DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Hersteller des Geräts registriert. [Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) Weitere Informationen finden Sie. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Hardwareversion des Geräts registriert. [HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) Weitere Informationen finden Sie. <br/> |
   

