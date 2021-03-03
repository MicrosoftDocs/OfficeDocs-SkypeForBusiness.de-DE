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
description: 'Zusammenfassung: Informationen zum Verwalten der Tastenzuordnung von Dual-Tone Multi-Frequency (DTMF)-Befehlen in Skype for Business Server.'
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828095"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Verwalten der Tastenzuordnung für DTMF-Befehle in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Tastenzuordnung von Dual-Tone Multi-Frequency (DTMF)-Befehlen in Skype for Business Server verwalten.
  
Benutzer von Einwahlkonferenzen können Tasten auf der Telefontaste drücken, um Dual-Tone-DTMF-Befehle (Dual-Tone Multi-Frequency) auszuführen. Mit dtmF-Befehlen können Benutzer, die sich in eine Konferenz einwählen, Konferenzeinstellungen (z. B. stummschalten und Stummschalten der eigenen Eigenen oder Sperren und Entsperren der Konferenz) über die Tastatur auf ihrem Telefon steuern. 
  
Verwenden Sie die Skype for Business Server-Verwaltungsshell mit den Cmdlets **"Get-CsDialinConferencingDtmfConfiguration",** **"Set-CsDialinConferencingDtmfConfiguration"** und **"New-CsDialinConferencingDtmfConfiguration",** um die für die Befehle "DTMF" verwendeten Schlüssel zu verwalten.
  
Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Verwalten der Tastenzuordnung von DTMF-Befehlen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um die für Einwahlkonferenzen verwendeten DTMF-Einstellungen anzeigen zu können:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Führen Sie das folgende Cmdlet aus, und geben Sie die Taste für jede Option an, die Sie ändern möchten, um die für Einwahlkonferenzen verwendeten DTMF-Einstellungen zu ändern:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.
    
Im folgenden Beispiel wird die Taste, die zum Aktivieren oder Deaktivieren von Ansagen gedrückt wird, und die Taste, die zum Stummschalten und Deaktivieren der Stummschaltung aller Teilnehmer gedrückt wird, ausgetauscht. Da keine Identität angegeben ist, gelten diese Änderungen für die globalen DTMF-Einstellungen:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Weitere Informationen finden Sie unter ["Get-CsDialInConferencingDtmfConfiguration",](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) ["Set-CsDialInConferencingDtmfConfiguration"](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)und ["New-CsDialInConferencingDtmfConfiguration".](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)
  

