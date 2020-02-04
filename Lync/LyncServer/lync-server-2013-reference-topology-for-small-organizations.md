---
title: Lync Server 2013-Referenztopologie für kleine Organisationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="433e4-102">Referenztopologie für lync Server 2013 in kleinen Organisationen</span><span class="sxs-lookup"><span data-stu-id="433e4-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="433e4-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="433e4-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="433e4-104">Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine robuste, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server mit lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="433e4-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="433e4-105">**Referenztopologie für kleine Organisationen**</span><span class="sxs-lookup"><span data-stu-id="433e4-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="433e4-106">![Referenztopologie mit drei Servern (Diagramm)](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Referenztopologie mit drei Servern (Diagramm)")</span><span class="sxs-lookup"><span data-stu-id="433e4-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="433e4-107">**Paar von Standard Edition-Servern**     , die diese Organisation bereitgestellt hat, hat 4.000-Benutzer an Ihrem zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="433e4-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="433e4-108">Die Organisation hat zwei Standard Edition-Server bereitgestellt und kombiniert, um eine höhere Verfügbarkeit und Disaster Recovery zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="433e4-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="433e4-109">Jeder Server verfügt über 2.000-Benutzer, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="433e4-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="433e4-110">Wenn einer ausfällt, kann ein Administrator für diese Benutzer einen Failover durchführen, um von dem anderen Server bedient zu werden, mit einem mindestunterbrechungs Intervall für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="433e4-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="433e4-111">Weitere Informationen zu Funktionen für die Hochverfügbarkeits-und Disaster Recovery in lync Server 2013 finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="433e4-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="433e4-112">**Die Bereitstellung von Edge-Servern wird empfohlen.**    Obwohl die Bereitstellungeines Edgeserver für interne Chats, Anwesenheitsfunktionen und Konferenzen nicht erforderlich ist, empfehlen wir dies auch für kleine Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="433e4-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="433e4-113">Sie können Ihre lync Server-Investition maximieren, indem Sie einen Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="433e4-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="433e4-114">Dies bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="433e4-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="433e4-115">Die eigenen Benutzer Ihrer Organisation können die lync-Server Funktionalität verwenden, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.</span><span class="sxs-lookup"><span data-stu-id="433e4-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="433e4-116">Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.</span><span class="sxs-lookup"><span data-stu-id="433e4-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="433e4-117">Wenn Sie über einen Partner, einen Kreditor oder eine Kundenorganisation verfügen, die ebenfalls lync Server verwendet, können Sie eine *Verbundbeziehung* mit dieser Organisation bilden.</span><span class="sxs-lookup"><span data-stu-id="433e4-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="433e4-118">Ihre lync Server-Bereitstellung erkennt dann Benutzer aus dieser Verbundorganisation, was zu einer besseren Zusammenarbeit führt.</span><span class="sxs-lookup"><span data-stu-id="433e4-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="433e4-119">Ihre Benutzer können Sofortnachrichten mit Benutzern von öffentlichen Chat Diensten austauschen, einschließlich einer oder aller der folgenden: Windows Live, AOL, Yahoo\!und Google Talk.</span><span class="sxs-lookup"><span data-stu-id="433e4-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="433e4-120">Für die Konnektivität öffentlicher Chats mit diesen Diensten ist möglicherweise eine separate Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="433e4-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="433e4-121">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="433e4-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="433e4-122">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="433e4-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="433e4-123">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="433e4-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="433e4-124">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="433e4-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="433e4-125">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="433e4-125">has been announced.</span></span> <span data-ttu-id="433e4-126">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="433e4-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="433e4-127">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="433e4-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="433e4-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="433e4-128">Messenger.</span></span> <span data-ttu-id="433e4-129">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="433e4-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="433e4-130">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="433e4-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="433e4-131">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="433e4-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="433e4-132">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="433e4-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="433e4-133">**Überlebensfähigkeit der Verzweigungs Website.**    In dieser Organisation wird ein Pilotprogramm des Enterprise-VoIP-Features von lync Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="433e4-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="433e4-134">Einige Benutzer verwenden lync Server als einzige Sprachlösung.</span><span class="sxs-lookup"><span data-stu-id="433e4-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="433e4-135">Einige dieser sprach Pilotbenutzer befinden sich auf der Zweigstelle.</span><span class="sxs-lookup"><span data-stu-id="433e4-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="433e4-136">Die Verzweigungs Website verfügt nicht über einen zuverlässigen WAN-Link (Wide Area Network) mit dem zentralen Standort, daher wird eine Survivable Branch-Appliance dort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="433e4-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="433e4-137">Dank der Survivable Branch-Anwendung können die Benutzer in der Zweigstelle bei Ausfall der WAN-Verbindung weiterhin Anrufe tätigen und entgegennehmen (sowohl innerhalb der Organisation als auch über das Festnetz), die Voicemailfunktion nutzen und per Chat kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="433e4-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="433e4-138">Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="433e4-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="433e4-139">**Exchange UM-Bereitstellung.**</span><span class="sxs-lookup"><span data-stu-id="433e4-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="433e4-140">Diese Referenztopologie umfasst einen Exchange Unified Messaging (um)-Server, auf dem Microsoft Exchange Server ausgeführt wird, nicht lync Server.</span><span class="sxs-lookup"><span data-stu-id="433e4-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="433e4-141">Ausführliche Informationen zu Exchange um finden Sie unter [Planen der Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [gehostete Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planning-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="433e4-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="433e4-142">**Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="433e4-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="433e4-143">Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="433e4-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="433e4-144">Mit Office Web Apps Server können PowerPoint-Folien in Webkonferenzen präsentiert werden.</span><span class="sxs-lookup"><span data-stu-id="433e4-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="433e4-145">Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="433e4-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

