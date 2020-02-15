---
title: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators
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
ms.openlocfilehash: fc0f47bf8e0a0aec5d2a2374decd79ce2bae77f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f4a5a-102">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung mithilfe des Topologie-Generators in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4a5a-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4a5a-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f4a5a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f4a5a-104">Führen Sie die folgenden Schritte im Topologie-Generator aus, um die hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="f4a5a-105">Fügen Sie die Spiegeldatenbanken und die sekundäre Datenbank des Protokollversands SQL Server speichern hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="f4a5a-106">Bearbeiten Sie die Eigenschaften des Server Diensts für beständigen Chat wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f4a5a-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="f4a5a-107">Aktivieren Sie die Spiegelung für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="f4a5a-108">Fügen Sie den primären Spiegel SQL Server Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="f4a5a-109">Aktivieren Sie die SQL Server Protokollversanddatenbank.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="f4a5a-110">Fügen Sie den sekundären SQL Server Speicher des SQL Server Protokollversands hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="f4a5a-111">Fügen Sie die SQL Server Speicher Spiegel für die sekundäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="f4a5a-112">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="f4a5a-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

