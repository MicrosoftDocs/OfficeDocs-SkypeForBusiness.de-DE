---
title: 'Lync Server 2013: Einrichten von Front-End-Servern und Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab21e5933623af58834d3b9effa5ba1e2beecc43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="5274f-102">Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5274f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5274f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5274f-104">Dieser Abschnitt führt Sie durch die Installation von lync Server 2013 und das Einrichten der Serverrollen für den Standard Edition-Server und den Front-End-Pool, einschließlich der Front-End-Server und aller Serverrollen, die mit den Front-End-Servern zusammengesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="5274f-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="5274f-105">Zum Installieren und Einrichten von Serverrollen führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren.</span><span class="sxs-lookup"><span data-stu-id="5274f-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="5274f-106">Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte abzuschließen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, der Konfiguration von Zertifikaten und dem Starten von Diensten.</span><span class="sxs-lookup"><span data-stu-id="5274f-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5274f-107">Bevor Sie Serverrollen einrichten können, müssen Sie eine Topologie erfolgreich veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="5274f-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="5274f-108">Details zum Veröffentlichen einer Topologie finden Sie unter <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalisieren und Implementieren des Topologie-Designs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5274f-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5274f-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5274f-109">In This Section</span></span>

  - [<span data-ttu-id="5274f-110">Installieren des lokalen Konfigurationsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="5274f-111">Installieren von Serverkomponenten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="5274f-112">Konfigurieren von Zertifikaten für Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="5274f-113">Starten von Diensten auf Servern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="5274f-114">Testen der Poolbereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="5274f-115">Testen des Standard Edition-Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5274f-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

