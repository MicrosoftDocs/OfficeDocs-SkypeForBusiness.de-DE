---
title: 'Lync Server 2013: Übersicht über die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe615b0bf434b0c87a452a35528aa565c85fe5d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="0e9ba-102">Übersicht über die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e9ba-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e9ba-103">_**Letztes Änderungsstand des Themas:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="0e9ba-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="0e9ba-104">Die Archivierung in lync Server 2013 bietet Ihnen die Möglichkeit, die Kommunikation zu archivieren, die über lync Server 2013 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="0e9ba-105">Sie können die Archivierung als Teil Ihrer anfänglichen lync Server 2013-Bereitstellung implementieren oder einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="0e9ba-106">Wenn Sie lync Server 2013 Archivierungsdatenbanken (SQL Server-Datenbanken) zum Speichern von Archivierungsdaten verwenden möchten, fügen Sie die Datenbanken mithilfe des Topologie-Generators zu Ihrer Topologie hinzu, und veröffentlichen Sie die Topologie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="0e9ba-107">Wenn alle Ihre Benutzer in Exchange 2013 verwaltet werden und ihre Postfächer in-situ-Speicher abgelegt werden, müssen Sie Ihre Topologie nicht aktualisieren, sondern müssen nur Microsoft Exchange Integration aktivieren, um archivierte Daten in Exchange 2013 zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="0e9ba-108">Wenn Sie die Archivierung implementieren, konfigurieren Sie Sie, um anzugeben, was archiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="0e9ba-109">Standardmäßig wird nichts archiviert.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-109">By default, nothing is archived.</span></span> <span data-ttu-id="0e9ba-110">Sie konfigurieren und verwalten die Archivierung mithilfe lync Server 2013 Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0e9ba-111">Sie können die Archivierung für die interne Kommunikation, die externe Kommunikation oder beides implementieren.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="0e9ba-112">Sie können Archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Websites, bestimmte Pools und bestimmte Benutzer und Benutzergruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="0e9ba-113">Ausführliche Informationen zum Bestimmen der geeigneten Optionen für Ihre Organisation finden Sie unter [Definieren der Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="0e9ba-114">Ausführliche Informationen zur Implementierung von Archivierungsrichtlinien und-Konfigurationen sowie Details darüber, welche Informationen archiviert werden können oder können, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0e9ba-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

