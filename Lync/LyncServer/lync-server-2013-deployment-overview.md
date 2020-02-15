---
title: 'Lync Server 2013: Übersicht über die Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d5fd5de9a72002d6ee8bd58ef5367b96634b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="b6c35-102">Übersicht über die Bereitstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6c35-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6c35-103">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="b6c35-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="b6c35-104">Der Hauptunterschied zwischen lync Server 2013 Enterprise Edition und lync Server 2013 Standard Edition besteht darin, dass die Standard Edition die in Enterprise Edition enthaltenen Features für hohe Verfügbarkeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b6c35-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="b6c35-105">Für hohe Verfügbarkeit müssen Sie mehrere Front-End-Server in einem Pool bereitstellen und dann den Server mit SQL Server spiegeln.</span><span class="sxs-lookup"><span data-stu-id="b6c35-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="b6c35-106">Mit Enterprise Edition können Sie eine eigenständige Vermittlungsserver festlegen oder collocate.</span><span class="sxs-lookup"><span data-stu-id="b6c35-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="b6c35-107">Die Monitoring Server und Archivierungsserver können einen eigenständigen Server mit SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6c35-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="b6c35-108">Sie können auch Instanzen von SQL Server haben, die auf dem Daten Bank Server für die Front-End-Server und-Pools aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="b6c35-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="b6c35-109">Server, auf denen lync Server 2013 Standard Edition betrieben wird, sind für kleinere Organisationen und Remotestandorte gedacht, die geografisch aus der Haupt Bereitstellungs Organisation entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b6c35-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="b6c35-110">Zwei Standard Edition-Server-Server, die bei einem Notfall für ein Failover zusammengefügt wurden, können bis zu 5.000 Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b6c35-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="b6c35-111">Sie können keine Standard Edition-Server wie die Front-End-Server in Enterprise Edition Pool.</span><span class="sxs-lookup"><span data-stu-id="b6c35-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="b6c35-112">Außerdem ist die SQL Server-Datenbank, die von Standard Edition verwendet wird, ein zusammengefasster Server mit SQL Server Express, der Standard Edition-Server Arbeitslasten verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="b6c35-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="b6c35-113">Dies bedeutet nicht, dass sich alle Rollen auf einem Standard Edition-Server befinden müssen.</span><span class="sxs-lookup"><span data-stu-id="b6c35-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="b6c35-114">Sie können eigenständige Vermittlungsserver und Edgeserver haben.</span><span class="sxs-lookup"><span data-stu-id="b6c35-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="b6c35-115">Die SQL Server Datenbank für den zentralen Verwaltungsspeicher und für die Zwecke von lync Server 2013 muss sich in der Standard Edition-Server befinden, die mit dem Server mit SQL Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b6c35-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="b6c35-116">Die Monitoring Server und Archivierungsserver verwenden einen eigenständigen Server mit der SQL Server Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b6c35-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

