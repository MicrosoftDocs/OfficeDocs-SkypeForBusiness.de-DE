---
title: 'Lync Server 2013: Übersicht über die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4aa88f94f0e32b35ab3fc5f71359e5a1c00d99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="30b77-102">Übersicht über die Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30b77-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30b77-103">_**Letztes Änderungsdatum des Themas:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="30b77-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="30b77-104">Die Archivierung in lync Server 2013 bietet eine Möglichkeit zum Archivieren von Kommunikationen, die über lync Server 2013 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="30b77-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="30b77-105">Sie können die Archivierung im Rahmen ihrer anfänglichen lync Server 2013-Bereitstellung implementieren, oder Sie können Sie einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="30b77-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="30b77-106">Wenn Sie lync Server 2013-Archivierungsdatenbanken (SQL Server-Datenbanken) für die Speicherung von Archivierungsdaten verwenden möchten, fügen Sie die Datenbanken mithilfe des Topologie-Generators Ihrer Topologie hinzu, und veröffentlichen Sie die Topologie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="30b77-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="30b77-107">Wenn sich alle Ihre Benutzer in Exchange 2013 befinden und ihre Postfächer in-situ-Speicher abgelegt werden, müssen Sie Ihre Topologie nicht aktualisieren, müssen aber nur die Microsoft Exchange-Integration aktivieren, um archivierte Daten in Exchange 2013 zu speichern.</span><span class="sxs-lookup"><span data-stu-id="30b77-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="30b77-108">Wenn Sie die Archivierung implementieren, konfigurieren Sie Sie, um anzugeben, was archiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="30b77-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="30b77-109">Standardmäßig wird nichts archiviert.</span><span class="sxs-lookup"><span data-stu-id="30b77-109">By default, nothing is archived.</span></span> <span data-ttu-id="30b77-110">Sie können die Archivierung mithilfe der lync Server 2013-Systemsteuerung konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="30b77-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="30b77-111">Sie können die Archivierung für die interne Kommunikation, die externe Kommunikation oder beides implementieren.</span><span class="sxs-lookup"><span data-stu-id="30b77-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="30b77-112">Sie können Archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Websites, bestimmte Pools und bestimmte Benutzer und Benutzergruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="30b77-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="30b77-113">Details zum Ermitteln der geeigneten Optionen für Ihre Organisation finden Sie unter [Definieren Ihrer Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="30b77-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="30b77-114">Details zur Implementierung von Archivierungsrichtlinien und-Konfigurationen sowie Details zu den Informationen, die archiviert werden können, finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="30b77-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

