---
title: Anzeigen von Konferenzrichtlinien in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von konferenzrichtlinien in Skype für Business Server 2015.'
ms.openlocfilehash: 4d91a04456f7c9d877e58caed1d576edc0f80b41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a>Anzeigen von Konferenzrichtlinien in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Anzeigen von konferenzrichtlinien in Skype für Business Server 2015.
  
Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell anzeigen.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Anzeigen von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.
    
5. Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.
    
    **Konferenzrichtlinie bearbeiten - \<Richtlinie\> ** die Einstellungen für die ausgewählte Richtlinie wird geöffnet.
    
    Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [Erstellen von konferenzrichtlinien in Skype für Business Server 2015](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Anzeigen von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Get-CsConferencingPolicy**, um Konferenzrichtlinien anzuzeigen:
  
```
Get-CsConferencingPolicy
```

Das Cmdlet gibt zum Beispiel folgende Informationen zurück:
  
```
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

```

Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

