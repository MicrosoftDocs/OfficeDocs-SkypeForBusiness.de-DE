---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Entfernen Sie die Microsoft SQL Server-Datenbanken und Instanzen nach dem Entfernen von der Servers, die mit hängen darauf klicken, oder nachdem Sie die Server, um eine andere Datenbank verwenden neu konfigurieren. Sie müssen mit dem Verfahren in diesem Thema beim Zurückziehen der aktuelle SQL Server oder neu, den aktuellen Server so konfigurieren, dass sie die Datenbanken veraltete oder nicht verfügbar rendert.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231504"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="67e6f-104">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="67e6f-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="67e6f-105">Entfernen Sie die Microsoft SQL Server-Datenbanken und Instanzen nach dem Entfernen von der Servers, die mit hängen darauf klicken, oder nachdem Sie die Server, um eine andere Datenbank verwenden neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="67e6f-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="67e6f-106">Sie müssen mit dem Verfahren in diesem Thema beim Zurückziehen der aktuelle SQL Server oder neu, den aktuellen Server so konfigurieren, dass sie die Datenbanken veraltete oder nicht verfügbar rendert.</span><span class="sxs-lookup"><span data-stu-id="67e6f-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="67e6f-107">Um die Datenbanken oder Instanzen für den Archivierungsserver oder Monitoring Server zu entfernen, müssen Sie zuerst die Serverrolle entfernen.</span><span class="sxs-lookup"><span data-stu-id="67e6f-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="67e6f-108">Auf ähnliche Weise, um die Instanzen oder die Datenbanken für Front-End-Pool zu entfernen, müssen zuerst entfernen oder neu konfigurieren, die abhängigen Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="67e6f-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="67e6f-109">Diese Verfahren stellen keine Unterscheidung zwischen verbundenen Datenbanken oder separate Instanzen für Server.</span><span class="sxs-lookup"><span data-stu-id="67e6f-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="67e6f-110">Die Verfahrensweise ist durch die gemeinsame Ausführung der Datenbanken nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="67e6f-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="67e6f-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="67e6f-111">In this section</span></span>

- [<span data-ttu-id="67e6f-112">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="67e6f-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="67e6f-113">Entfernen der SQL Server-Datenbank für einen Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="67e6f-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="67e6f-114">Entfernen der SQL Server-Datenbank für einen Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="67e6f-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

