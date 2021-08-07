---
title: Verwalten der Tastenzuordnung für DTMF-Befehle in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Tastenzuordnung von DTMF-Befehlen (Dual-Tone Multi-Frequency) in Skype for Business Server verwalten.'
ms.openlocfilehash: 106cd301826792ec494df4d490a6b953baf3badd1740d9cfd2de12e6de966d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276850"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Verwalten der Tastenzuordnung für DTMF-Befehle in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Tastenzuordnung von DTMF-Befehlen (Dual-Tone Multi-Frequency) in Skype for Business Server verwalten.
  
Benutzer von Einwahlkonferenzen können Tasten auf der Telefontastatur drücken, um DTMF-Befehle (Dual-Tone Multi-Frequency) auszuführen. MIT DTMF-Befehlen können Benutzer, die sich in eine Konferenz einwählen, Konferenzeinstellungen (z. B. Stummschalten und Aufheben der Stummschaltung selbst oder Sperren und Entsperren der Konferenz) mithilfe der Tastatur auf ihrem Telefon steuern. 
  
Um die für die DTMF-Befehle verwendeten Schlüssel zu verwalten, verwenden Sie die Skype for Business Server Verwaltungsshell mit den Cmdlets **"Get-CsDialinConferencingDtmfConfiguration",** **"Set-CsDialinConferencingDtmfConfiguration"** und **"New-CsDialinConferencingDtmfConfiguration".**
  
Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Verwalten der Tastenzuordnung von DTMF-Befehlen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um die für Einwahlkonferenzen verwendeten DTMF-Einstellungen anzuzeigen:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Um die DTMF-Einstellungen für Einwahlkonferenzen zu ändern, führen Sie das folgende Cmdlet aus, und geben Sie die Taste an, die für jede Option gedrückt werden soll, die Sie ändern möchten:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.
    
Im folgenden Beispiel wird die taste, die gedrückt wird, um Ankündigungen zu aktivieren oder zu deaktivieren, und die Taste, die gedrückt wird, um alle Teilnehmer stumm zu schalten und die Stummschaltung aufzuheben, vertauscht. Da kein Identitätswert angegeben ist, gelten diese Änderungen für die globalen DTMF-Einstellungen:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Weitere Informationen finden Sie unter ["Get-CsDialInConferencingDtmfConfiguration",](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) ["Set-CsDialInConferencingDtmfConfiguration"](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)und ["New-CsDialInConferencingDtmfConfiguration".](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)
