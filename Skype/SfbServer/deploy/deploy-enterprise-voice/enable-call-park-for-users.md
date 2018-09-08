---
title: Aktivieren des Parkens von Anrufen für Benutzer in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren von Benutzern für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: b9df6aebba145d71aa6d64d8f192d2ef332e5a7d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883932"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Aktivieren des Parkens von Anrufen für Benutzer in Skype für Unternehmen
 
Aktivieren von Benutzern für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
  
Parken von Anrufen ist standardmäßig für alle Benutzer deaktiviert. Benutzer können nicht Anrufe Parken oder Geparkte Anrufe abgerufen werden soll, bis sie für das Parken von Anrufen in VoIP-Richtlinie aktiviert sind.
  
Sie können das Parken von Anrufen auf globaler Ebene oder auf Standortebene oder Benutzerebene aktivieren. Benutzerbereich Vorrang gegenüber auf Standortebene und auf Standortebene Vorrang gegenüber globaler Ebene. Wenn Sie mehrere VoIP-Richtlinien haben, überprüfen Sie alle Richtlinien zum Parken von Anrufen, nicht nur die globale Richtlinie zu aktivieren.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Skype für Business Server-Systemsteuerung zum Aktivieren des Parkens von Anrufen für Benutzer zu verwenden.

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.
    
5. Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.
    
6. Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.
    
7. Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Zum Verwenden von Cmdlets zum Aktivieren des Parkens von Anrufen für Benutzer

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie folgenden Befehl aus:
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Wenn Sie beispielsweise zum Parken von Anrufen für die standardmäßige globale VoIP-Richtlinie zu aktivieren:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Siehe auch



[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen](voice-policy-and-pstn-usage-records.md)

