---
title: 'Lync Server 2013: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration'
description: 'Lync Server 2013: veröffentlichen Sie ausstehende Änderungen an der VoIP-Routingkonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565451"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="13064-103">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13064-103">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13064-104">_**Letztes Änderungsstand des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="13064-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="13064-105">Nachdem Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie dieses Verfahren aus, um die ausstehenden Änderungen zu überprüfen, zu veröffentlichen oder abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="13064-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13064-106">Stellen Sie sicher, dass nur ein Benutzer gleichzeitig die Konfigurationseinstellungen für das VoIP-Routing ändert.</span><span class="sxs-lookup"><span data-stu-id="13064-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="13064-107">Alle ausstehenden Änderungen müssen gleichzeitig veröffentlicht werden, indem der Befehl <STRONG>Commit</STRONG> ausführen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13064-107">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="13064-108">Ausstehende Änderungen können nicht selektiv veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="13064-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="13064-109">Führen Sie vor dem Veröffentlichen von ausstehenden Änderungen den Befehl nicht <STRONG>Commit für Änderungen überprüfen</STRONG> aus, und löschen Sie alle Konfigurationsänderungen, die nicht veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13064-109">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="13064-110">Wenn Sie von den Seiten in der VoIP- <STRONG>Routing</STRONG> Gruppe Weg navigieren, bevor Sie ausstehende Änderungen committen, gehen alle ausstehenden Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="13064-110">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="13064-111">Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine sprach Konfigurationsdatei exportieren und anschließend die aktualisierte Konfiguration importieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="13064-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="13064-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a Voice Route Configuration File in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="13064-112">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="13064-113">So überprüfen, veröffentlichen oder kündigen Sie Konfigurationsänderungen für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="13064-113">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="13064-114">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="13064-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="13064-115">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="13064-115">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="13064-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="13064-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13064-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13064-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13064-118">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="13064-118">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="13064-119">Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf jeder Seite der **VoIP-Routing** Gruppe vor.</span><span class="sxs-lookup"><span data-stu-id="13064-119">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="13064-120">Um ausstehende Änderungen zu überprüfen, ohne Sie zu veröffentlichen, wählen Sie im Menü **Commit** die Option nicht **übernommene Änderungen überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="13064-120">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="13064-121">Wenn Sie die ausstehenden Änderungen abbrechen möchten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="13064-121">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="13064-122">Wählen Sie im Menü **Commit** die Option **alle nicht übernommenen Änderungen abbrechen** aus.</span><span class="sxs-lookup"><span data-stu-id="13064-122">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="13064-123">Navigieren Sie zur Registerkarte der **VoIP-Routing** Seite mit ausstehenden Änderungen, die Sie abbrechen möchten, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit**, und klicken Sie dann auf **ausgewählte Änderungen abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="13064-123">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="13064-124">Nachdem Sie alle ausstehenden Änderungen überprüft und alle gelöscht haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit**, und klicken Sie dann auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="13064-124">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="13064-125">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen ohne Commit** , in dem eine Liste aller ausstehenden Änderungen angezeigt wird, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="13064-125">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="13064-126">Wenn lync Server-Systemsteuerung die Änderungen übernommen hat, wird die Meldung **erfolgreich veröffentlichter VoIP-Routing-Konfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="13064-126">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

