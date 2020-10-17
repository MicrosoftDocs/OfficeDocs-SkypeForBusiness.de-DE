---
title: 'Lync Server 2013: Konfigurieren der Katalogansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fd9823ca211242e0fd317e8a62ea118ed91a82f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517462"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="be907-102">Konfigurieren der Katalogansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be907-102">Configuring Gallery View in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be907-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="be907-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="be907-104">In lync Server 2013 konfigurieren Sie Videokonferenzen für die Galerieansicht in der konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="be907-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="be907-105">Die Galerieansicht ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="be907-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="be907-106">Wenn Sie nicht möchten, dass die Galerieansicht verwendet wird, oder wenn diese Ansicht nur von bestimmten Benutzern verwendet werden soll, müssen Sie diese Funktion in der Konferenzrichtlinie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="be907-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="be907-107">Wenn das Video eines Konferenzteilnehmers nicht verfügbar ist, kann die Benutzeroberfläche der Galerieansicht verbessert werden, wenn Sie hochauflösende Fotos bereitstellen, ein neues Feature in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be907-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="be907-108">Hochauflösende Fotos bieten eine Alternative zu den kleineren, begrenzten Auflösungen von Kontaktfotos, die in Active Directory-Domänendienste gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="be907-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="be907-109">Hochauflösende Fotos werden im Exchange 2013 Postfach eines Benutzers gespeichert und erfordern daher die Integration von lync Server 2013 mit Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="be907-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="be907-110">Ausführliche Informationen finden Sie im NextHop-Blog Artikel "integrieren von Exchange 2013 und lync Server 2013" unter [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) .</span><span class="sxs-lookup"><span data-stu-id="be907-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be907-111">Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="be907-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="be907-112">Sie können die Parameter der Katalogansicht mithilfe lync Server 2013 Systemsteuerung oder mithilfe eines der folgenden Cmdlets anzeigen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="be907-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="be907-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="be907-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="be907-114">**Gruppe-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="be907-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="be907-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="be907-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="be907-116">Konfigurieren der Galerieansicht mit den folgenden Konferenzrichtlinieneinstellungen:</span><span class="sxs-lookup"><span data-stu-id="be907-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="be907-117">**AllowMultiview**     Dieser Parameter steuert, ob ein Benutzer die Videokonferenzen für die Galerieansicht organisieren darf.</span><span class="sxs-lookup"><span data-stu-id="be907-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="be907-118">Die Festlegung des Parameters gilt für geplante Besprechungen ebenso wie für Ad-hoc-Besprechungen, die vom Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="be907-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="be907-119">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="be907-119">Examples:</span></span>
    
      - <span data-ttu-id="be907-120">Dieser Parameter ist für Benutzer a, der in einem lync Server 2013 Pool verwaltet wird, auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="be907-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="be907-121">Von Benutzer A organisierte Besprechungen ermöglichen Benutzern das Hinzufügen und empfangen mehrerer Videostreams.</span><span class="sxs-lookup"><span data-stu-id="be907-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="be907-122">Dieser Parameter wird für Benutzer B auf "false" festgelegt, der in einem lync Server 2013 Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="be907-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="be907-123">Von Benutzer B organisierte Besprechungen weisen einen einzelnen Videostream auf, der der von lync Server 2010 bereitgestellten Videokonferenz ähnelt.</span><span class="sxs-lookup"><span data-stu-id="be907-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="be907-p106">Dieser Parameter legt fest, welche Benutzer Besprechungen mit mehreren Videostreams organisieren können. Teilnehmer von Besprechungen, bei denen mehrere Videostreams zulässig sind, können diese empfangen, wenn sie dazu berechtigt sind (siehe Beschreibung für den EnableMultiviewJoin-Parameter). Andernfalls ist dies nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="be907-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="be907-126">**EnableMultiviewJoin**     Mit diesem Parameter wird gesteuert, ob ein Teilnehmer an einer Besprechung in Besprechungen, die ihn zulassen, das Videoerlebnis "Gallery View" erhält.</span><span class="sxs-lookup"><span data-stu-id="be907-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="be907-127">Der Parameter wirkt sich auf alle Besprechungen aus, an denen ein Benutzer teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="be907-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="be907-128">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="be907-128">Examples:</span></span>
    
      - <span data-ttu-id="be907-129">Dieser Parameter ist für Benutzer c auf true festgelegt. Benutzer c kann mehrere Videostreams empfangen, wenn er an einer Besprechung teilnimmt, die von Benutzer a organisiert oder gestartet wird. Benutzer c erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer von Benutzer B organisierten oder gestarteten Besprechung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="be907-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="be907-130">Dieser Parameter wird für Benutzer d auf "false" festgelegt. Benutzer d erhält einen einzelnen Videostream, der der Videokonferenz ähnelt, die von lync Server 2010 bei der Teilnahme an einer von Benutzer a oder Benutzer B organisierten Besprechung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="be907-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="be907-131">Das folgende Verfahren ist ein Beispiel für die Verwendung von lync Server-Verwaltungsshell zum Aktivieren von Videokonferenzen in der Galerieansicht.</span><span class="sxs-lookup"><span data-stu-id="be907-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="be907-132">So bearbeiten Sie die Konferenzrichtlinie für Videokonferenzen in der Galerieansicht</span><span class="sxs-lookup"><span data-stu-id="be907-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="be907-133">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="be907-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="be907-134">Führen Sie das folgende Cmdlet über die Befehlszeile aus, um die Konferenzrichtlinie zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="be907-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

