---
title: Überlegungen zur Skype Room System-Migration
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lesen Sie dieses Thema, um Informationen über die Bereitstellung von Skype Raum System in einer Umgebung, in denen mehrere Versionen von Skype Business Server und Lync Server.
ms.openlocfilehash: fef5e3e0a64fd1d533a53586b470584421a165ea
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219430"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="ac936-103">Überlegungen zur Skype Room System-Migration</span><span class="sxs-lookup"><span data-stu-id="ac936-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="ac936-104">Lesen Sie dieses Thema, um Informationen über die Bereitstellung von Skype Raum System in einer Umgebung, in denen mehrere Versionen von Skype Business Server und Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac936-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="ac936-105">Überlegungen zur Migration</span><span class="sxs-lookup"><span data-stu-id="ac936-105">Migration considerations</span></span>

<span data-ttu-id="ac936-106">In diesem Abschnitt erfahren Sie, wenn Sie Skype Raum System in einer Umgebung mit mehreren Pools bereitstellen, die verschiedene Versionen von Skype für Business Server oder Lync Server enthält.</span><span class="sxs-lookup"><span data-stu-id="ac936-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="ac936-107">Die Benutzerreplikationskomponente (User Replicator; UR) in Lync Server erhält Benutzerobjekte aus Active Directory und legt sie in der Back-End-SQL-Serverdatenbank in Lync Server ab.</span><span class="sxs-lookup"><span data-stu-id="ac936-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="ac936-108">Nur der BENUTZERREPLIKATIONSDIENST in Lync Server 2013 kennt Skype Raum Systemobjekte.</span><span class="sxs-lookup"><span data-stu-id="ac936-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="ac936-109">Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute zur Bezeichnung von LRS-Objekten, und nimmt sie dementsprechend auch nicht wahr.</span><span class="sxs-lookup"><span data-stu-id="ac936-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="ac936-110">Wenn ein Skype Raum Systemkonto zur Anmeldung bei Lync versucht, und führt basierend auf SRV-Eintrag oder DNS-A-Eintrag Nachschlagen AutoErmittlung, und zeigen Sie diese Konten zu einer früheren Version von Lync Server oder Office Communications Server, erhält LRS eine 404 nicht gefunden-Antwort vom  Pool der Vorgängerversion.</span><span class="sxs-lookup"><span data-stu-id="ac936-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="ac936-111">Pool der Vorgängerversion möglich zur Umleitung von Skype Raum System an die Lync Server 2013 home-Pool nicht.</span><span class="sxs-lookup"><span data-stu-id="ac936-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="ac936-112">Sie können diesem Problem mit folgenden Optionen begegnen:</span><span class="sxs-lookup"><span data-stu-id="ac936-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="ac936-113">Verweisen Sie Ihren AutoErmittlung-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="ac936-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="ac936-114">Ist die erste Option nicht möglich, müssen Sie manuell konfigurieren LRS und geben Sie die Lync Server 2013-Pool-Adresse durch Konfigurieren sie direkt in die Konsolenanwendung Skype Raum System.</span><span class="sxs-lookup"><span data-stu-id="ac936-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="ac936-115">Skype Raum System außerhalb des Unternehmensnetzwerks bereitgestellt wird, und einen Lync-Edge-Server bereitgestellt und zeigen Sie auf einem vorversionspool oder Director konfiguriert wurde, ein sekundärer Standort Edge-Server ist erforderlich, der auf dem Lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="ac936-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="ac936-116">Finden Sie in der Dokumentation zur Bereitstellung von Edge-Server für Weitere Informationen zum Bereitstellen einer sekundären Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="ac936-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="ac936-117">Skype-Raum Systeminteroperabilität mit einem Lync Server 2010-Pool</span><span class="sxs-lookup"><span data-stu-id="ac936-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="ac936-118">Während der Migration Wenn ein Benutzer, der auf einem Lync Server 2010-Pool verwaltet wird eine Besprechung plant und das Systemkonto Raum Skype lädt der Client Skype Raum System eingeschränkte Funktionalität auf haben während die Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ac936-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="ac936-119">Wenn der Client Skype Raum System eine geplante Telefonkonferenz teilnimmt, die durch organisiert wurden, hat ein Benutzer auf Lync Server 2010, verwaltet, Skype Raum System weist die folgenden in der Besprechung Nachteile:</span><span class="sxs-lookup"><span data-stu-id="ac936-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="ac936-120">Skype Raum System kann nicht Videogalerie mit Mehrfachansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac936-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="ac936-121">Es kann nicht auf Teilnehmer video Sperre anwenden, wenn der Client Skype Raum System der Referent ist.</span><span class="sxs-lookup"><span data-stu-id="ac936-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="ac936-122">Skype Raum System kann nicht 1080p Auflösung (eingehend oder ausgehend), angezeigt werden, selbst wenn die konferenzrichtlinie für Lync Server 2013 es, aufgrund der folgenden ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="ac936-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="ac936-123">Lync Server 2010 unterstützt keine 1080p-Lösung.</span><span class="sxs-lookup"><span data-stu-id="ac936-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="ac936-124">Skype Raum System wird immer durch der Organisator konferenzrichtlinie für videoauflösung begrenzt.</span><span class="sxs-lookup"><span data-stu-id="ac936-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="ac936-125">Aus diesem Grund, auch wenn der Lync 2010-Pool 720p Lösung unterstützt, werden Skype Raum System nicht 720p-Auflösung nutzen, solange des Organisators Richtlinie nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac936-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="ac936-p105">Lync 2013-Clients erkennen das Vorhandensein von LRS im Besprechungsraum und schalten sich selbst stumm, um Rückkopplungen im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ac936-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="ac936-128">Für die Leistungsfähigkeit von Desktopfreigaben für auf Lync Server 2010 gehosteten Besprechungen gelten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ac936-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="ac936-129">Benutzer möglich nicht, private (eingeschränkte) an Besprechungen teilzunehmen, die gehostet werden für Lync 2010 mit Skype Raum System.</span><span class="sxs-lookup"><span data-stu-id="ac936-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

