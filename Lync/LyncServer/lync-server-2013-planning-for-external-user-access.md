---
title: 'Lync Server 2013: Planen des Zugriffs durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e418ee1db146afa1f766aa0fc56842222f7b510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="315b5-102">Planen des Zugriffs durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="315b5-103">_**Letztes Änderungsstand des Themas:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="315b5-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="315b5-p101">Die Kommunikation beinhaltet in den meisten Organisationen Dienste und Benutzer, die sich nicht innerhalb des internen Netzwerks befinden. Diese Dienste und Benutzer umfassen Mitarbeiter, die zeitweise oder dauerhaft außerhalb des Standorts arbeiten, Mitarbeiter von Kunden- oder Partnerorganisationen, Benutzer von öffentlichen Instant Messaging-Diensten (IM) sowie potenzielle Kunden, Partner und anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen möchten. Diese Benutzer werden in dieser Dokumentation kollektiv als *externe Benutzer* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="315b5-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="315b5-107">Mit Microsoft lync Server 2013 können Benutzer in Ihrer Organisation Chat und Anwesenheitsinformationen verwenden, um mit externen Benutzern zu kommunizieren, und Sie können an Audio/Video-Konferenzen und-Webkonferenzen mit Ihren externen Mitarbeitern und anderen Typen externer Benutzer teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="315b5-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="315b5-108">Sie können auch den externen Zugriff von mobilen Geräten und über Enterprise-VoIP unterstützen.</span><span class="sxs-lookup"><span data-stu-id="315b5-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="315b5-109">Externe Benutzer, die nicht Mitglied Ihrer Organisation sind, können an lync Server 2013 Besprechungen teilnehmen und anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="315b5-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="315b5-110">Um die Kommunikation über die Firewall Ihrer Organisation hinweg zu unterstützen, stellen Sie lync Server 2013 Edgeserver in Ihrem Umkreisnetzwerk bereit (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="315b5-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="315b5-111">Die Edgeserver steuert, wie Benutzer außerhalb der Firewall eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="315b5-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="315b5-112">Der Edgeserver steuert darüber hinaus die Kommunikation von Benutzern innerhalb der Firewall mit externen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="315b5-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="315b5-113">Je nach Ihren Anforderungen können Sie einen oder mehrere Edgeserver an einem oder mehreren Standorten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="315b5-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="315b5-114">In diesem Abschnitt werden Szenarien für den Zugriff durch externe Benutzer in lync Server 2013 beschrieben, und es wird erläutert, wie Sie die Edge-und Reverse-Proxy Topologie planen.</span><span class="sxs-lookup"><span data-stu-id="315b5-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="315b5-115">Sie benötigen zwar eine Edgeserver zur Unterstützung von Enterprise-VoIP und externer Benutzer Zugriff, dieser Abschnitt konzentriert sich jedoch auf die Unterstützung von Sofortnachrichten, Anwesenheitsinformationen, A/V-Konferenzen, Verbund, Webkonferenzen und lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="315b5-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="315b5-116">Ausführliche Informationen zur Unterstützung von Enterprise-VoIP finden Sie unter <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="315b5-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="315b5-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="315b5-117">In This Section</span></span>

  - [<span data-ttu-id="315b5-118">Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken</span><span class="sxs-lookup"><span data-stu-id="315b5-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="315b5-119">System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="315b5-120">Übersicht über den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="315b5-121">Grundlegendes zur AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="315b5-122">Auswählen einer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="315b5-123">Datensammlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="315b5-124">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="315b5-125">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="315b5-126">Planen von Edgeserver Zertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="315b5-127">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315b5-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

