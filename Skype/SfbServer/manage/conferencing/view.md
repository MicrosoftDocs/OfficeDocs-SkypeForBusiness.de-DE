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
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="1f50b-103">Anzeigen von Konferenzrichtlinien in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1f50b-103">View conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1f50b-104">**Zusammenfassung:** Informationen Sie zum Anzeigen von konferenzrichtlinien in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1f50b-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1f50b-105">Sie können konferenzrichtlinien mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f50b-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1f50b-106">Anzeigen von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="1f50b-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1f50b-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1f50b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1f50b-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1f50b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1f50b-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="1f50b-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="1f50b-110">Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f50b-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="1f50b-111">Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1f50b-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="1f50b-112">**Konferenzrichtlinie bearbeiten - \<Richtlinie\> ** die Einstellungen für die ausgewählte Richtlinie wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1f50b-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="1f50b-113">Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [Erstellen von konferenzrichtlinien in Skype für Business Server 2015](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f50b-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server 2015](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1f50b-114">Anzeigen von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="1f50b-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1f50b-115">Verwenden Sie das Cmdlet **Get-CsConferencingPolicy**, um Konferenzrichtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1f50b-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="1f50b-116">Das Cmdlet gibt zum Beispiel folgende Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="1f50b-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="1f50b-117">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1f50b-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

