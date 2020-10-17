---
title: Lync Server 2013 Referenztopologie für kleine Organisationen
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
ms.openlocfilehash: 68163756f2c2153d1e164999532bc6265400ac5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536732"
---
# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="57e4a-102">Referenztopologie für lync Server 2013 in kleinen Organisationen</span><span class="sxs-lookup"><span data-stu-id="57e4a-102">Reference topology for Lync Server 2013 in small organizations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57e4a-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="57e4a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="57e4a-104">Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine stabile, hoch verfügbare Lösung bereitstellen können, indem Sie nur drei Server mit lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="57e4a-105">**Referenztopologie für kleine Organisationen**</span><span class="sxs-lookup"><span data-stu-id="57e4a-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="57e4a-106">![Referenztopologie Bereitstellen von drei Server Diagrammen](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Referenztopologie Bereitstellen von drei Server Diagrammen")</span><span class="sxs-lookup"><span data-stu-id="57e4a-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="57e4a-107">**Paar von Standard Edition-Servern, die bereitgestellt werden**     Diese Organisation verfügt über 4.000 Benutzer am zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="57e4a-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="57e4a-108">Die Organisation hat zwei Standard Edition-Server bereitgestellt und kombiniert, um hohe Verfügbarkeit und Notfallwiederherstellung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="57e4a-109">Jeder Server Homes 2.000 Benutzer, aber Informationen zu allen Benutzern werden zwischen den beiden Servern synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="57e4a-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="57e4a-110">Wenn eine ausfällt, kann ein Administrator ein Failover für diese Benutzer durchführen, um von dem anderen Server bedient zu werden, mit einem Minimum an Unterbrechungen für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="57e4a-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="57e4a-111">Weitere Informationen zu Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013 finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="57e4a-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="57e4a-112">**Edgeserver Bereitstellung wird empfohlen.**     Obwohl die Bereitstellungeines Edgeserver für interne Sofortnachrichten, Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird dies auch für kleine Bereitstellungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="57e4a-113">Sie können Ihre lync Server Investition maximieren, indem Sie eine Edgeserver bereitstellen, um die Dienste für Benutzer bereitzustellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="57e4a-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="57e4a-114">Hierdurch bieten sich folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="57e4a-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="57e4a-115">Die eigenen Benutzer Ihrer Organisation können lync Server Funktionalität verwenden, wenn Sie von zu Hause aus arbeiten oder unterwegs sind.</span><span class="sxs-lookup"><span data-stu-id="57e4a-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="57e4a-116">Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="57e4a-117">Wenn Sie über einen Partner, einen Anbieter oder eine Kundenorganisation verfügen, die auch lync Server verwendet, können Sie eine *Verbundbeziehung* mit dieser Organisation bilden.</span><span class="sxs-lookup"><span data-stu-id="57e4a-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="57e4a-118">Ihre lync Server-Bereitstellung würde dann Benutzer aus dieser Verbundorganisation erkennen, was zu einer besseren Zusammenarbeit führt.</span><span class="sxs-lookup"><span data-stu-id="57e4a-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="57e4a-119">Ihre Benutzer können Sofortnachrichten mit Benutzern von öffentlichen Instant Messaging-Diensten austauschen, einschließlich einer oder aller der folgenden: Windows Live, AOL, Yahoo \! und Google Talk.</span><span class="sxs-lookup"><span data-stu-id="57e4a-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="57e4a-120">Für öffentliche Chat Verbindungen mit diesen Diensten ist möglicherweise eine separate Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="57e4a-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="57e4a-121">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57e4a-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="57e4a-122">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="57e4a-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="57e4a-123">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="57e4a-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="57e4a-124">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="57e4a-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="57e4a-125">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="57e4a-125">has been announced.</span></span> <span data-ttu-id="57e4a-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57e4a-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="57e4a-127">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="57e4a-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="57e4a-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="57e4a-128">Messenger.</span></span> <span data-ttu-id="57e4a-129">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="57e4a-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="57e4a-130">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="57e4a-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="57e4a-131">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="57e4a-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="57e4a-132">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="57e4a-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="57e4a-133">Überlebensfähigkeit von **Zweigstellen Websites.**     In dieser Organisation wird ein Pilotprogramm der Enterprise-VoIP-Funktion von lync Server durchführen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="57e4a-134">Einige Benutzer verwenden lync Server als einzige Sprachlösung.</span><span class="sxs-lookup"><span data-stu-id="57e4a-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="57e4a-135">Einige dieser VoIP-Pilotbenutzer befinden sich am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="57e4a-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="57e4a-136">Der Zweigstellenstandort verfügt nicht über eine zuverlässige WAN-Verbindung (Wide Area Network) mit dem zentralen Standort, sodass ein Survivable Branch Appliance dort bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="57e4a-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="57e4a-137">Wenn die WAN-Verbindung ausfällt, können Benutzer am Zweigstellenstandort weiterhin Anrufe tätigen und empfangen (beide Anrufe innerhalb der Organisation und PSTN-Anrufe), über Voicemailfunktionen verfügen und mit Instant Messaging (Sofortnachrichten) mit zwei Teilnehmern kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="57e4a-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="57e4a-138">Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="57e4a-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="57e4a-139">**Exchange UM-Bereitstellung.**</span><span class="sxs-lookup"><span data-stu-id="57e4a-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="57e4a-140">Diese Referenztopologie umfasst einen Exchange Unified Messaging (um) Server, der Exchange Server und nicht lync Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="57e4a-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="57e4a-141">Ausführliche Informationen zu Exchange um finden Sie unter [Planning for Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messagingintegration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="57e4a-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="57e4a-142">**Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="57e4a-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="57e4a-143">Wir empfehlen die Bereitstellung eines Office Web Apps Servers oder einer Office Web Apps Server-Farm in allen Organisation, die Webkonferenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="57e4a-144">Office-webapps-Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="57e4a-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="57e4a-145">Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="57e4a-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

