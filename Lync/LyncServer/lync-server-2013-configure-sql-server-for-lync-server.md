---
title: 'Lync Server 2013: Konfigurieren von SQL Server für Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="6f71b-102">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f71b-103">_**Letztes Änderungsdatum des Themas:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="6f71b-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="6f71b-104">In den Themen in diesem Abschnitt wird erläutert, wie Sie SQL Server für die Verwendung in einer Enterprise-Bereitstellung von lync Server bereitstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6f71b-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="6f71b-105">Standard Edition-Server verwenden eine SQL Server Express-Version von SQL Server, die für die Arbeitslasten eines Standard Edition-Servers die richtige Größe hat.</span><span class="sxs-lookup"><span data-stu-id="6f71b-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="6f71b-106">Der lync Server 2013 Central-Verwaltungsspeicher enthält Benutzerdaten für alle Enterprise Edition-Server in einem Pool und ist für den Standort auf einem auf einem SQL Server basierenden Back-End-Server konzipiert.</span><span class="sxs-lookup"><span data-stu-id="6f71b-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="6f71b-107">Als zentrales Repository kann der zentrale Verwaltungsspeicher nicht auf demselben Computer wie jede andere lync Server 2013-Rolle installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f71b-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="6f71b-108">Der zentrale Verwaltungsspeicher kann sich nicht auf einem Enterprise Edition-Server im Pool befinden.</span><span class="sxs-lookup"><span data-stu-id="6f71b-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="6f71b-109">Der zentrale Verwaltungsspeicher wird automatisch erstellt, wenn Sie die Topologie zum ersten Mal veröffentlichen, und wählen Sie aus, um die Datenbanken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f71b-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="6f71b-110">Auf dem Computer, den Sie als Back-End-Server festlegen, muss bereits die SQL Server-Datenbanksoftware ausgeführt werden, damit die Installation erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6f71b-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f71b-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6f71b-111">In This Section</span></span>

  - [<span data-ttu-id="6f71b-112">Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="6f71b-113">Konfigurieren von SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="6f71b-114">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="6f71b-115">Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="6f71b-116">Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="6f71b-117">Konfigurieren des SQL Server-Clusters für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f71b-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

