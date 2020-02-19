---
title: Konfigurieren lync Server für die Verwendung mit System Center Operations Manager
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
ms.openlocfilehash: accadd3f12c9f07ec5dfa295a037ce50a72f11ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="8b3bf-102">Konfigurieren lync Server 2013 für die Verwendung mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="8b3bf-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b3bf-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8b3bf-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8b3bf-104">Um Ihre Microsoft lync Server 2013-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8b3bf-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="8b3bf-105">Identifizieren und konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="8b3bf-106">Das Konfigurieren des Verwaltungsservers umfasst die Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 sowie das Einrichten einer Back-End-Datenbank mithilfe von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="8b3bf-107">Die aktuelle Version von SQL Server, die Sie verwenden müssen, hängt von der von Ihnen verwendeten Version von System Center Operations Manager ab.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="8b3bf-108">Ausführliche Informationen finden Sie unter [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="8b3bf-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="8b3bf-109">Identifizieren und konfigurieren Sie die lync Server Computer, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="8b3bf-110">Um einen lync Server Computer mithilfe von System Center Operations Manager zu überwachen, müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="8b3bf-111">Identifizieren und konfigurieren Sie die Computer, die als lync Server Watcher- *Knoten*fungieren sollen.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="8b3bf-112">Watcher-Knoten sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden, bei denen es sich um Windows PowerShell-Cmdlets handelt, die sicherstellen, dass wichtige lync Server-Komponenten, beispielsweise die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austauschen von Chatnachrichten, funktioniert wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="8b3bf-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="8b3bf-113">Die Themen in diesem Abschnitt enthalten Anweisungen zum Ausführen aller dieser Aufgaben</span><span class="sxs-lookup"><span data-stu-id="8b3bf-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b3bf-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8b3bf-114">In This Section</span></span>

  - [<span data-ttu-id="8b3bf-115">Konfigurieren des primären Verwaltungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b3bf-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="8b3bf-116">Installieren der lync Server 2013 Management Packs</span><span class="sxs-lookup"><span data-stu-id="8b3bf-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="8b3bf-117">Konfigurieren der lync Server Computer, die in lync Server 2013 überwacht werden</span><span class="sxs-lookup"><span data-stu-id="8b3bf-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="8b3bf-118">Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b3bf-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

