---
title: 'Lync Server 2013: Erstellen einer Edge-und Director-Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be41eb547589c74b070a55325efcfd05e33f4588
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="23ba1-102">Erstellen einer Edge-und Director-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23ba1-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23ba1-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="23ba1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="23ba1-104">Das Bereitstellen der Topologie umfasst die folgenden Planungs- und Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="23ba1-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="23ba1-105">**Planung**   Sie müssen eine geeignete Topologie für Ihre Organisation definieren und die für die Bereitstellung erforderlichen Komponenten identifizieren.</span><span class="sxs-lookup"><span data-stu-id="23ba1-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="23ba1-106">Dies sind die Standardschritte im Planungsprozess.</span><span class="sxs-lookup"><span data-stu-id="23ba1-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="23ba1-107">Das mit lync Server 2013 bereitgestellte Microsoft lync Server 2013-Planungs Tool erleichtert den Start des Planungsprozesses sowie die Möglichkeit, Änderungen leicht vorzunehmen, wenn Ihre Anforderungen und Pläne abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="23ba1-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="23ba1-108">**Bereitstellung**   die Topologie, die Sie mit dem Topologie-Generator definieren, ist für die Bereitstellungeines beliebigen lync Server 2013 Servers unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="23ba1-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="23ba1-109">Wenn Sie die Definition und Veröffentlichung Ihrer Topologie nicht mit dem Topologie-Generator im Rahmen ihrer Planungsbemühungen abgeschlossen haben, müssen Sie Sie abschließen und die Topologie veröffentlichen, bevor Sie die Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="23ba1-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="23ba1-110">Sie können Edgeserver-Komponenten erst bereitstellen, wenn Sie mindestens einen internen Pool bereitgestellt haben, und Sie müssen den Topologie-Generator installieren, um einen internen Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="23ba1-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="23ba1-111">In diesem Abschnitt wird die Installation des Topologie-Generators nicht behandelt, da dies Teil des Installationsprozesses für den internen Pool ist.</span><span class="sxs-lookup"><span data-stu-id="23ba1-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="23ba1-112">Ausführliche Informationen zu diesen Tools finden Sie unter [Checkliste für die Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="23ba1-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23ba1-113">Wenn Sie zuvor den Topologie-Generator verwendet haben, um eine vollständige Topologie zu definieren, einschließlich der Edge-Topologie, können Sie die <A href="lync-server-2013-define-your-edge-topology.md">Definition ihrer Edge-Topologie in lync Server 2013</A> überspringen und <A href="lync-server-2013-publish-your-topology.md">Ihre Topologie in lync Server 2013</A> Aufgaben in diesem Abschnitt veröffentlichen, aber Sie müssen die <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">lync Server 2013 Topologie exportieren und Sie in externe Medien für die Installation von Edge-Installationen kopieren</A> ausführen.</span><span class="sxs-lookup"><span data-stu-id="23ba1-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="23ba1-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="23ba1-114">In This Section</span></span>

  - [<span data-ttu-id="23ba1-115">Definieren Ihrer Edge-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23ba1-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="23ba1-116">Definieren von optionalen Director-Topologien in Ihrer Topologie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23ba1-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="23ba1-117">Veröffentlichen Ihrer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23ba1-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="23ba1-118">Exportieren der lync Server 2013 Topologie und kopieren auf externe Medien für die Edge-Installation</span><span class="sxs-lookup"><span data-stu-id="23ba1-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

