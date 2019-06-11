---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="6f897-102">Veröffentlichen der Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f897-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f897-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6f897-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6f897-104">Jedes Mal, wenn Sie die Topologie mithilfe des Topologie-Generators erstellen, müssen Sie die Topologie in einer Datenbank im zentralen Verwaltungsspeicher veröffentlichen, damit die Daten für die Bereitstellung von lync Server 2013 verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6f897-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="6f897-105">Gehen Sie wie folgt vor, um Ihre Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6f897-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="6f897-106">So veröffentlichen Sie die Topologie</span><span class="sxs-lookup"><span data-stu-id="6f897-106">To publish the topology</span></span>

1.  <span data-ttu-id="6f897-107">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="6f897-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6f897-108">Klicken Sie im Topologie-Generator in der Konsolenstruktur mit der rechten Maustaste auf **lync 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="6f897-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="6f897-109">Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f897-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="6f897-110">Klicken Sie auf der Seite " **Topologie-Generator** " auf " **weiter**".</span><span class="sxs-lookup"><span data-stu-id="6f897-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="6f897-111">Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6f897-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="6f897-112">Wenn der Status angibt, dass die Daten Bank Erstellung erfolgreich war, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="6f897-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="6f897-113">Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6f897-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="6f897-114">Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6f897-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="6f897-115">Wenn es sich um eine neue Installation eines Edge-Servers oder eines Edge-Pools handelt, müssen Sie die Edgeserver-Konfiguration von einem vorhandenen Front-End-Server, Front-End-Pool oder Standard Edition-Server exportieren.</span><span class="sxs-lookup"><span data-stu-id="6f897-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="6f897-116">Informationen zum Exportieren der Konfiguration finden Sie unter <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportieren Ihrer lync Server 2013-Topologie und Kopieren der Konfiguration auf externe Medien für die Edge-Installation</A>.</span><span class="sxs-lookup"><span data-stu-id="6f897-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="6f897-117">Sie importieren die Konfigurationsdatei aus der externen Medien-oder Netzwerkfreigabe während der Setup-und Bereitstellungsphase der Edgeserver über den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="6f897-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="6f897-118">Sobald die Edgeserver in Betrieb sind und die lokale Configuration Management Store-Datenbank mit der internen Bereitstellung repliziert wird, werden nachfolgende Updates der lync Server 2013-Konfiguration veröffentlicht und auf die Edgeserver repliziert.</span><span class="sxs-lookup"><span data-stu-id="6f897-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

