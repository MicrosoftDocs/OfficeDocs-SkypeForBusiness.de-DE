---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Bei einer Standard Edition-Server-Bereitstellung wird die erforderliche Microsoft SQL Server Express-Datenbanksoftware und SQL Server Datenbank automatisch installiert. Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216496"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="a681d-104">Hinzufügen des SQL Server-Speichers des Front-Ends</span><span class="sxs-lookup"><span data-stu-id="a681d-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="a681d-105">Bei einer Standard Edition-Server-Bereitstellung wird die erforderliche Microsoft SQL Server Express-Datenbanksoftware und SQL Server Datenbank automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="a681d-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="a681d-106">Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a681d-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="a681d-107">Für die Front-End-Pool einer Enterprise Edition-Server-Bereitstellung ist eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware für die Back-End-Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a681d-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="a681d-108">Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befinden soll, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz oder eine benannte Instanz, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="a681d-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="a681d-109">Sie können auch die Spiegelung im SQL Server Speicher aktivieren und einen Spiegelungs Zeugen für das automatische Failover angeben.</span><span class="sxs-lookup"><span data-stu-id="a681d-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="a681d-110">Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung von [Daten Bank Software und Cluster](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) Unterstützung in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a681d-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="a681d-111">Ausführliche Informationen zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [configure SQL Server for lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a681d-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="a681d-p105">Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Back-End-Datenbank (Echtzeitkommunikation, RTC) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="a681d-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="a681d-114">Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server für eine Enterprise Edition-Bereitstellung müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="a681d-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="a681d-115">Wenn Sie kein Mitglied der Gruppe "SQL Server Sysadmins" sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a681d-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="a681d-116">Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a681d-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="a681d-117">Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="a681d-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


