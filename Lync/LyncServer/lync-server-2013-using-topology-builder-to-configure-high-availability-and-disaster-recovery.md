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
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f8585-102">Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8585-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8585-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f8585-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f8585-104">Führen Sie die folgenden Schritte im Topologie-Generator aus, um die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8585-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="f8585-105">Hinzufügen der Spiegeldatenbanken und der sekundären Datenbank des Protokollversands SQL Server Stores.</span><span class="sxs-lookup"><span data-stu-id="f8585-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="f8585-106">Bearbeiten Sie die Diensteigenschaften des beständigen Chat-Servers wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f8585-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="f8585-107">Aktivieren Sie die Spiegelung für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f8585-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="f8585-108">Fügen Sie den primären Spiegelungs-SQL Server-Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8585-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="f8585-109">Aktivieren Sie die SQL Server-Protokollversanddatenbank.</span><span class="sxs-lookup"><span data-stu-id="f8585-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="f8585-110">Fügen Sie den SQL Server-Protokollversand-sekundären SQL Server-Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8585-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="f8585-111">Fügen Sie die SQL Server Store-Spiegelung für die sekundäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8585-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="f8585-112">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="f8585-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

