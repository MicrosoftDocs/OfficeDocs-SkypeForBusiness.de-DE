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
ms.openlocfilehash: 3ad7162dd2e42e8f430adeeaa461a30f77723f05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509692"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="16bee-102">Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16bee-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="16bee-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="16bee-104">Dieser Abschnitt führt Sie durch die Installation von lync Server 2013 und das Einrichten der Serverrollen für die Standard Edition-Server und die Front-End-Pool, einschließlich der Front-End-Server und aller Serverrollen, die mit den Front-End-Servern zusammengesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="16bee-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="16bee-105">Zum Installieren und Einrichten von Serverrollen führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren.</span><span class="sxs-lookup"><span data-stu-id="16bee-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="16bee-106">Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte abzuschließen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, der Konfiguration von Zertifikaten und dem Starten von Diensten.</span><span class="sxs-lookup"><span data-stu-id="16bee-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16bee-107">Bevor Sie Serverrollen einrichten können, müssen Sie eine Topologie erfolgreich veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="16bee-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="16bee-108">Ausführliche Informationen zum Veröffentlichen einer Topologie finden Sie unter <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">finaling and Implementation The Topology Design in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="16bee-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16bee-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="16bee-109">In This Section</span></span>

  - [<span data-ttu-id="16bee-110">Installieren des lokalen Konfigurationsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="16bee-111">Installieren von Server Komponenten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="16bee-112">Konfigurieren von Zertifikaten für Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="16bee-113">Starten von Diensten auf Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="16bee-114">Testen der Pool Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="16bee-115">Testen der Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bee-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

