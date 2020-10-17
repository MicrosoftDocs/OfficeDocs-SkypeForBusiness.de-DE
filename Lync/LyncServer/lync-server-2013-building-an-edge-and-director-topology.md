---
title: 'Lync Server 2013: Erstellen einer Edge-und Director-Topologie'
description: 'Lync Server 2013: Erstellen einer Edge-und Director-Topologie.'
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
ms.openlocfilehash: bcb2d422136cf0a421c68ebc2adba50f03c5cc85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569271"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="88525-103">Erstellen einer Edge-und Director-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88525-103">Building an edge and Director topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88525-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="88525-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="88525-105">Das Bereitstellen der Topologie umfasst die folgenden Planungs- und Bereitstellungsaufgaben:</span><span class="sxs-lookup"><span data-stu-id="88525-105">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="88525-106">**Planung**     Sie müssen eine geeignete Topologie für Ihre Organisation definieren und die für die Bereitstellung erforderlichen Komponenten identifizieren.</span><span class="sxs-lookup"><span data-stu-id="88525-106">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="88525-107">Dies sind die Standardschritte im Planungsprozess.</span><span class="sxs-lookup"><span data-stu-id="88525-107">These are standard steps in the planning process.</span></span> <span data-ttu-id="88525-108">Das mit lync Server 2013 bereitgestellte Microsoft lync Server 2013-Planungs Tool erleichtert den Start des Planungsprozesses sowie die Möglichkeit, Änderungen leicht vorzunehmen, wenn Ihre Anforderungen und Pläne abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="88525-108">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="88525-109">**Bereitstellung**     Die Topologie, die Sie mit dem Topologie-Generator definieren, ist für die Bereitstellungeines beliebigen lync Server 2013 Servers unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="88525-109">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="88525-110">Wenn Sie die Definition und Veröffentlichung Ihrer Topologie nicht mit dem Topologie-Generator im Rahmen ihrer Planungsbemühungen abgeschlossen haben, müssen Sie Sie abschließen und die Topologie veröffentlichen, bevor Sie die Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="88525-110">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="88525-111">Sie können Edgeserver-Komponenten erst bereitstellen, wenn Sie mindestens einen internen Pool bereitgestellt haben, und Sie müssen den Topologie-Generator installieren, um einen internen Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="88525-111">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="88525-112">In diesem Abschnitt wird die Installation des Topologie-Generators nicht behandelt, da dies Teil des Installationsprozesses für den internen Pool ist.</span><span class="sxs-lookup"><span data-stu-id="88525-112">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="88525-113">Ausführliche Informationen zu diesen Tools finden Sie unter [Checkliste für die Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="88525-113">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88525-114">Wenn Sie zuvor den Topologie-Generator verwendet haben, um eine vollständige Topologie zu definieren, einschließlich der Edge-Topologie, können Sie die <A href="lync-server-2013-define-your-edge-topology.md">Definition ihrer Edge-Topologie in lync Server 2013</A> überspringen und <A href="lync-server-2013-publish-your-topology.md">Ihre Topologie in lync Server 2013</A> Aufgaben in diesem Abschnitt veröffentlichen, aber Sie müssen die <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">lync Server 2013 Topologie exportieren und Sie in externe Medien für die Installation von Edge-Installationen kopieren</A> ausführen.</span><span class="sxs-lookup"><span data-stu-id="88525-114">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88525-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="88525-115">In This Section</span></span>

  - [<span data-ttu-id="88525-116">Definieren Ihrer Edge-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88525-116">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="88525-117">Definieren von optionalen Director-Topologien in Ihrer Topologie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88525-117">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="88525-118">Veröffentlichen Ihrer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88525-118">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="88525-119">Exportieren der lync Server 2013 Topologie und kopieren auf externe Medien für die Edge-Installation</span><span class="sxs-lookup"><span data-stu-id="88525-119">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

