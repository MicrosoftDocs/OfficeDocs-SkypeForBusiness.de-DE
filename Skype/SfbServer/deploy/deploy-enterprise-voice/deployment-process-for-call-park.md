---
title: Bereitstellungsprozess für das Parken von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Bereitstellungsprozess und Schritte für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812355"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Bereitstellungsprozess für das Parken von Anrufen in Skype for Business
 
Bereitstellungsprozess und Schritte für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Durch das Parken von Anrufen kann ein Enterprise-VoIP-Benutzer einen Anruf von einem Telefon aus in die Warteschleife setzen und den Anruf später durch Wählen einer internen Nummer (auch als Orbit zum Parken von Anrufen bezeichnet) von einem beliebigen Telefon aus abrufen.
  
Die komponenten, die zum Parken von Anrufen verwendet werden, werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP. Sie müssen jedoch die folgenden Schritte ausführen, um das Parken von Anrufen zu konfigurieren, bevor es für Benutzer verfügbar ist. 
  
**Bereitstellungsprozess für die Funktion zum Parken von Anrufen**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren der Orbitbereiche zum Parken von Anrufen in der Orbittabelle  <br/> |Verwenden Sie die Skype for Business Server-Systemsteuerung oder das **Cmdlet New-CSCallParkOrbit,** um die Orbitbereiche in der Orbittabelle für das Parken von Anrufen zu erstellen und sie dem Anwendungsdienst zuzuordnen, der die Anwendung zum Parken von Anrufen hostet. <br/> **Hinweis:** Für eine nahtlose Integration in vorhandene Wählpläne werden Orbitbereiche in der Regel als Block virtueller Durchwahlen konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Konfigurieren von Einstellungen für das Parken von Anrufen  <br/> | Verwenden Sie **das Cmdlet "Set-CsCpsConfiguration",** um Einstellungen für das Parken von Anrufen zu konfigurieren. Es wird empfohlen, mindestens die Option **"OnTimeoutURI"** zu konfigurieren, um das Fallbackziel zu konfigurieren, das bei einem Zeittimeout für geparkte Anrufe verwendet werden soll. Sie können auch die folgenden Einstellungen konfigurieren: <br/>  (Optional) **EnableMusicOnHold** zum Aktivieren oder Deaktivieren von Wartemusik. <br/>  (Optional) **MaxCallPickupAttempts** zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird. <br/>  (Optional) **CallPickupTimeoutThreshold** zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Konfigurieren von Einstellungen für das Parken von Anrufen in Skype for Business](configure-call-park-settings.md) <br/> |
|Wartemusik anpassen (optional)  <br/> |Verwenden Sie das **Set-CsCallParkServiceMusicOnHoldFile**-Cmdlet zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Anpassen der Wartemusik für das Parken von Anrufen inSkype for Business](customize-call-park-music-on-hold.md) <br/> |
|Konfigurieren einer Sprachrichtlinie zum Aktivieren des Parkens von Anrufen für Benutzer  <br/> |Verwenden Sie die Skype for Business Server-Systemsteuerung oder das **Cmdlet "Set-CSVoicePolicy"** mit der Option **"EnableCallPark",** um das Parken von Anrufen für Benutzer in der Sprachrichtlinie zu aktivieren. <br/> Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert.  <br/> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft "EnableCallPark" nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Aktivieren des Parkens von Anrufen für Benutzer in Skype for Business](enable-call-park-for-users.md) <br/> |
|Überprüfen der Normalisierungsregeln für das Parken von Anrufen  <br/> |Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|Überprüfen der Bereitstellung des Parkens von Anrufen  <br/> |Testen Sie das Parken und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.  <br/> |-  <br/> |[(Optional) Überprüfen der Bereitstellung des Parkens von Anrufen in Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

