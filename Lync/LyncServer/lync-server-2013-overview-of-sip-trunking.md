---
title: 'Lync Server 2013: Übersicht über SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="277d2-102">Übersicht über SIP-Trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="277d2-102">Overview of SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277d2-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="277d2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="277d2-p101">Die Bereitstellung von SIP-Trunking kann die Telefonkommunikation in Ihrer Organisation deutlich vereinfachen und stellt gleichzeitig eine Vorbereitung auf die neuesten Funktionen für die Echtzeitkommunikation dar. Einer der Hauptvorteile beim SIP-Trunking besteht darin, dass Sie PSTN-Verbindungen (Public Switched Telephone Network, Telefonfestnetz) an einem zentralen Standort in Ihrer Organisation konsolidieren können – im Gegensatz zum Vorgänger, dem TDM (Time Division Multiplexing)-Trunking, das in der Regel einen separaten Trunk für jeden Zweigstellenstandort erfordert.</span><span class="sxs-lookup"><span data-stu-id="277d2-p101">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications. One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="277d2-106">SIP-Trunking in lync Server</span><span class="sxs-lookup"><span data-stu-id="277d2-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="277d2-107">Die lync Server 2013 SIP-Trunking-Funktionen ermöglichen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="277d2-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="277d2-108">Ein Enterprise-Benutzer, ob innerhalb oder außerhalb der Unternehmensfirewall, kann einen Orts-oder Ferngespräch führen, das durch eine E. 164-konforme Nummer festgelegt ist, die im PSTN als Dienst des entsprechenden Dienstanbieters beendet wird.</span><span class="sxs-lookup"><span data-stu-id="277d2-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="277d2-109">Jeder PSTN-Abonnent kann mit einem Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall Kontakt aufnehmen, indem er eine direkte Durchwahl (DID) wählt, die dem Unternehmensbenutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="277d2-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="277d2-110">Kosteneinsparung</span><span class="sxs-lookup"><span data-stu-id="277d2-110">Cost Savings</span></span>

<span data-ttu-id="277d2-111">Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:</span><span class="sxs-lookup"><span data-stu-id="277d2-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="277d2-112">Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.</span><span class="sxs-lookup"><span data-stu-id="277d2-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="277d2-113">Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.</span><span class="sxs-lookup"><span data-stu-id="277d2-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="277d2-p102">Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen einem SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ITSP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)</span><span class="sxs-lookup"><span data-stu-id="277d2-p102">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="277d2-118">SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="277d2-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="277d2-p103">Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen.</span><span class="sxs-lookup"><span data-stu-id="277d2-p103">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="277d2-121">Erweiterte VoIP-Dienste</span><span class="sxs-lookup"><span data-stu-id="277d2-121">Expanded VoIP Services</span></span>

<span data-ttu-id="277d2-122">VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar.</span><span class="sxs-lookup"><span data-stu-id="277d2-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="277d2-123">Mit SIP-Trunking können Sie VoIP-Funktionen erweitern und lync Server 2013 die Bereitstellung umfassender Dienstleistungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="277d2-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="277d2-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="277d2-124">For example:</span></span>

  - <span data-ttu-id="277d2-125">Die verbesserte Anwesenheitserkennung für Geräte, auf denen lync Server 2013 nicht ausgeführt wird, kann eine bessere Integration mit Mobiltelefonen ermöglichen, sodass Sie sehen können, wenn ein Benutzer einen Mobiltelefon Anruf führt.</span><span class="sxs-lookup"><span data-stu-id="277d2-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="277d2-126">E9-1-1-Notrufdienste ermöglichen der Rettungsleitstelle, die einen Notruf entgegennimmt, den geografischen Standort des Anrufers anhand seiner Telefonnummer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="277d2-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="277d2-127">Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="277d2-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

