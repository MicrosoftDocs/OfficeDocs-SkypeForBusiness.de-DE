---
title: Erstellen von Standortrichtlinien in Skype for Business Server
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
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für den erweiterten Notfalldienst (E9-1-1) in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822545"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Erstellen von Standortrichtlinien in Skype for Business Server

In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für erweiterte Notfalldienste (E9-1-1) in Skype for Business Server Enterprise-VoIP. 

Skype for Business Server verwendet eine Standortrichtlinie, um Skype for Business-Clients während der Clientregistrierung für E9-1-1 zu aktivieren. Eine Standortrichtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Weitere Informationen finden Sie unter ["Planen von Standortrichtlinien für Skype for Business Server".](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)

Sie definieren Standortrichtlinien mithilfe der Skype for Business-Systemsteuerung oder mithilfe des [Cmdlets "New-CsLocationPolicy".](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)

> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie die Informationen in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) und Configure multiple emergency numbers in Skype for Business [befolgen.](configure-multiple-emergency-numbers.md) 

Sie können die globale Standortrichtlinie bearbeiten und neue kategorisierten Standortrichtlinien erstellen. Ein Client erhält eine globale Richtlinie, wenn er sich nicht in einem Subnetz mit einer zugeordneten Standortrichtlinie befindet oder dem Client keine Standortrichtlinie direkt zugewiesen wurde. Markierte Richtlinien werden Subnetzen oder Benutzern zugewiesen. 

Zum Erstellen einer Standortrichtlinie müssen Sie ein Konto verwenden, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder Mitglied der Administratorrolle "CsVoiceAdministrator" ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.

Weitere Informationen finden Sie unter ["Planen von Standortrichtlinien für Skype for Business Server".](../../plan-your-deployment/enterprise-voice-solution/location-policies.md) Cmdlets in diesem Verfahren verwenden eine Standortrichtlinie, die mit den folgenden Werten definiert wurde. Eine vollständige Beschreibung der Parameter und Werte von Cmdlets finden Sie unter [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Element**                               | **Wert**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Haftungsausschluss** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | Ihre Unternehmensrichtlinie erfordert, dass Sie einen Standort festlegen. Wenn Sie keinen Standort festlegen, können Notrufdienste Sie im Notfall nicht finden. Bitte legen Sie einen Speicherort an.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>So erstellen Sie Standortrichtlinien

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

    > [!NOTE]
    > Bei "CsLocationPolicy" wird ein Fehler angezeigt, wenn die Einstellung für **"PstnUsage"** noch nicht in der globalen Liste von "PstnUsages" enthalten ist.

2. Führen Sie optional das folgende Cmdlet aus, um die globale Standortrichtlinie zu bearbeiten:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Führen Sie die folgenden Schritte aus, um eine markierte Standortrichtlinie zu erstellen.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte markierte Standortrichtlinie auf eine Benutzerrichtlinie anzuwenden.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
