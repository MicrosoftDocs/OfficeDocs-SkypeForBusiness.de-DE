---
title: 'Lync Server 2013: Komponenten und Topologien für die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dbc882940bc0f28217bcf7c41663bf9ed3708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="dca8a-102">Komponenten und Topologien für die Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dca8a-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca8a-103">_**Letztes Änderungsstand des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="dca8a-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="dca8a-104">Da die Unified Data Collection-Agents auf jedem Front-End-Server automatisch installiert und aktiviert werden, müssen Sie keinen Server konfigurieren, der als Überwachungsserver fungiert. Jeder Front-End-Server fungiert bereits als Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="dca8a-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="dca8a-105">Sie müssen jedoch eine Datenbank installieren und konfigurieren, damit Sie als Back-End-Datenspeicher für Ihre Überwachungsdaten fungieren kann.</span><span class="sxs-lookup"><span data-stu-id="dca8a-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="dca8a-106">Microsoft lync Server 2013 können eine der folgenden Datenbanken als Back-End-Speicher für die Überwachung verwenden:</span><span class="sxs-lookup"><span data-stu-id="dca8a-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="dca8a-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dca8a-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="dca8a-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="dca8a-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="dca8a-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dca8a-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="dca8a-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="dca8a-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="dca8a-111">Beachten Sie, dass Sie die 64-Bit-Editionen dieser Datenbanken verwenden müssen; 32-Bit-Versionen von SQL Server können nicht als Back-End-Speicher für die Überwachung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dca8a-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="dca8a-112">Ebenso unterstützt lync Server 2013 die Express-Editionen von SQL Server 2008 oder SQL Server 2012 nicht.</span><span class="sxs-lookup"><span data-stu-id="dca8a-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="dca8a-113">Weitere Informationen zu den Datenbankanforderungen für lync Server 2013 finden Sie im Thema [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md) im lync Server 2013 Support Guide.</span><span class="sxs-lookup"><span data-stu-id="dca8a-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="dca8a-114">Beachten Sie, dass SQL Server installiert und konfiguriert werden müssen, bevor Sie die Überwachung bereitstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dca8a-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="dca8a-115">Sie müssen jedoch nur SQL Server selbst bereitstellen; Sie müssen die Überwachungsdatenbanken nicht im Voraus einrichten.</span><span class="sxs-lookup"><span data-stu-id="dca8a-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="dca8a-116">Stattdessen werden diese Datenbankenautomatisch für Sie erstellt, wenn Sie Ihre lync Server Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="dca8a-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="dca8a-117">Überwachungsdaten können eine SQL Server Instanz für andere Datentypen freigeben.</span><span class="sxs-lookup"><span data-stu-id="dca8a-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="dca8a-118">Normalerweise verwenden die LcsCdr (Call Detail Recording Database) und die QoEMetrics (Quality of Experience Database) dieselbe SQL-Instanz; Es ist auch üblich, dass sich die beiden Überwachungsdatenbanken in derselben SQL-Instanz wie die Archivierungsdatenbank (LcsLog) befinden.</span><span class="sxs-lookup"><span data-stu-id="dca8a-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="dca8a-119">Die einzige wirkliche Anforderung bei SQL Server-Instanzen besteht darin, dass eine Instanz von SQL Server auf Folgendes beschränkt ist:</span><span class="sxs-lookup"><span data-stu-id="dca8a-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="dca8a-120">Eine Instanz der lync Server 2013-Back-End-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="dca8a-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="dca8a-121">(In der Regel empfiehlt es sich nicht, die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="dca8a-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="dca8a-122">Obwohl es technisch möglich ist, besteht die Gefahr, dass die Überwachungsdatenbank den von der Back-End-Datenbank benötigten Speicherplatz belegt.)</span><span class="sxs-lookup"><span data-stu-id="dca8a-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="dca8a-123">Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="dca8a-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="dca8a-124">Eine Instanz der Datenbank für die Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="dca8a-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="dca8a-125">Eine Instanz der Archivierungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="dca8a-125">One instance of the archiving database.</span></span>

<span data-ttu-id="dca8a-126">In anderen Worten: Sie können nicht zwei Instanzen der LcsCdr-Datenbank in derselben Instanz von SQL Server haben.</span><span class="sxs-lookup"><span data-stu-id="dca8a-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="dca8a-127">Wenn Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere Instanzen von SQL Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dca8a-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dca8a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dca8a-128">See Also</span></span>


[<span data-ttu-id="dca8a-129">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dca8a-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

