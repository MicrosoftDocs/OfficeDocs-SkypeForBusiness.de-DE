---
title: Registrierungsansicht
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: In der Registrierungsansicht werden Informationen zur Benutzerregistrierung gespeichert. Diese Ansicht wurde in Lync Server 2013 eingeführt.
---

# <a name="registration-view"></a>Registrierungsansicht
 
In der Registrierungsansicht werden Informationen zur Benutzerregistrierung gespeichert. Diese Ansicht wurde in Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**RegisterTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem die Registrierung erfolgte.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der sich registriert hat.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |URI-Typ des registrierten Benutzers. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der sich registriert hat. Weitere Informationen finden Sie in der [Tabelle "Mandanten](tenants.md) ". <br/> |
|**EndpointId** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des registrierten Benutzers.  <br/> |
|**EndpointEra** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner, der verwendet wird, um Registrierungen zu unterscheiden, die denselben Benutzer und denselben Endpunkt betreffen.  <br/> |
|**DeRegisterType** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem die Dereferenzierung erfolgte.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Grund für die Dereferenzierung.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die von dem Benutzer verwendet wird, der sich registriert hat.  <br/> |
|**ClientType** <br/> |int  <br/> |Client, der von dem Benutzer verwendet wird, der sich registriert hat. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie des Clients, der vom registrierten Benutzer verwendet wird.  <br/> |
|**Ipaddress** <br/> |nvarchar(256)  <br/> |IP-Adresse, mit der der Benutzer registriert wurde. Dies kann eine IPv4- oder IPv6-Adresse sein.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP-Dialog-ID. Das Format von "the" lautet wie folgt:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Vom SIP-Header erfasste Diagnose-ID.  <br/> |
|**Registrar** <br/> |nvarchar(256)  <br/> |FQDN der Registrierungsstelle.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edgeservers, der vom registrierten Benutzer verwendet wird.  <br/> |
|**IsInternal** <br/> |Bit  <br/> |Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.  <br/> |
|**IsUserServiceAvailable** <br/> |Bit  <br/> |Gibt an, ob userService zur Registrierungszeit verfügbar war.  <br/> |
|**IsPrimaryRegistrar** <br/> |Bit  <br/> |Gibt an, ob die Registrierung bei der primären Registrierungsstelle erfolgt ist.  <br/> |
|**DeviceMacAddress** <br/> |Bigint  <br/> |MAC-Adresse des registrierten Geräts.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Hersteller des registrierten Geräts. Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md). <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Hardwareversion des registrierten Geräts. Weitere Informationen finden Sie [in der Tabelle "HardwareVersions" in Skype for Business Server 2015](hardwareversions.md). <br/> |
   

