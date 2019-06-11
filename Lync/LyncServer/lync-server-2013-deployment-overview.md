---
title: 'Lync Server 2013: Übersicht über die Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="9bbbf-102">Übersicht über die Bereitstellung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bbbf-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bbbf-103">_**Letztes Änderungsdatum des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="9bbbf-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="9bbbf-104">Der Hauptunterschied zwischen lync Server 2013 Enterprise Edition und lync Server 2013 Standard Edition besteht darin, dass Standard Edition die in Enterprise Edition enthaltenen Features für die Verfügbarkeit von Funktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="9bbbf-105">Für eine höhere Verfügbarkeit müssen Sie mehrere Front-End-Server in einem Pool bereitstellen, und Sie können den Server, auf dem SQL Server ausgeführt wird, spiegeln.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="9bbbf-106">Mit Enterprise Edition können Sie einen eigenständigen Vermittlungs Server collocate oder definieren.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="9bbbf-107">Der Überwachungsserver und der Archivierungsserver können einen eigenständigen Server verwenden, auf dem SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="9bbbf-108">Oder es können Instanzen von SQL Server auf dem Datenbankserver für die Front-End-Server und-Pools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="9bbbf-109">Server mit lync Server 2013 Standard Edition sind für kleinere Organisationen und Remotestandorte vorgesehen, die geografisch aus der Haupt Bereitstellung des Unternehmens entfernt sind.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="9bbbf-110">Zwei Standard Edition-Server Server, die für Failover im Notfall kombiniert werden, können bis zu 5.000-Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="9bbbf-111">Sie können keine Standard Edition-Server wie Front-End-Server in Enterprise Edition Poolen.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="9bbbf-112">Darüber hinaus ist die SQL Server-Datenbank, die von der Standard Edition verwendet wird, ein Server mit SQL Server Express, der für die Verarbeitung von Arbeitsauslastungen auf Standard Edition ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="9bbbf-113">Damit soll nicht gesagt werden, dass sich alle Rollen auf einem Standard Edition-Server befinden müssen.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="9bbbf-114">Sie können eigenständige Vermittlungsserver und Edgeserver besitzen.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="9bbbf-115">Die SQL Server-Datenbank für den zentralen Verwaltungsspeicher und für die Zwecke von lync Server 2013 muss sich auf dem Standard Edition-Server befinden, der mit dem Server mit SQL Server ausgestattet ist.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="9bbbf-116">Der Überwachungsserver und der Archivierungsserver verwenden einen eigenständigen Server mit der SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9bbbf-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

