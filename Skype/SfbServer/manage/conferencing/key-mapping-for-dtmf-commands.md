---
title: Verwalten der Schlüsselzuordnung für DTMF-Befehle in Skype for Business Server
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Tastenzuordnung von DtmF-Befehlen (Dual-Tone Multi Frequency) in Skype for Business Server verwalten.'
ms.openlocfilehash: 6b409ccce10128fdd7776e3ea77d6ee17d4a49f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119444"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Verwalten der Schlüsselzuordnung für DTMF-Befehle in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Tastenzuordnung von DtmF-Befehlen (Dual-Tone Multi Frequency) in Skype for Business Server verwalten.
  
Benutzer von Einwahlkonferenzen können die Tasten auf der Telefontaste drücken, um DTMF-Befehle (Dual-Tone Multi Frequency) auszuführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, die Konferenzeinstellungen steuern (z. B. stummschalten und deaktivieren oder die Konferenz sperren und entsperren), indem sie die Tastatur auf ihrem Telefon verwenden. 
  
Verwenden Sie die Skype for Business Server Management Shell mit den **Cmdlets Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** und **New-CsDialinConferencingDtmfConfiguration,** um die Schlüssel zu verwalten, die für die DTMF-Befehle verwendet werden.
  
Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Verwalten der Schlüsselzuordnung von DTMF-Befehlen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um die für Einwahlkonferenzen verwendeten DTMF-Einstellungen anzeigen zu können:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Führen Sie zum Ändern der für Einwahlkonferenzen verwendeten DTMF-Einstellungen das folgende Cmdlet aus, und geben Sie die Taste an, die für jede Option gedrückt werden soll, die Sie ändern möchten:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.
    
Im folgenden Beispiel wird die Taste, die gedrückt wird, um Ansagen zu aktivieren oder zu deaktivieren, und die Taste, die gedrückt wird, um alle Teilnehmer stummschalten und stummschalten zu lassen, ausgetauscht. Da keine Identität angegeben ist, gelten diese Änderungen für die globalen DTMF-Einstellungen:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Weitere Informationen finden Sie unter [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)und [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
