---
title: 'Lync Server 2013: Anzeigen von Informationen zur konferenzrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2417af7b1258a1b0bd9fce1bd5aafb6c691c59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506522"
---
# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="2e378-102">Anzeigen von Informationen zu Konferenzrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e378-102">View conferencing policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e378-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2e378-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2e378-104">In lync Server 2013 Systemsteuerung verwenden Sie Konferenzrichtlinien, um zu steuern, wie Konferenzen in Ihrer Bereitstellung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e378-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="2e378-105">Dies umfasst die folgenden Konferenzrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="2e378-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="2e378-106">Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2e378-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2e378-107">Optionale Richtlinie auf Standort-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Konferenzen für bestimmte Websites oder Benutzer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e378-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="2e378-108">So zeigen Sie konferenzrichtlinieneinstellungen an</span><span class="sxs-lookup"><span data-stu-id="2e378-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="2e378-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2e378-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2e378-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2e378-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2e378-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2e378-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2e378-112">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="2e378-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="2e378-113">Doppelklicken Sie auf der Seite **konferenzrichtlinie** auf die konferenzrichtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e378-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="2e378-114">Wählen Sie unter **Datei Filter bearbeiten**die Option **Details anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="2e378-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="2e378-115">Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="2e378-115">check box.</span></span>
    
    <span data-ttu-id="2e378-116">**Bearbeiten der konferenzrichtlinie \<policy\> –** Öffnet die Anzeige der Einstellungen für die ausgewählte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="2e378-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="2e378-117">Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2e378-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2e378-118">Anzeigen von Konferenzrichtlinien mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2e378-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2e378-119">Konferenzrichtlinien können mithilfe von Windows PowerShell und dem Get-CsConferencingPolicy-Cmdlet angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2e378-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="2e378-120">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2e378-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2e378-121">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="2e378-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="2e378-122">So zeigen Sie Konferenzrichtlinien an</span><span class="sxs-lookup"><span data-stu-id="2e378-122">To view conferencing policies</span></span>

  - <span data-ttu-id="2e378-123">Um Informationen zu allen Konferenzrichtlinien anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="2e378-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="2e378-124">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="2e378-124">That will return information similar to this:</span></span>
    
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

</div>

<span data-ttu-id="2e378-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="2e378-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

