---
title: Verwalten der Tastenzuordnung für DTMF-Befehle in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Tastenzuordnung von DTMF-Befehlen (Dual Tone Multi-Frequency) in Skype for Business Server verwalten.'
ms.openlocfilehash: 3bab799bb116d0ded48002eb91898ffc1587543c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991820"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Verwalten der Tastenzuordnung für DTMF-Befehle in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Tastenzuordnung von DTMF-Befehlen (Dual Tone Multi-Frequency) in Skype for Business Server verwalten.
  
Einwahlkonferenzbenutzer können DTMF-Befehle (Dual-Tone Multi-Frequency) mithilfe der Tasten ihres Telefons ausführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. die Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren). 
  
Um die für die DTMF-Befehle verwendeten Schlüssel zu verwalten, verwenden Sie die Skype for Business Server-Verwaltungsshell mit den Cmdlets " **Get-CsDialinConferencingDtmfConfiguration**", " **CsDialinConferencingDtmfConfiguration**" und " **New-CsDialinConferencingDtmfConfiguration** ".
  
Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Verwalten der Tastaturzuordnung für die DTMF-Befehle

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Um die verwendeten DTMF-Einstellungen anzuzeigen, führen Sie an der Eingabeaufforderung den folgenden Befehl aus:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Um die verwendeten DTMF-Einstellungen zu ändern, führen Sie das folgende Cmdlet aus und geben Sie für jede Option, die Sie ändern möchten, die gewünschte Taste an:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.
    
In diesem Beispiel wird die Taste zur Aktivierung und Deaktivierung von Ankündigungen mit der Taste zur Stummschaltung und Aufhebung der Stummschaltung aller Teilnehmer getauscht. Da kein Identitätswert angegeben ist, wirken sich diese Änderungen auf die globalen DTMF-Einstellungen aus.
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Weitere Informationen finden Sie unter [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)und [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

