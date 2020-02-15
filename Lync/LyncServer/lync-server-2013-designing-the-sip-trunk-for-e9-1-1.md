---
title: 'Lync Server 2013: Entwerfen des SIP-Trunks für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8daf27670f7820a64cd7a91fe350ba7345c9463e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="1ed4a-102">Entwerfen des SIP-Trunks für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed4a-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed4a-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1ed4a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1ed4a-104">Lync Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1 -1-Dienstanbieter zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="1ed4a-105">Sie können Notfalldienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jedem Zweigstellenstandort einrichten.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="1ed4a-106">Wenn jedoch die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, der den SIP-Trunk Dienst hostet, nicht verfügbar ist, benötigt ein Anruf, der von einem Benutzer am getrennten Standort getätigt wird, einen speziellen Telefonverwendungseintrag in der VoIP-Richtlinie des Benutzers, der den Anruf an den ECRC über das lokale PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1ed4a-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="1ed4a-107">Das gleiche gilt, wenn die Anrufsteuerung gleichzeitige Anruf Grenzwerte wirksam macht.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ed4a-108">Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer lync Server Umgebung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="1ed4a-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1ed4a-109">Verwenden Sie mehrfach vernetzte Vermittlungsserver, die ihre nach außen gerichteten öffentlich weitergeleiteten Schnittstellen verwenden, um mit dem SIP-Trunk Anbieter zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="1ed4a-110">Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren Abgrenzungs Pfad zwischen den Vermittlungsservern und den Diensten des SIP-Trunk Anbieters bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="1ed4a-111">Wenn Sie die letztere Methode auswählen, müssen Sie sicherstellen, dass die von Ihnen ausgewählte SBC-Marke und das Modell zertifiziert wurden und unterstützt die Übergabe von Anwesenheitsinformationen im Daten Format Location-Objekt (PIDF-Lo) als Teil der SIP-INVITE-Daten.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="1ed4a-112">Andernfalls werden die Anrufe bei dem Notrufdienst Anbieter eintreffen, der von den Standortinformationen entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="1ed4a-113">Ausführliche Informationen zu zertifizierten SBCS finden Sie unter "qualifizierte Infrastruktur für Microsoft lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>" unter.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="1ed4a-114">Mit E9-1-1-Dienstanbietern erhalten Sie Zugriff auf ein SBCS-Paar für Redundanz.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="1ed4a-115">Sie müssen mehrere Entscheidungen hinsichtlich der Vermittlungsserver Topologie und der Anruf Weiterleitungskonfiguration treffen.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="1ed4a-116">Werden Sie beide SBCS als gleichwertige Peers behandeln und das Round-Robin-Routing für Anrufe zwischen Ihnen verwenden, oder werden Sie einen SBC als primären und den anderen als sekundären angeben?</span><span class="sxs-lookup"><span data-stu-id="1ed4a-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="1ed4a-117">Ausführliche Informationen zum Bereitstellen eines SIP-Trunks in lync Server finden Sie unter [wie kann ich SIP-Trunking in lync Server 2013 implementieren?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="1ed4a-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="1ed4a-118">Die folgenden Fragen helfen Ihnen bei der Entscheidung, wie die SIP-Trunks für E9-1-1 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="1ed4a-119">**Sollten Sie den SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="1ed4a-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="1ed4a-120">Es ist wichtig, dass Notrufe immer eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-120">It is important that emergency calls always connect.</span></span> <span data-ttu-id="1ed4a-121">Eine dedizierte Leitung bietet eine Verbindung, die nicht von anderen Datenverkehr im Netzwerk getrennt wird, und bietet Ihnen die Möglichkeit zur Implementierung von Quality of Service (QoS).</span><span class="sxs-lookup"><span data-stu-id="1ed4a-121">A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS).</span></span> <span data-ttu-id="1ed4a-122">Denken Sie daran, dass die IPSec-Verschlüsselung erforderlich ist, wenn Sie über das öffentliche Internet eine Verbindung mit Dienstanbietern für die Notfalldienste herstellen und die Vertraulichkeit von Notrufen sicherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-122">Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="1ed4a-123">**Ist Ihre E9-1-1-Bereitstellung für die Notfalltoleranz ausgelegt?**</span><span class="sxs-lookup"><span data-stu-id="1ed4a-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="1ed4a-124">Da es sich hierbei um eine Notfalllösung handelt, ist die Ausfallsicherheit wichtig.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="1ed4a-125">Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Trunks an Notfall toleranten Speicherorten bereit.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="1ed4a-126">Es empfiehlt sich, die primäre Vermittlungsserver bereitzustellen, die den von ihr unterstützten Benutzern am nächsten ist, und Failover-Anrufe über das sekundäre Vermittlungsserver (an einem anderen geografischen Standort) weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="1ed4a-127">**Sollten Sie einen separaten SIP-Trunk für jede Zweigstelle bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="1ed4a-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="1ed4a-128">Lync Server bietet verschiedene Strategien für die Handhabung von VoIP-Ausfallsicherheit in Zweigstellen, darunter: belastbare Datennetzwerke, Bereitstellungeines SIP-Trunks in jeder Filiale oder Pushen von Anrufen beim lokalen Gateway während Ausfällen.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="1ed4a-129">Ausführliche Informationen finden Sie unter [Branch Site SIP Trunking in lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="1ed4a-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="1ed4a-130">**Ist die Anrufsteuerung (Call Admission Control, CAC) aktiviert?**</span><span class="sxs-lookup"><span data-stu-id="1ed4a-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="1ed4a-131">In lync Server werden Notrufe nicht anders als bei normalen anrufen behandelt.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="1ed4a-132">Aus diesem Grund kann sich die Bandbreitenverwaltung oder die Anrufsteuerung (Call Admission Control, CAC) negativ auf eine E9-1-1-Konfiguration auswirken.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="1ed4a-133">Notfallanrufe werden blockiert oder an das lokale PSTN-Gateway weitergeleitet, wenn eine Anrufsteuerung aktiviert ist und die konfigurierte Grenze für einen Link überschritten wird, an dem Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="1ed4a-134">Wie weiter oben in diesem Thema erwähnt, werden solche Anrufe keine Standortdaten haben und müssen manuell an die ECRC weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1ed4a-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

