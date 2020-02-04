---
title: 'Lync Server 2013: Einrichten von Front-End-Servern und Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b912eca536960bccc09c5e7a14c9adc245fe69e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="76bb5-102">Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76bb5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="76bb5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="76bb5-104">Dieser Abschnitt führt Sie durch die Installation von lync Server 2013 und das Einrichten der Serverrollen für den Standard Edition-Server und den Front-End-Pool, einschließlich der Front-End-Server und aller Serverrollen, die mit den Front-End-Servern zusammengesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="76bb5-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="76bb5-105">Zum Installieren und Einrichten von Serverrollen führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren.</span><span class="sxs-lookup"><span data-stu-id="76bb5-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="76bb5-106">Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte abzuschließen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, der Konfiguration von Zertifikaten und dem Starten von Diensten.</span><span class="sxs-lookup"><span data-stu-id="76bb5-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76bb5-107">Bevor Sie Serverrollen einrichten können, müssen Sie eine Topologie erfolgreich veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="76bb5-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="76bb5-108">Details zum Veröffentlichen einer Topologie finden Sie unter <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalisieren und Implementieren des Topologie-Designs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="76bb5-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76bb5-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="76bb5-109">In This Section</span></span>

  - [<span data-ttu-id="76bb5-110">Installieren des lokalen Konfigurationsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="76bb5-111">Installieren von Serverkomponenten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="76bb5-112">Konfigurieren von Zertifikaten für Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="76bb5-113">Starten von Diensten auf Servern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="76bb5-114">Testen der Poolbereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="76bb5-115">Testen des Standard Edition-Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bb5-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

