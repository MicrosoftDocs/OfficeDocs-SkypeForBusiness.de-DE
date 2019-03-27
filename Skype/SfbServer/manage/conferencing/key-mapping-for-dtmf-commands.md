---
title: Verwalten der tastenzuordnung für DTMF-Befehle in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Zusammenfassung: Erfahren Sie, wie der tastenzuordnung von Dual-Tone Multi-Frequency (MFV) Befehle in Skype für Business Server verwalten.'
ms.openlocfilehash: 33ab031e6032b6246dd637bc55c9ec6b600f0c82
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898071"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="25fcb-103">Verwalten der tastenzuordnung für DTMF-Befehle in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="25fcb-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="25fcb-104">**Zusammenfassung:** Erfahren Sie, wie der tastenzuordnung von Dual-Tone Multi-Frequency (MFV) Befehle in Skype für Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="25fcb-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="25fcb-p101">Einwahlkonferenzbenutzer können DTMF-Befehle (Dual-Tone Multi-Frequency) mithilfe der Tasten ihres Telefons ausführen. Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen mit der Telefontastatur steuern (z. B. eigene Person stummschalten bzw. die Stummschaltung der eigenen Person aufheben oder Konferenz sperren bzw. entsperren).</span><span class="sxs-lookup"><span data-stu-id="25fcb-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="25fcb-107">Verwenden Sie zum Verwalten von die Schlüssel für die DTMF-Befehle, die Skype für Business Server-Verwaltungsshell mit dem **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**und \*\* Neue-CsDialinConferencingDtmfConfiguration\*\* Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="25fcb-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="25fcb-108">Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="25fcb-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="25fcb-109">Verwalten der Tastaturzuordnung für die DTMF-Befehle</span><span class="sxs-lookup"><span data-stu-id="25fcb-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="25fcb-110">Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.</span><span class="sxs-lookup"><span data-stu-id="25fcb-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="25fcb-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="25fcb-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="25fcb-112">Um die verwendeten DTMF-Einstellungen anzuzeigen, führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="25fcb-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="25fcb-113">Um die verwendeten DTMF-Einstellungen zu ändern, führen Sie das folgende Cmdlet aus und geben Sie für jede Option, die Sie ändern möchten, die gewünschte Taste an:</span><span class="sxs-lookup"><span data-stu-id="25fcb-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="25fcb-114">(Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.</span><span class="sxs-lookup"><span data-stu-id="25fcb-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="25fcb-p102">In diesem Beispiel wird die Taste zur Aktivierung und Deaktivierung von Ankündigungen mit der Taste zur Stummschaltung und Aufhebung der Stummschaltung aller Teilnehmer getauscht. Da kein Identitätswert angegeben ist, wirken sich diese Änderungen auf die globalen DTMF-Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="25fcb-p102">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="25fcb-117">Weitere Informationen finden Sie unter [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)und [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="25fcb-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

