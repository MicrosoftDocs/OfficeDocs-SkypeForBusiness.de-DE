---
title: Aktivieren des Anruf Parks für Benutzer in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren von Benutzern für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: c3ad2bcf70c7b175ba372ba2834e56209de9f664
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002555"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Aktivieren des Anruf Parks für Benutzer in Skype for Business
 
Aktivieren von Benutzern für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP
  
Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert. Benutzer können keine Anrufe parken oder geparkte Anrufe abrufen, bis Sie in der VoIP-Richtlinie für den Anruf Park aktiviert sind.
  
Sie können das Parken von Anrufen im globalen Bereich oder auf dem Website Bereich oder dem Benutzerbereich aktivieren. Der Benutzerbereich hat Vorrang vor dem Website Bereich, und der Website Bereich hat Vorrang vor dem globalen Bereich. Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um den Anruf Park zu aktivieren, und nicht nur die globale Richtlinie.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>So verwenden Sie die Skype for Business Server-Systemsteuerung zum Aktivieren des Anruf Parks für Benutzer

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.
    
5. Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.
    
6. Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.
    
7. Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>So verwenden Sie Cmdlets zum Aktivieren des Anruf Parks für Benutzer

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie folgenden Befehl aus:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    So können Sie beispielsweise den Anruf Park für die standardmäßige globale VoIP-Richtlinie aktivieren:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Siehe auch



[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)

