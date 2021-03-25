---
title: Anzeigen von Konferenzrichtlinien in Skype for Business Server
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Zusammenfassung: Informationen zum Anzeigen von Konferenzrichtlinien in Skype for Business Server.'
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119404"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Anzeigen von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server anzeigen.
  
Sie können Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell anzeigen.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Konferenzrichtlinie**.
    
4. **Doppelklicken Sie** auf der Seite Konferenzrichtlinie auf die Konferenzrichtlinie, die Sie anzeigen möchten.
    
5. Aktivieren **Sie unter Dateifilter bearbeiten** das Kontrollkästchen **Details** anzeigen.
    
    **Bearbeiten von Konferenzrichtlinien \<policy\> –** zeigt die Einstellungen für die ausgewählte Richtlinie an.
    
    Weitere Informationen zum Konfigurieren der Einstellungen finden Sie unter Erstellen von Konferenzrichtlinien [in Skype for Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Anzeigen von Konferenzrichtlinien das **Cmdlet Get-CsConferencingPolicy:**
  
```PowerShell
Get-CsConferencingPolicy
```

Das Cmdlet gibt Informationen wie die folgenden zurück:
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

Weitere Informationen, einschließlich einer vollständigen Syntaxbeschreibung und einer Liste von Parametern, finden Sie unter [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
