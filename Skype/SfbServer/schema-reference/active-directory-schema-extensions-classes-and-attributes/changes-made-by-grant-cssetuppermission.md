---
title: Änderungen, die durch Grant-CsSetupPermission in Skype für Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Wenn Setup delegieren möchten, können Sie Berechtigungen gewähren der universellen Gruppe "RTCUniversalServerAdmins" für einen bestimmten Active Directory-Organisationseinheit (OU), aktivieren Mitglied der Gruppe RTCUniversalServerAdmins ist in dieser Organisationseinheit So installieren Sie Skype für Business Server in der angegebene Domäne ohne Mitglieder der Gruppe Domänen-Admins an.
ms.openlocfilehash: 6c87ad11e0c125f2a58f2518218060b2a3636f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Änderungen, die durch Grant-CsSetupPermission in Skype für Business Server
 
Wenn Setup delegieren möchten, können Sie Berechtigungen gewähren der universellen Gruppe "RTCUniversalServerAdmins" für einen bestimmten Active Directory-Organisationseinheit (OU), aktivieren Mitglied der Gruppe RTCUniversalServerAdmins ist in dieser Organisationseinheit So installieren Sie Skype für Business Server in der angegebene Domäne ohne Mitglieder der Gruppe Domänen-Admins an. 
  
Das Cmdlet **Grant-CsSetupPermission** erteilt die Gruppe RTCUniversalServerAdmins Berechtigungen in einer Organisationseinheit, wie in der folgenden Tabelle angegeben:
  
**Objekte in der Organisationseinheit erteilte Berechtigungen**

|**Berechtigungen gelten:**|**Erteilte Berechtigungen sind:**|
|:-----|:-----|
|"RTCUniversalServerAdmins"  <br/> | Beschränkter Zugriff: <br/>  ServicePrincipalName lesen <br/>  ServicePrincipalName schreiben <br/>  Struktur löschen <br/>  Verzeichnisänderungen <br/> |
|Untergeordnete ServiceConnectionPoint-Objekte  <br/> | Beschränkter Zugriff: <br/>  Leseberechtigungen <br/>  Schreibberechtigungen <br/>  Untergeordnetes Objekt erstellen <br/>  Untergeordnetes Objekt löschen <br/>  Inhalt auflisten <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-Server-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-WebComponents-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-MCU-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-MediationServer-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-ApplicationServer-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-ConnectionPoint-Objekte  <br/> | Beschränkter Zugriff: <br/>  Eigenschaft schreiben <br/>  Eigenschaft lesen <br/>  Struktur löschen <br/> |
|Untergeordnete Computer-Objekte  <br/> | Beschränkter Zugriff für ServiceConnectionPoint: <br/>  Untergeordnete Objekte erstellen <br/>  Untergeordnete Objekte löschen <br/>  Struktur löschen <br/>  Beschränkter Zugriff für Öffentliche Informationen: <br/>  Eigenschaft lesen <br/>  Beschränkter Zugriff für DNS-Hostnamen: <br/>  Eigenschaft lesen <br/> |
   

