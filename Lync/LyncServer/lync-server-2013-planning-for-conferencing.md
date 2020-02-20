---
title: 'Lync Server 2013: Planen von Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0fd8edb6e2939b82711392c53b0e5bef3e7740
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="eed8a-102">Planen von Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed8a-103">_**Letztes Änderungsstand des Themas:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="eed8a-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="eed8a-104">Lync Server 2013 bietet eine umfassende Palette von Konferenzfunktionen:</span><span class="sxs-lookup"><span data-stu-id="eed8a-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="eed8a-105">Webkonferenzen, einschließlich Dokument Zusammenarbeit, Anwendungsfreigabe und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="eed8a-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="eed8a-106">Lync Server 2013 verwendet Office-Webanwendungen und den Office-webapps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="eed8a-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="eed8a-107">Ausführliche Informationen zum Installieren und Konfigurieren des Office-webapps-Servers finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="eed8a-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="eed8a-108">Audio/Video-Konferenzen (A/V), mit denen Benutzer in Echtzeit Audio-oder Videokonferenzen haben können, ohne dass externe Dienste wie die Microsoft Live Meeting-Dienst oder eine Audio-Bridge eines Drittanbieters erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eed8a-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="eed8a-109">Einwahlkonferenzen, mit denen Benutzer dem Audioteil einer lync Server 2013 Konferenz mithilfe eines PSTN-Telefons (Public Switched Telephone Network) beitreten können, ohne dass ein Drittanbieter für Audiokonferenzen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="eed8a-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="eed8a-110">Chat Konferenzen (Instant Messaging), bei denen mehr als zwei Parteien in einer einzelnen Chatsitzung miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="eed8a-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="eed8a-111">Ausführliche Informationen zu Chat Konferenzen finden Sie unter [Planning for Front End Servers, Instant Messaging und Presence in lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="eed8a-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="eed8a-112">Lync Server 2013 unterstützt sowohl geplante Konferenzen als auch spontane Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="eed8a-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="eed8a-113">Wenn Sie lync Server 2013 Front-End-Server bereitstellen, können Sie auswählen, ob Sie auch die Webkonferenz-, A/V-Konferenz-und einwahlkonferenzfunktionen bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="eed8a-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="eed8a-114">Chat Konferenzfunktionen werden immer automatisch zusammen mit Chatfunktionen auf lync Server 2013-Front-End-Servern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eed8a-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eed8a-115">Wenn Ihre Bereitstellung Besprechungen umfasst, die mit Office Communicator 2007 R2 Clients (einschließlich der Live Meeting Konsole oder Add-in für Konferenzen für Microsoft Office Outlook) organisiert werden, haben die Besprechungen nach der Migration zu lync folgende Einschränkungen: Server 2013:</span><span class="sxs-lookup"><span data-stu-id="eed8a-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="eed8a-116">Benutzer in der Besprechung können keine Daten Zusammenarbeitsfeatures verwenden, einschließlich Dokument Zusammenarbeit, Anwendungsfreigabe und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="eed8a-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="eed8a-117">Stabilitätsprobleme können auftreten, da Office Communicator 2007 R2 Clients nicht mit lync Server 2013 unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="eed8a-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="eed8a-118">Um diese Probleme zu vermeiden, planen Sie eine Besprechung, die mit Office Communicator 2007 R2-Clients mit Outlook 2010 oder Outlook 2013 organisiert wurde, entweder über das Add-in Onlinebesprechung für lync 2010 oder Online-Besprechungs-Add-in für lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eed8a-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="eed8a-119">In den folgenden Abschnitten wird beschrieben, was für die Bereitstellung der verschiedenen Arten von Konferenzfunktionen erforderlich ist, einschließlich des Planungsprozesses, der Komponenten, der Hardware-und Softwareanforderungen sowie des Bereitstellungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="eed8a-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eed8a-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eed8a-120">In This Section</span></span>

  - [<span data-ttu-id="eed8a-121">Übersicht über Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="eed8a-122">Definieren der Anforderungen für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="eed8a-123">Komponenten und Topologien für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="eed8a-124">Technische Anforderungen für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="eed8a-125">Prüfliste für die Bereitstellung für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="eed8a-126">Unterstützung für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed8a-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

