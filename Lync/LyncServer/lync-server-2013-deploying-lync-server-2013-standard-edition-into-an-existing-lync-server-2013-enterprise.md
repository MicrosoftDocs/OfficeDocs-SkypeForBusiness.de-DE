---
title: 'Lync Server 2013: Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="45b31-102">Bereitstellen von Lync Server 2013 Standard Edition in einer vorhandenen Lync Server 2013 Enterprise-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="45b31-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45b31-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="45b31-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="45b31-104">Die Bereitstellungeines Standard Edition-Servers in einer vorhandenen Enterprise Edition-Bereitstellung ähnelt der Bereitstellung zusätzlicher Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="45b31-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="45b31-105">Ein Standard Edition-Server kann auf einer anderen Website bereitgestellt werden, sodass die Benutzer auf dieser Website auf dem Standard Edition-Server statt im Front-End-Pool über ein WAN (Wide Area Network) verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="45b31-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="45b31-106">Die Verfahren zum Installieren der neuen Website und der neuen Server auf dieser Website sind bereits in anderen Abschnitten der [Bereitstellung von lync Server 2013](lync-server-2013-deploying-lync-server.md) -Dokumentation definiert.</span><span class="sxs-lookup"><span data-stu-id="45b31-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="45b31-107">**So definieren Sie eine neue Website**</span><span class="sxs-lookup"><span data-stu-id="45b31-107">**To define a new site**</span></span>

1.  <span data-ttu-id="45b31-108">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="45b31-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="45b31-109">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **neue zentrale Website**.</span><span class="sxs-lookup"><span data-stu-id="45b31-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="45b31-110">Geben Sie auf der Seite **Website identifizieren** einen Namen für die Website ein, und geben Sie optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="45b31-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="45b31-111">Befolgen Sie die Verfahren zum Definieren der restlichen Website Topologie.</span><span class="sxs-lookup"><span data-stu-id="45b31-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="45b31-112">Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="45b31-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="45b31-113">Veröffentlichen der aktualisierten Topologie</span><span class="sxs-lookup"><span data-stu-id="45b31-113">Publish the updated topology.</span></span> <span data-ttu-id="45b31-114">Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="45b31-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="45b31-115">Einrichten und Installieren eines Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="45b31-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="45b31-116">Wenn Sie eine Umgebung mit nur einem Standard Edition-Server bereitgestellt haben, hätten Sie den Setup-Vorgang mit dem lync Server-Bereitstellungs-Assistenten begonnen, indem Sie den Link <STRONG>First Standard Edition-Server vorbereiten</STRONG> verwenden, um die anfänglichen Datenbankdateien auf dem neuen Standard Edition-Server zu installieren.</span><span class="sxs-lookup"><span data-stu-id="45b31-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="45b31-117">Führen Sie diesen Vorgang <STRONG>nicht</STRONG> aus, wenn Sie einen Standard Edition-Server in einer vorhandenen lync Server 2013-Bereitstellung installieren.</span><span class="sxs-lookup"><span data-stu-id="45b31-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

