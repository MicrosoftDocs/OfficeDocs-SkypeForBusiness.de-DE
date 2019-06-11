---
title: 'Lync Server 2013: veröffentlichen ausstehender Änderungen in der VoIP-Routingkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22cabe1725d899ace42e5b525105c1753c3d9925
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="fecff-102">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fecff-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fecff-103">_**Letztes Änderungsdatum des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="fecff-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="fecff-104">Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="fecff-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fecff-105">Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt.</span><span class="sxs-lookup"><span data-stu-id="fecff-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="fecff-p101">Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl <STRONG>Commit für alle Element ausführen</STRONG> veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl <STRONG>Noch nicht übernommene Änderungen überprüfen</STRONG> aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fecff-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="fecff-109">Wenn Sie die Seiten in der Gruppe <STRONG>VoIP-Routing</STRONG> verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="fecff-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="fecff-110">Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fecff-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="fecff-111">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Exportieren einer sprach Routen-Konfigurationsdatei in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fecff-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="fecff-112">So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="fecff-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="fecff-113">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="fecff-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fecff-114">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fecff-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="fecff-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fecff-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fecff-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fecff-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fecff-117">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="fecff-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="fecff-118">Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.</span><span class="sxs-lookup"><span data-stu-id="fecff-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="fecff-119">Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fecff-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="fecff-120">Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="fecff-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="fecff-121">Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.</span><span class="sxs-lookup"><span data-stu-id="fecff-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="fecff-122">Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.</span><span class="sxs-lookup"><span data-stu-id="fecff-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="fecff-123">Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fecff-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="fecff-124">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fecff-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="fecff-125">Wenn die lync Server-Systemsteuerung die Änderungen übernommen hat, wird die Meldung **erfolgreich veröffentlichte sprach Routingkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecff-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

