---
title: 'Lync Server 2013: Konfigurieren von SQL Server für lync Server'
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
ms.openlocfilehash: 435fad8ff60a25b897eff91416e2809a6e2284f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="62650-102">Konfigurieren von SQL Server für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62650-103">_**Letztes Änderungsstand des Themas:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="62650-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="62650-104">In den Themen in diesem Abschnitt wird erläutert, wie Sie SQL Server bereitstellen und konfigurieren, die in einer Enterprise-Bereitstellung von lync Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62650-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="62650-105">Standard Edition-Server verwenden eine zusammengefasste SQL Server Express Version von SQL Server, die für die Arbeitslasten eines Standard Edition-Server richtig dimensioniert ist.</span><span class="sxs-lookup"><span data-stu-id="62650-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="62650-106">Der lync Server 2013 zentrale Verwaltungsspeicher speichert Benutzerdaten für alle Enterprise Edition-Server in einem Pool und ist auf einem SQL Server basierten Back-End-Server ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="62650-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="62650-107">Als zentrales Repository kann der zentrale Verwaltungsspeicher nicht auf demselben Computer installiert werden wie eine beliebige andere lync Server 2013 Rolle.</span><span class="sxs-lookup"><span data-stu-id="62650-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="62650-108">Der zentrale Verwaltungsspeicher kann sich nicht auf einem Enterprise Edition-Server im Pool befinden.</span><span class="sxs-lookup"><span data-stu-id="62650-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="62650-109">Der zentrale Verwaltungsspeicher wird automatisch erstellt, wenn Sie die Topologie zum ersten Mal veröffentlichen, und wählen Sie aus, um die Datenbanken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62650-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="62650-110">Der Computer, den Sie als Back-End-Server festlegen, muss bereits SQL Server Datenbanksoftware ausgeführt werden, damit die Installation erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="62650-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62650-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62650-111">In This Section</span></span>

  - [<span data-ttu-id="62650-112">SQL Server der Daten-und Protokolldatei Platzierung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="62650-113">Konfigurieren von SQL Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="62650-114">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="62650-115">Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="62650-116">Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="62650-117">Konfigurieren von SQL Server Clustering für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62650-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

