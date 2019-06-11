---
title: 'Lync Server 2013: Konfigurieren der Katalogansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="7c66f-102">Konfigurieren der Katalogansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c66f-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c66f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7c66f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7c66f-104">In lync Server 2013 konfigurieren Sie Videokonferenzen in der Katalogansicht in Konferenzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7c66f-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="7c66f-105">Die Katalogansicht ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7c66f-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="7c66f-106">Wenn Sie die Katalogansicht nicht zulassen oder nur für einige Benutzer zulassen möchten, müssen Sie das Feature in Konferenzrichtlinien deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7c66f-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="7c66f-107">Wenn das Video eines Konferenzteilnehmers nicht zur Verfügung steht, kann die Benutzeroberfläche für die Galerieansicht verbessert werden, wenn Sie Fotos mit hoher Auflösung, ein neues Feature in lync Server 2013, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7c66f-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="7c66f-108">Fotos mit hoher Auflösung bieten eine Alternative zu den kleineren, in den Active Directory-Domänendiensten gespeicherten Kontaktfotos mit begrenzter Auflösung.</span><span class="sxs-lookup"><span data-stu-id="7c66f-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="7c66f-109">Fotos mit hoher Auflösung werden im Exchange 2013-Postfach eines Benutzers gespeichert, und daher müssen Sie lync Server 2013 in Exchange 2013 integrieren.</span><span class="sxs-lookup"><span data-stu-id="7c66f-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="7c66f-110">Ausführliche Informationen finden Sie im NextHop-Blog Artikel "Integration von Exchange 2013 und lync Server 2013" unter [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span><span class="sxs-lookup"><span data-stu-id="7c66f-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c66f-111">Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7c66f-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="7c66f-112">Sie können die Parameter für die Katalogansicht mithilfe der lync Server 2013-Systemsteuerung oder mithilfe eines der folgenden Cmdlets anzeigen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="7c66f-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="7c66f-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7c66f-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="7c66f-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7c66f-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="7c66f-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7c66f-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="7c66f-116">Konfigurieren Sie die Katalogansicht mit den folgenden konferenzrichtlinieneinstellungen:</span><span class="sxs-lookup"><span data-stu-id="7c66f-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="7c66f-117">**AllowMultiview**   dieser Parameter steuert, ob ein Benutzer die Möglichkeit hat, Videokonferenzen in der Katalogansicht zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="7c66f-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="7c66f-118">Dieser Parameter gilt für geplante und Ad-hoc-Besprechungen, die vom Benutzer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7c66f-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="7c66f-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7c66f-119">Examples:</span></span>
    
      - <span data-ttu-id="7c66f-120">Dieser Parameter ist für Benutzer A auf true festgelegt, der in einem lync Server 2013-Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="7c66f-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="7c66f-121">Besprechungen, die von einem Benutzer organisiert werden, ermöglichen es Benutzern, mehreren Videostreams beizutreten und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="7c66f-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="7c66f-122">Dieser Parameter wird für Benutzer B auf "false" festgelegt, der sich in einem lync Server 2013-Pool befindet.</span><span class="sxs-lookup"><span data-stu-id="7c66f-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="7c66f-123">Besprechungen, die von Benutzer B organisiert werden, sind mit einem einzelnen Videostream vergleichbar mit der Videokonferenz, die von lync Server 2010 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7c66f-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="7c66f-124">Dieser Parameter bestimmt, wer Besprechungen organisieren kann, die mehrere Videostreams zulassen.</span><span class="sxs-lookup"><span data-stu-id="7c66f-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="7c66f-125">Teilnehmern an Besprechungen, die mehrere Videostreams zulassen, ist es möglich, auf der Grundlage ihrer individuellen Berechtigungen mehrere Videostreams zu empfangen (siehe Beschreibung des EnableMultiviewJoin-Parameters).</span><span class="sxs-lookup"><span data-stu-id="7c66f-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="7c66f-126">**EnableMultiviewJoin**   dieser Parameter steuert, ob ein Teilnehmer an einer Besprechung in Besprechungen, die ihn zulassen, die videoerfahrung in der Galerieansicht erhält.</span><span class="sxs-lookup"><span data-stu-id="7c66f-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="7c66f-127">Dieser Parameter steuert die Benutzererfahrung in jeder Besprechung, an der Sie teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="7c66f-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="7c66f-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7c66f-128">Examples:</span></span>
    
      - <span data-ttu-id="7c66f-129">Dieser Parameter wird für Benutzer c auf "true" festgelegt, um mehrere Videostreams empfangen zu können, wenn Sie an einer Besprechung teilnehmen, die von Benutzer a organisiert oder gestartet wurde. Benutzer c erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bereitgestellt wird, wenn teilnehmen an einer Besprechung, die von Benutzer B organisiert oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7c66f-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="7c66f-130">Dieser Parameter wird für Benutzer d auf "false" festgelegt und erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer Besprechung, die von Benutzer a oder Benutzer B organisiert wurde, bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7c66f-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="7c66f-131">Das folgende Verfahren ist ein Beispiel für die Verwendung der lync Server-Verwaltungsshell zum Aktivieren von Videokonferenzen in der Katalogansicht.</span><span class="sxs-lookup"><span data-stu-id="7c66f-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="7c66f-132">So ändern Sie die konferenzrichtlinie für Videokonferenzen in der Katalogansicht</span><span class="sxs-lookup"><span data-stu-id="7c66f-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="7c66f-133">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7c66f-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7c66f-134">Führen Sie in der Befehlszeile das folgende Cmdlet aus, um die konferenzrichtlinie zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="7c66f-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

