---
title: Von Grant-CsSetupPermission in Skype for Business Server vorgenommene Änderungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Zum Delegieren des Setups können Sie der universellen Gruppe "RTCUniversalServerAdmins" Berechtigungen für eine bestimmte Active Directory-Organisationseinheit (OU) erteilen, sodass Mitglieder der Gruppe "RTCUniversalServerAdmins" in dieser OU Skype for Business Server in der angegebenen Domäne installieren können, ohne Mitglieder der Gruppe "Domänenadministratoren" zu sein.
ms.openlocfilehash: 32c0d48c5b6c63a38ff48e7808b8009c3ef265e6f0b6eb739094f797e47ace4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349707"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Von Grant-CsSetupPermission in Skype for Business Server vorgenommene Änderungen
 
Zum Delegieren des Setups können Sie der universellen Gruppe "RTCUniversalServerAdmins" Berechtigungen für eine bestimmte Active Directory-Organisationseinheit (OU) erteilen, sodass Mitglieder der Gruppe "RTCUniversalServerAdmins" in dieser OU Skype for Business Server in der angegebenen Domäne installieren können, ohne Mitglieder der Gruppe "Domänenadministratoren" zu sein. 
  
Das Cmdlet **"Grant-CsSetupPermission"** gewährt der Gruppe "RTCUniversalServerAdmins" Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:
  
**Berechtigungen, die Objekten in der OU erteilt werden**

|**Berechtigungen gelten für:**|**Erteilte Berechtigungen sind:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Spezieller Zugriff: <br/>  ServicePrincipalName lesen <br/>  servicePrincipalName schreiben <br/>  Struktur löschen <br/>  Verzeichnisänderungen replizieren <br/> |
|Untergeordnete serviceConnectionPoint-Objekte  <br/> | Spezieller Zugriff: <br/>  Leseberechtigungen <br/>  Schreibberechtigungen <br/>  Untergeordnetes Element erstellen <br/>  Untergeordnetes Element löschen <br/>  Inhalt auflisten <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-Server-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-WebComponents-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-MCU-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-MediationServer-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete MsRTCSIP-ApplicationServer-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-ConnectionPoint-Objekte  <br/> | Spezieller Zugriff: <br/>  Write-Eigenschaft <br/>  Read-Eigenschaft <br/>  Struktur löschen <br/> |
|Untergeordnete Computer-Objekte  <br/> | Spezieller Zugriff für serviceConnectionPoint: <br/>  Erstellen untergeordneter Objekte <br/>  Löschen untergeordneter Objekte <br/>  Struktur löschen <br/>  Spezieller Zugriff für öffentliche Informationen: <br/>  Read-Eigenschaft <br/>  Spezieller Zugriff für DNS-Hostname: <br/>  Read-Eigenschaft <br/> |
   

