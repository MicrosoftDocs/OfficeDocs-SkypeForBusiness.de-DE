---
title: 'Lync Server 2013: Anrufsteuerung für einen SIP-Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f60a868a4a77259b358f8ab9d4042bf33c56b044
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="e1fc0-102">Anrufsteuerung für einen SIP-Trunk in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1fc0-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1fc0-103">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e1fc0-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e1fc0-p101">Zur Bereitstellung der Anrufsteuerung für einen SIP-Trunk erstellen Sie einen Netzwerkstandort, der den Anbieter von Internettelefoniediensten repräsentiert. Um Bandbreitenrichtlinienwerte auf den SIP-Trunk anzuwenden, erstellen Sie eine standortübergreifende Richtlinie zwischen dem Netzwerkstandort in Ihrem Unternehmen und dem Netzwerkstandort, der für den Anbieter von Internettelefoniediensten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="e1fc0-106">Die folgende Abbildung zeigt ein Beispiel für die Bereitstellung der Anrufsteuerung für einen SIP-Trunk.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="e1fc0-107">**Konfiguration der Anrufsteuerung für einen SIP-Trunk**</span><span class="sxs-lookup"><span data-stu-id="e1fc0-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="e1fc0-108">![Anrufsteuerung – SIP-Trunking-Diagramm](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Anrufsteuerung – SIP-Trunking-Diagramm")</span><span class="sxs-lookup"><span data-stu-id="e1fc0-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="e1fc0-109">Zur Konfiguration der Anrufsteuerung für einen SIP-Trunk müssen Sie während der Bereitstellung der Anrufsteuerung die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e1fc0-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="e1fc0-110">Erstellen eines Netzwerkstandorts, der den Anbieter von Internettelefoniediensten repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="e1fc0-111">Zuordnen des Netzwerkstandorts zu einer geeigneten Netzwerkregion und Zuweisen eines Bandbreitenwerts von Null für Audio und Video für diesen Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="e1fc0-112">Ausführliche Informationen finden Sie unter [Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e1fc0-113">Für den Anbieter von Internettelefoniediensten ist diese Netzwerkstandortkonfiguration nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="e1fc0-114">Die Bandbreitenrichtlinienwerte werden tatsächlich in Schritt 2 angewendet.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="e1fc0-115">Erstellen Sie eine standortübergreifende Verbindung für den SIP-Trunk unter Verwendung der relevanten Parameterwerte für den in Schritt 1 erstellten Standort.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="e1fc0-116">Verwenden Sie z. B. den Namen des Netzwerkstandorts in Ihrem Unternehmen als Wert des Parameters "NetworkSiteID1" und den ITSP-Netzwerkstandort als Wert des Parameters "NetworkSiteID2".</span><span class="sxs-lookup"><span data-stu-id="e1fc0-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="e1fc0-117">Ausführliche Informationen finden Sie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="e1fc0-118">Lesen Sie auch die lync Server-Verwaltungsshell-Dokumentation für das Cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="e1fc0-119">Lassen Sie sich vom Anbieter der Internettelefoniedienste die IP-Adresse des SBC-Medienendpunkts (Session Border Controller) geben.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="e1fc0-120">Fügen Sie diese IP-Adresse mit der Subnetzmaske 32 zu dem Netzwerkstandort hinzu, der den Anbieter von Internettelefoniediensten repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="e1fc0-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="e1fc0-121">Ausführliche Informationen finden Sie unter Zuordnen eines Subnetzes [zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="e1fc0-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

