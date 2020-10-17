---
title: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators
description: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547321"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="fedf1-103">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung mithilfe des Topologie-Generators in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fedf1-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fedf1-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fedf1-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fedf1-105">Führen Sie die folgenden Schritte im Topologie-Generator aus, um die hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fedf1-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="fedf1-106">Fügen Sie die Spiegeldatenbanken und die sekundäre Datenbank des Protokollversands SQL Server speichern hinzu.</span><span class="sxs-lookup"><span data-stu-id="fedf1-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="fedf1-107">Bearbeiten Sie die Eigenschaften des Server Diensts für beständigen Chat wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fedf1-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="fedf1-108">Aktivieren Sie die Spiegelung für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="fedf1-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="fedf1-109">Fügen Sie den primären Spiegel SQL Server Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="fedf1-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="fedf1-110">Aktivieren Sie die SQL Server Protokollversanddatenbank.</span><span class="sxs-lookup"><span data-stu-id="fedf1-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="fedf1-111">Fügen Sie den sekundären SQL Server Speicher des SQL Server Protokollversands hinzu.</span><span class="sxs-lookup"><span data-stu-id="fedf1-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="fedf1-112">Fügen Sie die SQL Server Speicher Spiegel für die sekundäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="fedf1-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="fedf1-113">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="fedf1-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

