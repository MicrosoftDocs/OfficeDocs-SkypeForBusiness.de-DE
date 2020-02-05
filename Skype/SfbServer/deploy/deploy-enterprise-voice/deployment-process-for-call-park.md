---
title: Bereitstellungsprozess für den Parken von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Bereitstellungsprozess und Schritte für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: e0e0559a99160bad06379751cbc0bb89fb882c20
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767478"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Bereitstellungsprozess für den Parken von Anrufen in Skype for Business
 
Bereitstellungsprozess und Schritte für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP
  
Der Anruf Park ermöglicht es einem Enterprise-VoIP-Nutzer, einen Anruf von einem Telefon aus zu halten und den Anruf später abzurufen, indem er von einem beliebigen Telefon aus eine interne Rufnummer (sog. Call Park Orbit) wählt.
  
Die Komponenten, die von Park verwendet werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Sie müssen jedoch die folgenden Schritte zum Konfigurieren des Anruf Parks verwenden, bevor er für Benutzer verfügbar ist. 
  
**Bereitstellungsprozess für die Funktion zum Parken von Anrufen**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren der Orbitbereiche zum Parken von Anrufen in der Orbittabelle  <br/> |Verwenden Sie die Skype for Business Server-Systemsteuerung oder das Cmdlet " **New-CSCallParkOrbit** ", um die Umlaufbahn Bereiche in der Orbit-Tabelle des Anruf Parks zu erstellen und Sie dem Anwendungsdienst zuzuordnen, der die Anwendung "Parken des Anrufs" hostet. <br/> **Hinweis:** Für die nahtlose Integration in vorhandene Wählpläne werden die Umlaufbahn Bereiche in der Regel als Block virtueller Erweiterungen konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Umlauf Bereichs für einen Anruf Park in Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Konfigurieren von Einstellungen für das Parken von Anrufen  <br/> | Verwenden Sie das Cmdlet " **Satz-CsCpsConfiguration** ", um die Einstellungen für den Anruf Park zu konfigurieren. Wir empfehlen, die **OnTimeoutURI** -Option so zu konfigurieren, dass das Fall Back Ziel so konfiguriert wird, dass bei einem geparkten Anruf ein Timeout festgestellt wird. Sie können auch die folgenden Einstellungen konfigurieren: <br/>  (Optional) **EnableMusicOnHold** zum Aktivieren oder Deaktivieren von Wartemusik. <br/>  (Optional) **MaxCallPickupAttempts** zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird. <br/>  (Optional) **CallPickupTimeoutThreshold** zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Konfigurieren von Einstellungen für den Anruf Park in Skype for Business](configure-call-park-settings.md) <br/> |
|Wartemusik anpassen (optional)  <br/> |Verwenden Sie das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile** zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Anpassen der Musik des Anruf Parks im Wartebereich von Skype for Business](customize-call-park-music-on-hold.md) <br/> |
|Konfigurieren der VoIP-Richtlinie zum Aktivieren des Anruf Parks für Benutzer  <br/> |Verwenden Sie die Skype for Business Server-Systemsteuerung oder das Cmdlet " **Satz-CSVoicePolicy** " mit der Option " **EnableCallPark** ", um den Anruf Park für Benutzer in der VoIP-Richtlinie zu aktivieren. <br/> Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert.  <br/> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft „EnableCallPark“ nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Aktivieren des Anruf Parks für Benutzer in Skype for Business](enable-call-park-for-users.md) <br/> |
|Überprüfen der Normalisierungsregeln für das Parken von Anrufen  <br/> |Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Überprüfen von Normalisierungsregeln für den Parken von Anrufen in Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|Überprüfen der Bereitstellung des Anruf Parks  <br/> |Testen Sie das Parken und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.  <br/> |-  <br/> |[Optional Überprüfen der Bereitstellung des Anruf Parks in Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

