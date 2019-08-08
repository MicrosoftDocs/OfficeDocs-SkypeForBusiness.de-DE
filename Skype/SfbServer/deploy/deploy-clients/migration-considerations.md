---
title: Überlegungen zur Skype Room System-Migration
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lesen Sie dieses Thema, um mehr über die Bereitstellung von Skype Room System in einer Umgebung zu erfahren, in der mehrere Versionen von Skype for Business Server und lync Server enthalten sind.
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234208"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="a7114-103">Überlegungen zur Skype Room System-Migration</span><span class="sxs-lookup"><span data-stu-id="a7114-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="a7114-104">Lesen Sie dieses Thema, um mehr über die Bereitstellung von Skype Room System in einer Umgebung zu erfahren, in der mehrere Versionen von Skype for Business Server und lync Server enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a7114-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="a7114-105">Überlegungen zur Migration</span><span class="sxs-lookup"><span data-stu-id="a7114-105">Migration considerations</span></span>

<span data-ttu-id="a7114-106">Dieser Abschnitt enthält Anleitungen für die Bereitstellung von Skype Room System in einer Multi-Pool-Umgebung, die unterschiedliche Versionen von Skype for Business Server oder lync Server umfasst.</span><span class="sxs-lookup"><span data-stu-id="a7114-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="a7114-107">Die Benutzerreplikationskomponente (User Replicator; UR) in Lync Server erhält Benutzerobjekte aus Active Directory und legt sie in der Back-End-SQL-Serverdatenbank in Lync Server ab.</span><span class="sxs-lookup"><span data-stu-id="a7114-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="a7114-108">Nur die ur in lync Server 2013 ist sich der Skype Room-System Objekte bewusst.</span><span class="sxs-lookup"><span data-stu-id="a7114-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="a7114-109">Die UR in früheren Versionen von Lync Server und Office Communications Server erkennt nicht die Active Directory-Attribute zur Bezeichnung von LRS-Objekten, und nimmt sie dementsprechend auch nicht wahr.</span><span class="sxs-lookup"><span data-stu-id="a7114-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="a7114-110">Wenn ein Skype Room-System Konto versucht, sich bei lync anzumelden und die automatische Ermittlung basierend auf SRV-Eintrag oder DNS ausführt, wird ein Eintrag nachschlagen, und wenn diese Konten auf eine frühere Version von lync Server oder Office Communications Server verweisen, erhält LRS eine Antwort vom 404 nicht gefunden.  der Legacy Pool.</span><span class="sxs-lookup"><span data-stu-id="a7114-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="a7114-111">Der Legacy Pool kann das Skype Room-System nicht in seinen lync Server 2013-Home-Pool umleiten.</span><span class="sxs-lookup"><span data-stu-id="a7114-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="a7114-112">Sie können diesem Problem mit folgenden Optionen begegnen:</span><span class="sxs-lookup"><span data-stu-id="a7114-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="a7114-113">Verweisen Sie Ihren AutoErmittlung-SRV-Eintrag (_sipinternaltls._tcp.contoso.com) auf den Lync Server 2013-Pool.</span><span class="sxs-lookup"><span data-stu-id="a7114-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="a7114-114">Wenn die erste Option nicht möglich ist, müssen Sie LRS manuell konfigurieren und die lync Server 2013-Pool Adresse bereitstellen, indem Sie Sie direkt in der Skype Room System Console-Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a7114-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="a7114-115">Wenn das Skype Room-System außerhalb des Unternehmensnetzwerks bereitgestellt wird und ein lync-Edgeserver bereitgestellt und so konfiguriert wurde, dass er auf einen Legacy Pool oder Director verweist, ist eine sekundäre Edgeserver-Website erforderlich, die auf den lync Server 2013-Pool verweist.</span><span class="sxs-lookup"><span data-stu-id="a7114-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="a7114-116">Weitere Informationen zum Bereitstellen eines sekundären Edgeserver finden Sie in der Dokumentation zur Edge Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a7114-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="a7114-117">Interoperabilität von Skype Room-Systemen mit einem lync Server 2010-Pool</span><span class="sxs-lookup"><span data-stu-id="a7114-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="a7114-118">Wenn ein Benutzer, der sich in einem lync Server 2010-Pool befindet, eine Besprechung plant und das Skype Room System-Konto einlädt, hat der Skype Room-System Client während der Migration nur begrenzte Funktionen, während er an der Besprechung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="a7114-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="a7114-119">Wenn der Skype Room-System Client zu einem geplanten Konferenzanruf wechselt, der von einem Benutzer organisiert wurde, der sich in lync Server 2010 befindet, gelten für Skype Room System die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="a7114-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="a7114-120">Skype Room System kann den Multi-View-Video Katalog nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7114-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="a7114-121">Wenn es sich bei dem Skype Room-System Client um den Referenten handelt, kann er keine Video Sperre für Teilnehmer anwenden.</span><span class="sxs-lookup"><span data-stu-id="a7114-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="a7114-122">Skype Room System kann keine 1080p-Videoauflösung (eingehend oder ausgehend) anzeigen, selbst wenn die lync Server 2013-konferenzrichtlinie dies zulässt, und zwar aufgrund der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="a7114-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="a7114-123">Lync Server 2010 unterstützt keine 1080p-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="a7114-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="a7114-124">Das Skype-Raum System ist immer durch die Konferenzrichtlinien des Organisators für die Videoauflösung limitiert.</span><span class="sxs-lookup"><span data-stu-id="a7114-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="a7114-125">Auch wenn der lync 2010-Pool eine 720p-Auflösung unterstützt, kann Skype Room System die 720p-Auflösung nicht nutzen, solange die Richtlinien von Organizer dies nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7114-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="a7114-p105">Lync 2013-Clients erkennen das Vorhandensein von LRS im Besprechungsraum und schalten sich selbst stumm, um Rückkopplungen im physischen Besprechungsraum zu vermeiden. Dieses Feature funktioniert nicht in Besprechungen, die auf Lync Server 2010 gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="a7114-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="a7114-128">Für die Leistungsfähigkeit von Desktopfreigaben für auf Lync Server 2010 gehosteten Besprechungen gelten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a7114-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="a7114-129">Benutzer können nicht an privaten (eingeschränkten) Besprechungen teilnehmen, die in lync 2010 mit Skype Room System gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="a7114-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

