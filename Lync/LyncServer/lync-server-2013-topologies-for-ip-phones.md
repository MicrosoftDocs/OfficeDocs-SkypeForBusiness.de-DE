---
title: 'Lync Server 2013: Topologien für IP-Telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="bf077-102">Topologien für IP-Telefone in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf077-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf077-103">_**Letztes Änderungsdatum des Themas:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="bf077-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="bf077-104">Dieser Abschnitt bietet einen Überblick über den Verbindungsprozess und erläutert die Unterschiede zwischen der Verbindung eines IP-Telefons in einem internen und einem externen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="bf077-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf077-105">Lync Server bietet Unterstützung für die folgenden IP-Telefone: das Aastra 6721ip-Telefon, das Aastra 6725ip-Telefon, das HP 4110-IP-Telefon (Common Area Phone), das HP 4120 IP-Telefon (Tischtelefon), das Polycom CX600 IP-Tischtelefon, das Polycom CX700-IP-Tischtelefon, Polycom CX500 IP Telefon mit gemeinsamem Bereich und Polycom CX3000 IP-Konferenztelefon.</span><span class="sxs-lookup"><span data-stu-id="bf077-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="bf077-106">Von diesen Telefonen kann nur die Polycom CX700 lync Phone Edition ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf077-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="bf077-107">Das folgende Diagramm beschreibt alle Komponenten, die für die Gerätekonnektivität innerhalb der Unternehmensumgebung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bf077-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="bf077-108">**Interne Topologie**</span><span class="sxs-lookup"><span data-stu-id="bf077-108">**Internal Topology**</span></span>

<span data-ttu-id="bf077-109">![3d88893e-df57-46e3-855a-a1d24589030a] (images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="bf077-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf077-110">Bei der vorherigen Abbildung handelt es sich um eine logische Darstellung, keine physische Übersicht.</span><span class="sxs-lookup"><span data-stu-id="bf077-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="bf077-111">Beispielsweise befindet sich die Active Directory-Domänendienste (AD DS) selten auf demselben Computer wie alle lync Server-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bf077-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="bf077-112">Der Benutzerspeicher kann sich auf dem Back-End-Server oder auf den Archivierungs-und Überwachungs Servern befinden.</span><span class="sxs-lookup"><span data-stu-id="bf077-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="bf077-113">Die lync Server-Verwaltungsshell, Webserver und Updatedienste sind Teil der Front-End-Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="bf077-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="bf077-114">Das folgende Diagramm bietet eine Übersicht über die beteiligten Komponenten, wenn sich das Gerät außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="bf077-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="bf077-115">**Externe Topologie**</span><span class="sxs-lookup"><span data-stu-id="bf077-115">**External Topology**</span></span>

<span data-ttu-id="bf077-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3] (images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="bf077-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf077-117">Der Geräte Update-Webdienst bietet eine externe und interne Website, aber nur die externe Website wird hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf077-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="bf077-118">Der Speicherort der Registrierungsstelle und die URL des Geräte Update-Webdiensts für die Organisation müssen in DNS veröffentlicht werden, wenn externer Zugriff aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf077-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="bf077-119">Darüber hinaus muss der Edgeserver bereitgestellt und ordnungsgemäß konfiguriert werden, um die externe Kommunikation vom Gerät zur Unternehmensumgebung und zurück zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bf077-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="bf077-120">Dies wird im vorherigen Diagramm ausgelassen, da die Edge-Bereitstellung nicht für die Gerätekonnektivität spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="bf077-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

