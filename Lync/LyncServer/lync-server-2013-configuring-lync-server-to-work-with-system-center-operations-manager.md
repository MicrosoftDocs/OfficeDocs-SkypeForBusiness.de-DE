---
title: Konfigurieren lync Server für die Verwendung mit System Center Operations Manager
description: Konfigurieren von lync Server für die Verwendung mit System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58126c9e56d48548ba5ce6d74059809c55fecf5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570771"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="57804-103">Konfigurieren lync Server 2013 für die Verwendung mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="57804-103">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57804-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="57804-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="57804-105">Um Ihre Microsoft lync Server 2013-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="57804-105">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="57804-106">Identifizieren und konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="57804-106">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="57804-107">Das Konfigurieren des Verwaltungsservers umfasst die Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 sowie das Einrichten einer Back-End-Datenbank mithilfe von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57804-107">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="57804-108">Die aktuelle Version von SQL Server, die Sie verwenden müssen, hängt von der von Ihnen verwendeten Version von System Center Operations Manager ab.</span><span class="sxs-lookup"><span data-stu-id="57804-108">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="57804-109">Ausführliche Informationen finden Sie unter [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="57804-109">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="57804-110">Identifizieren und konfigurieren Sie die lync Server Computer, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="57804-110">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="57804-111">Um einen lync Server Computer mithilfe von System Center Operations Manager zu überwachen, müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert.</span><span class="sxs-lookup"><span data-stu-id="57804-111">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="57804-112">Identifizieren und konfigurieren Sie die Computer, die als lync Server Watcher- *Knoten*fungieren sollen.</span><span class="sxs-lookup"><span data-stu-id="57804-112">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="57804-113">Watcher-Knoten sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden, bei denen es sich um Windows PowerShell-Cmdlets handelt, die überprüfen, ob die Schlüssel lync Server Komponenten wie die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austauschen von Chatnachrichten wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="57804-113">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="57804-114">Die Themen in diesem Abschnitt enthalten Anweisungen zum Ausführen aller dieser Aufgaben</span><span class="sxs-lookup"><span data-stu-id="57804-114">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57804-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="57804-115">In This Section</span></span>

  - [<span data-ttu-id="57804-116">Konfigurieren des primären Verwaltungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57804-116">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="57804-117">Installieren der lync Server 2013 Management Packs</span><span class="sxs-lookup"><span data-stu-id="57804-117">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="57804-118">Konfigurieren der lync Server Computer, die in lync Server 2013 überwacht werden</span><span class="sxs-lookup"><span data-stu-id="57804-118">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="57804-119">Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57804-119">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

