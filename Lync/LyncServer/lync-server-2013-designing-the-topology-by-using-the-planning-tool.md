---
title: 'Lync Server 2013: Entwerfen der Topologie mithilfe des Planungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="93fbf-102">Entwerfen der Topologie für lync Server 2013 mithilfe des Planungstools</span><span class="sxs-lookup"><span data-stu-id="93fbf-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93fbf-103">_**Letztes Änderungsdatum des Themas:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="93fbf-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="93fbf-104">Das Planungstool für Microsoft lync Server 2013 ist ein Assistenten gesteuertes, Interview ähnliches Tool, in dem Fragen zur lync Server 2013-Topologie gestellt werden, die Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="93fbf-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="93fbf-105">Das Planungs Tool verwendet die bereitgestellten Informationen in Verbindung mit den bevorzugten Methoden für Topologie-Design und-Kapazität, um eine empfohlene Topologie basierend auf den bereitgestellten Antworten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="93fbf-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="93fbf-106">Sie können das Planungs Tool aus dem Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="93fbf-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="93fbf-107">Das Ziel des Planungstools besteht letztendlich darin, die potenzielle Komplexität beim Entwerfen einer vollständigen lync Server 2013-Topologie zu verringern.</span><span class="sxs-lookup"><span data-stu-id="93fbf-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="93fbf-108">Das Tool stellt außerdem kontextbezogene Verweise auf die im Tool enthaltene Planungs- und Bereitstellungsdokumentation bereit, sofern eine Internetverbindung zur Microsoft TechNet-Website verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="93fbf-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="93fbf-109">Nach dem Anpassen der Topologie mit den TCP/IP-Adressen der Infrastruktur und den vollqualifizierten Domänennamen (FQDNs) stellt das Planungs Tool eine Reihe von Berichten zur Verfügung, die DNS-Benennung (Domain Name System), Firewallregeln, Zertifikate und vieles mehr beinhalten.</span><span class="sxs-lookup"><span data-stu-id="93fbf-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="93fbf-110">Das Planungs Tool bietet auch die Möglichkeit, Informationen in zwei Formaten zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="93fbf-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="93fbf-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="93fbf-111">Microsoft Excel</span></span>

  - <span data-ttu-id="93fbf-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="93fbf-112">Microsoft Visio</span></span>

<span data-ttu-id="93fbf-113">In den folgenden Themen wird das Planungs Tool vorgestellt und detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93fbf-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93fbf-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="93fbf-114">In This Section</span></span>

  - [<span data-ttu-id="93fbf-115">Installieren des Planungstools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="93fbf-116">Installieren von optionaler Software in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="93fbf-117">Navigieren im Planungs Tool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="93fbf-118">Erstellen des anfänglichen Topologie-Designs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="93fbf-119">Überprüfen der Administratorberichte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93fbf-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93fbf-120">See Also</span></span>


[<span data-ttu-id="93fbf-121">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="93fbf-122">Planen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93fbf-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

