---
title: Änderungen, die von Grant-CsSetupPermission in Skype for Business Server vorgenommen werden
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
description: Zum Delegieren der Einrichtung können Sie der universellen Gruppe "RTCUniversalServerAdmins" Berechtigungen für eine bestimmte Active Directory-Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe "RTCUniversalServerAdmins" in dieser ORGANISATIONSEINHEIT Skype for Business Server in der angegebenen Domäne installieren können, ohne Mitglied der Gruppe "Domänen-Admins" zu sein.
ms.openlocfilehash: 3f6de30e7068f9f44ca6d958f8ca30af866b536a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831835"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Änderungen, die von Grant-CsSetupPermission in Skype for Business Server vorgenommen werden
 
Zum Delegieren der Einrichtung können Sie der universellen Gruppe "RTCUniversalServerAdmins" Für eine bestimmte Active Directory-Organisationseinheit (Organizational Unit, OU) Berechtigungen erteilen, sodass Mitglieder der Gruppe "RTCUniversalServerAdmins" in dieser ORGANISATIONSEINHEIT Skype for Business Server in der angegebenen Domäne installieren können, ohne Mitglied der Gruppe "Domänen-Admins" zu sein. 
  
Das **Cmdlet Grant-CsSetupPermission** gewährt der Gruppe "RTCUniversalServerAdmins" Berechtigungen für eine Organisationseinheit, wie in der folgenden Tabelle angegeben:
  
**Berechtigungen, die Objekten in der Organisationseinheit erteilt werden**

|**Berechtigungen gelten für:**|**Erteilte Berechtigungen sind:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Spezieller Zugriff: <br/>  ServicePrincipalName lesen <br/>  Write servicePrincipalName <br/>  Struktur löschen <br/>  Verzeichnisänderungen replizieren <br/> |
|Untergeordnete serviceConnectionPoint -Objekte  <br/> | Spezieller Zugriff: <br/>  Leseberechtigungen <br/>  Schreibberechtigungen <br/>  Untergeordnetes Element erstellen <br/>  Untergeordnetes Element löschen <br/>  Inhalt auflisten <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-Server-Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-WebComponents-Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-MCU-Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-MediationServer -Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-ApplicationServer -Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete msRTCSIP-ConnectionPoint-Objekte  <br/> | Spezieller Zugriff: <br/>  Eigenschaft "Write" <br/>  Eigenschaft "Read" <br/>  Struktur löschen <br/> |
|Untergeordnete Computer-Objekte  <br/> | Spezieller Zugriff für serviceConnectionPoint: <br/>  Erstellen untergeordneter Objekte <br/>  Löschen untergeordneter Objekte <br/>  Struktur löschen <br/>  Spezieller Zugriff auf öffentliche Informationen: <br/>  Eigenschaft "Read" <br/>  Spezieller Zugriff auf den DNS-Hostnamen: <br/>  Eigenschaft "Read" <br/> |
   

