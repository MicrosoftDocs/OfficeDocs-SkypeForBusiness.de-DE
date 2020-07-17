---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd5a681be1395038116be32b3267be07213af1b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="4d5c1-102">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="4d5c1-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d5c1-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4d5c1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4d5c1-104">Sie entfernen die Microsoft SQL Server Datenbanken und Instanzen, nachdem Sie die von diesen abhängigen Server lync Server 2010 entfernt haben oder nachdem Sie die Server mit lync Server 2010 neu konfiguriert haben, um eine andere Datenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="4d5c1-105">Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server mit lync Server 2010 so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="4d5c1-106">Um die Datenbanken oder Instanzen für die Archivierungsserver oder Monitoring Server zu entfernen, müssen Sie zuerst die Server Rolle entfernen.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="4d5c1-107">Ebenso müssen Sie zum Entfernen der Instanzen oder Datenbanken für Front-End-Pool zunächst die abhängige Serverrolle entfernen oder neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="4d5c1-108">Bei diesen Verfahren wird nicht zwischen oder verbundenen Datenbanken oder getrennten Instanzen für Server unterschieden.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="4d5c1-109">Die Kollokation von Datenbanken wirkt sich nicht auf die Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="4d5c1-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d5c1-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4d5c1-110">In This Section</span></span>

  - [<span data-ttu-id="4d5c1-111">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="4d5c1-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="4d5c1-112">Entfernen der SQL Server-Datenbank für einen Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="4d5c1-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="4d5c1-113">Entfernen der SQL Server-Datenbank für einen Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="4d5c1-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

