---
title: 'Lync Server 2013: Bereitstellen lync Server 2013 Standard Edition in einem vorhandenen lync Server 2013 Unternehmen'
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
ms.openlocfilehash: cd3d666eefe04a6650a5c1a10253f490e391ff22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501512"
---
# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="49eca-102">Bereitstellen lync Server 2013 Standard Edition in einem vorhandenen lync Server 2013 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49eca-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49eca-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="49eca-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="49eca-104">Das Bereitstelleneiner Standard Edition-Server in einer vorhandenen Enterprise Edition-Bereitstellung ähnelt dem Bereitstellen zusätzlicher Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="49eca-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="49eca-105">Ein Standard Edition-Server kann an einer anderen Website bereitgestellt werden, sodass Benutzer an dieser Website auf dem Standard Edition-Server statt auf der Front-End-Pool über ein WAN (Wide Area Network) hinweg verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="49eca-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="49eca-106">Die Verfahren zum Installieren der neuen Website und der Server an diesem Standort sind bereits in anderen Abschnitten der [Bereitstellung lync Server 2013](lync-server-2013-deploying-lync-server.md) Dokumentation definiert.</span><span class="sxs-lookup"><span data-stu-id="49eca-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="49eca-107">**So definieren Sie einen neuen Standort**</span><span class="sxs-lookup"><span data-stu-id="49eca-107">**To define a new site**</span></span>

1.  <span data-ttu-id="49eca-108">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="49eca-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="49eca-109">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **neuer zentraler Standort**.</span><span class="sxs-lookup"><span data-stu-id="49eca-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="49eca-110">Geben Sie auf der Seite **Standort identifizieren** einen Namen für den Standort und optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="49eca-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="49eca-111">Führen Sie die erforderlichen Schritte zum Definieren der weiteren Komponenten der Standorttopologie aus.</span><span class="sxs-lookup"><span data-stu-id="49eca-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="49eca-112">Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="49eca-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="49eca-113">Veröffentlichen Sie die aktualisierte Topologie.</span><span class="sxs-lookup"><span data-stu-id="49eca-113">Publish the updated topology.</span></span> <span data-ttu-id="49eca-114">Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="49eca-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="49eca-115">Einrichten und Installieren eines Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="49eca-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="49eca-116">Wenn Sie eine Umgebung mit nur einem Standard Edition-Server bereitgestellt haben, hätten Sie den Installationsvorgang mit dem lync Server-Bereitstellungs-Assistenten mithilfe des Links <STRONG>Prepare First Standard Edition-Server</STRONG> begonnen, um die anfänglichen Datenbankdateien im neuen Standard Edition-Server zu installieren.</span><span class="sxs-lookup"><span data-stu-id="49eca-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="49eca-117">Führen Sie diesen Prozess <STRONG>nicht</STRONG> aus, wenn Sie einen Standard Edition-Server in einer vorhandenen lync Server 2013-Bereitstellung installieren.</span><span class="sxs-lookup"><span data-stu-id="49eca-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

