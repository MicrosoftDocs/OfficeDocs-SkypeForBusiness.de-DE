---
title: Bereitstellungsprozess für die Funktion zum Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Bereitstellungsprozess und Schritte für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d7bc57664b7f6880cde7481c3ba5aff97c2d4392
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Bereitstellungsprozess für die Funktion zum Parken von Anrufen in Skype for Business 2015
 
Bereitstellungsprozess und Schritte für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
  
Anruf Parken können einen Enterprise-VoIP-Benutzer einen Anruf von einem Telefon halten und anschließendes entgegennehmen des Anrufs später durch Wählen einer internen Nummer (auch bekannt als eine Orbit zum Parken von Anrufen) von jedem Telefon aus.
  
Die Komponenten, die zum Parken von Anrufen verwendet sind automatisch installiert und bei der Bereitstellung von Enterprise-VoIP auf dem Front-End-Server oder Standard Edition-Server aktiviert. Allerdings müssen Sie die folgenden Schritte verwenden, Parken von Anrufen zu konfigurieren, bevor es für Benutzer verfügbar ist. 
  
**Bereitstellungsprozess für das Parken von Anrufen**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Dokumentation zur Bereitstellung**|
|:-----|:-----|:-----|:-----|
|Konfigurieren der Orbitbereiche zum Parken von Anrufen in der Orbittabelle  <br/> |Verwenden Sie Skype für Business Server-Systemsteuerung oder das Cmdlet **New-CSCallParkOrbit** die orbitbereiche in der orbittabelle für das Parken von Anrufen erstellen und zuordnen, den Anwendungsdienst, der als Host der Anwendung zum Parken. <br/> **Hinweis:** Für die nahtlose Integration mit vorhandenen Wählpläne werden die orbitbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt. <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> CsServerAdministrator  <br/> "Csadministrator"  <br/> |[Erstellen Sie oder ändern Sie einen orbitbereich zum Parken von Anrufen in Skype für Business 2015](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Konfigurieren von Einstellungen für das Parken von Anrufen  <br/> | Verwenden Sie das Cmdlet **Set-CsCpsConfiguration** , um Einstellungen für das Parken von Anrufen zu konfigurieren. Mindestens wird empfohlen, dass Sie die Option **Fallbackziel** so konfigurieren Sie ontimeouturi zu verwenden, wenn ein Timeout für ein geparkter Anruf konfigurieren. Sie können auch die folgenden Einstellungen konfigurieren: <br/>  (Optional) **EnableMusicOnHold** zum Aktivieren oder deaktivieren die Musik in der Warteschleife. <br/>  (Optional) **MaxCallPickupAttempts** wie oft einen geparkten Anruf klingelt antwortenden Telefon ermittelt, bevor der Aufruf an den fallback URI Uniform Resource Identifier () weitergeleitet. <br/>  (Optional) **CallPickupTimeoutThreshold** bestimmt die Zeitspanne, die verstreicht, nachdem Sie ein Anruf geparkt wurde, bevor es wieder auf das Telefon klingelt, in dem der Anruf entgegengenommen wurde. <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> CsServerAdministrator  <br/> "Csadministrator"  <br/> |[Konfigurieren von Einstellungen für das Parken von Anrufen in Skype für Business 2015](configure-call-park-settings.md) <br/> |
|Wartemusik anpassen (optional)  <br/> |Verwenden Sie das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile** zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige wartemusik verwenden möchten, halten. <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> CsServerAdministrator  <br/> "Csadministrator"  <br/> |[Anpassen des Parkens von Anrufen Musik in der Warteschleife InSkype für Business 2015](customize-call-park-music-on-hold.md) <br/> |
|Konfigurieren von VoIP-Richtlinie zum Parken von Anrufen für Benutzer aktivieren  <br/> |Verwenden Sie Skype für Business Server-Systemsteuerung oder **Set-CSVoicePolicy** -Cmdlet mit der Option **EnableCallPark** , um das Parken von Anrufen für Benutzer in VoIP-Richtlinie zu aktivieren. <br/> Parken von Anrufen ist standardmäßig für alle Benutzer deaktiviert.  <br/> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft „EnableCallPark“ nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.  <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> "CsUserAdministrator"  <br/> "Csadministrator"  <br/> |[Aktivieren des Parkens von Anrufen für Benutzer in Skype für Business 2015](enable-call-park-for-users.md) <br/> |
|Überprüfen der Normalisierungsregeln für das Parken von Anrufen  <br/> |Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.  <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> CsServerAdministrator  <br/> "Csadministrator"  <br/> |[Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype für Business 2015](verify-normalization-rules-for-call-park.md) <br/> |
|Überprüfen der bereitstellungs des Parkens von Anrufen  <br/> |Testen Sie das Parken und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.  <br/> |-  <br/> |[(Optional) Überprüfen der Bereitstellung in Skype für Business 2015 zum Parken von Anrufen](optional-verify-call-park-deployment.md) <br/> |
   

