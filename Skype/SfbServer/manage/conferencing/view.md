---
title: Anzeigen von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server anzeigen.'
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992190"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6b3d3-103">Anzeigen von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b3d3-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6b3d3-104">**Zusammenfassung:** Informationen zum Anzeigen von Konferenzrichtlinien in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6b3d3-105">Sie können Konferenzrichtlinien über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6b3d3-106">Anzeigen von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6b3d3-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6b3d3-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6b3d3-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6b3d3-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6b3d3-110">Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="6b3d3-111">Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="6b3d3-112">**Konferenzrichtlinien bearbeiten – \<die\> Richtlinie** wird geöffnet und zeigt die Einstellungen für die ausgewählte Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="6b3d3-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="6b3d3-113">Details zum Konfigurieren der Einstellungen finden Sie unter [Erstellen von Konferenzrichtlinien in Skype for Business Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6b3d3-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6b3d3-114">Anzeigen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6b3d3-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6b3d3-115">Verwenden Sie das Cmdlet **Get-CsConferencingPolicy**, um Konferenzrichtlinien anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="6b3d3-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="6b3d3-116">Das Cmdlet gibt zum Beispiel folgende Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="6b3d3-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="6b3d3-117">Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6b3d3-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

