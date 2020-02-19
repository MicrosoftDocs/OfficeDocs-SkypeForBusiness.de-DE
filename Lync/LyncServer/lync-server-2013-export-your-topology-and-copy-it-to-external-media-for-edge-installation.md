---
title: Exportieren Sie Ihre Topologie, und kopieren Sie Sie in externe Medien für die Edge-Installation.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 784ed29372b137d5d3f58d749a3660d11cbb55d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="5e152-102">Exportieren der lync Server 2013 Topologie und kopieren auf externe Medien für die Edge-Installation</span><span class="sxs-lookup"><span data-stu-id="5e152-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e152-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5e152-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5e152-104">Nachdem Sie Ihre Topologie veröffentlicht haben, benötigt der lync Server-Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers, um den Bereitstellungsprozess auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="5e152-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="5e152-105">Im internen Netzwerk sind die Daten direkt von den Servern verfügbar, aber Edgeserver, die sich nicht in der internen Domäne befinden, können nicht auf die Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5e152-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="5e152-106">Um die Topologie-Konfigurationsdaten für eine Edgeserver-Bereitstellung zur Verfügung zu stellen, müssen Sie die Topologiedaten in eine Datei exportieren und auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die im Edgeserver verfügbar ist) kopieren, bevor Sie die lync Server DEP ausführen. loyment-Assistent im Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="5e152-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="5e152-107">Verwenden Sie das folgende Verfahren, um Ihre Topologie-Konfigurationsdaten auf dem Edgeserver bereitzustellen, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5e152-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5e152-108">Nachdem Sie lync Server 2013 auf einem Edgeserver installiert haben, verwalten Sie die Edgeserver mit den Verwaltungstools im internen Netzwerk, wodurch die Konfiguration automatisch auf alle Edgeserver in Ihrer Bereitstellung repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="5e152-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="5e152-109">Die einzige Ausnahme ist das zuweisen und Installieren von Zertifikaten und das Beenden und starten von Diensten, die beide auf der Edgeserver ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5e152-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="5e152-110">So stellen Sie Ihre Topologiedaten mithilfe von lync Server-Verwaltungsshell auf einem Edgeserver zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="5e152-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="5e152-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5e152-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5e152-112">Führen Sie im lync Server-Verwaltungsshell das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="5e152-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="5e152-113">Kopieren Sie die exportierte Datei auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die im Edgeserver während der Bereitstellung zur Verfügung steht).</span><span class="sxs-lookup"><span data-stu-id="5e152-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

