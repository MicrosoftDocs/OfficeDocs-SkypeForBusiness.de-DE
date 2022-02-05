---
title: Aktivieren des Parkens von Anrufen für Benutzer in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren sie Benutzer für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
---

# <a name="enable-call-park-for-users-in-skype-for-business"></a>Aktivieren des Parkens von Anrufen für Benutzer in Skype for Business
 
Aktivieren sie Benutzer für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert. Benutzer können Anrufe nicht parken oder geparkte Anrufe abrufen, bis sie in der VoIP-Richtlinie für das Parken von Anrufen aktiviert sind.
  
Sie können das Parken von Anrufen auf globaler Oder Standort- oder Benutzerebene aktivieren. Der Benutzerbereich hat Vorrang vor dem Standortbereich, und der Websitebereich hat Vorrang vor dem globalen Bereich. Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um das Parken von Anrufen zu aktivieren, nicht nur die globale Richtlinie.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>So verwenden Sie Skype for Business Server Systemsteuerung, um das Parken von Anrufen für Benutzer zu aktivieren

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.
    
5. Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.
    
6. Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.
    
7. Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>So verwenden Sie Cmdlets zum Aktivieren des Parkens von Anrufen für Benutzer

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der administrativen Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell**.
    
3. Ausführen:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    So aktivieren Sie beispielsweise das Parken von Anrufen für die standardmäßige globale VoIP-Richtlinie:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Siehe auch



[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)

