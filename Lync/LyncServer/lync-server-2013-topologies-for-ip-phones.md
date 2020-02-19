---
title: 'Lync Server 2013: Topologien für IP-Telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b01e4d98ced806b40cd5f092c0b8051ce86f47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="9f00d-102">Topologien für IP-Telefone in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f00d-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f00d-103">_**Letztes Änderungsstand des Themas:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="9f00d-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="9f00d-104">In diesem Abschnitt erhalten Sie einen Überblick über den Prozess der Verbindungsherstellung. Erklärt werden außerdem die Unterschiede zwischen dem Herstellen einer Verbindung über ein IP-Telefon in einem internen Netzwerk und dem gleichen Vorgang in einem externen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="9f00d-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f00d-105">Lync Server bietet Unterstützung für die folgenden IP-Telefone: das Mobiltelefon Aastra 6721ip, das Aastra 6725ip-Telefon, das HP 4110-IP-Telefon (Telefon im öffentlichen Bereich), das HP 4120-IP-Telefon (Schreibtisch Telefon), Polycom CX600 IP-Telefon, Polycom CX700-IP-Tischtelefon, Polycom CX500-IP Telefon mit öffentlichem Bereich und Polycom CX3000 IP-Konferenztelefon.</span><span class="sxs-lookup"><span data-stu-id="9f00d-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="9f00d-106">Von diesen Telefonen können alle außer dem Polycom CX700 lync Phone Edition ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f00d-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="9f00d-107">Im folgenden Diagramm werden alle Komponenten beschrieben, die an der Geräteanbindung innerhalb einer Unternehmensumgebung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="9f00d-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="9f00d-108">**Interne Topologie**</span><span class="sxs-lookup"><span data-stu-id="9f00d-108">**Internal Topology**</span></span>

<span data-ttu-id="9f00d-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="9f00d-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f00d-110">Die obige Abbildung ist eine logische Darstellung und keine physische.</span><span class="sxs-lookup"><span data-stu-id="9f00d-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="9f00d-111">Beispielsweise befindet sich Active Directory-Domänendienste (AD DS) selten auf demselben Computer wie alle lync Server-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f00d-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="9f00d-112">Der Benutzerspeicher kann sich auf dem Back-End-Server oder auf den Archivierungs- und Monitoring Servern befinden.</span><span class="sxs-lookup"><span data-stu-id="9f00d-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="9f00d-113">Die lync Server-Verwaltungsshell-, Webserver-und Updatedienste sind Teil der Front-End-Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="9f00d-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="9f00d-114">Das folgende Diagramm zeigt einen Überblick über die Komponenten, die beteiligt sind, wenn das Gerät sich außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="9f00d-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="9f00d-115">**Externe Topologie**</span><span class="sxs-lookup"><span data-stu-id="9f00d-115">**External Topology**</span></span>

<span data-ttu-id="9f00d-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="9f00d-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f00d-117">Der Geräteupdate-Webdienst stellt eine externe und eine interne Website bereit, hier wird jedoch nur die externe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f00d-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="9f00d-p103">Der Standort der Registrierungsstelle und die URL des Geräteupdate-Webdiensts für die Organisation müssen in DNS veröffentlicht werden, wenn Zugriff durch externe Benutzer unterstützt werden soll. Außerdem muss der Edgeserver bereitgestellt und korrekt konfiguriert werden, damit externe Kommunikation vom Gerät zur Unternehmensumgebung und zurück möglich ist. Dies wird im obigen Diagramm nicht dargestellt, da die Edgebereitstellung nicht spezifisch für die Geräteanbindung ist.</span><span class="sxs-lookup"><span data-stu-id="9f00d-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

