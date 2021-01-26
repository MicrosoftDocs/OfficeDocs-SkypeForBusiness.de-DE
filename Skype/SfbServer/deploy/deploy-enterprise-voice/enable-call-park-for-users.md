---
title: Aktivieren des Parkens von Anrufen für Benutzer in Skype for Business
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren Sie Benutzer für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830955"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Aktivieren des Parkens von Anrufen für Benutzer in Skype for Business
 
Aktivieren Sie Benutzer für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert. Benutzer können Anrufe erst parken oder geparkte Anrufe abrufen, wenn sie in der Sprachrichtlinie für das Parken von Anrufen aktiviert sind.
  
Sie können das Parken von Anrufen auf globaler ebene oder auf Standort- oder Benutzerbereich aktivieren. Der Benutzerbereich hat Vorrang vor dem Standortbereich, und der Standortbereich hat Vorrang vor dem globalen Bereich. Wenn Sie über mehrere Richtlinien für Sprachanrufe verfügen, überprüfen Sie alle Richtlinien, um das Parken von Anrufen zu aktivieren, nicht nur die globale Richtlinie.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>So aktivieren Sie das Parken von Anrufen für Benutzer mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.
    
5. Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.
    
6. Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.
    
7. Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>So verwenden Sie Cmdlets zum Aktivieren des Parkens von Anrufen für Benutzer

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der administrativen Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie dies aus:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    So aktivieren Sie beispielsweise das Parken von Anrufen für die globale Standard-Voice-Richtlinie:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Siehe auch



[Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)

