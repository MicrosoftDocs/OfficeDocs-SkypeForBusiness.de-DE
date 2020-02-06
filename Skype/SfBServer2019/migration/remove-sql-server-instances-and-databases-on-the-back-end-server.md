---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie entfernen die Microsoft SQL Server-Datenbanken und-Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812983"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="a16f4-104">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="a16f4-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="a16f4-105">Sie entfernen die Microsoft SQL Server-Datenbanken und-Instanzen, nachdem Sie die Server entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server neu konfiguriert haben, um eine andere Datenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a16f4-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="a16f4-106">Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a16f4-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="a16f4-107">Um die Datenbanken oder Instanzen für den Archivierungsserver oder den Überwachungsserver zu entfernen, müssen Sie zuerst die Serverrolle entfernen.</span><span class="sxs-lookup"><span data-stu-id="a16f4-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="a16f4-108">Um die Instanzen oder Datenbanken für den Front-End-Pool zu entfernen, müssen Sie die abhängige Serverrolle zunächst entfernen oder neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a16f4-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="a16f4-109">Bei diesen Verfahren wird nicht zwischen zusammengefassten Datenbanken oder separaten Instanzen für Server unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a16f4-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="a16f4-110">Die Verfahren sind von der Daten Bank Zusammenstellung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="a16f4-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a16f4-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="a16f4-111">In this section</span></span>

- [<span data-ttu-id="a16f4-112">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="a16f4-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="a16f4-113">Entfernen der SQL Server-Datenbank für einen Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a16f4-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="a16f4-114">Entfernen der SQL Server-Datenbank für einen Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="a16f4-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

