---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Bei einer Standard Edition-Server Bereitstellung werden die erforderliche Microsoft SQL Server Express-Datenbanksoftware und die SQL Server-Datenbank automatisch installiert. Daher sind alle Optionen vorab ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: 58b0af996e418a3db5852571cec6fa82380dde76
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798512"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="ba12b-104">Hinzufügen des SQL Server-Speichers des Front-Ends</span><span class="sxs-lookup"><span data-stu-id="ba12b-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="ba12b-105">Bei einer Standard Edition-Server Bereitstellung werden die erforderliche Microsoft SQL Server Express-Datenbanksoftware und die SQL Server-Datenbank automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="ba12b-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="ba12b-106">Daher sind alle Optionen vorab ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="ba12b-107">Der Front-End-Pool einer Enterprise Edition-Server Bereitstellung erfordert eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware für die Back-End-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ba12b-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="ba12b-108">Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, und die Instanz von SQL S. erver, das Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="ba12b-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="ba12b-109">Sie können auch die Spiegelung im SQL Server-Speicher aktivieren und einen Spiegelungs Zeugen für das automatische Failover angeben.</span><span class="sxs-lookup"><span data-stu-id="ba12b-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="ba12b-110">Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung für [Daten Bank Software und Clusterunterstützung](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="ba12b-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="ba12b-111">Details zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [Konfigurieren von SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ba12b-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="ba12b-112">Wenn das Konto, das zum Veröffentlichen der Topologie verwendet wird, über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie die Back-End-Datenbank (Real-Time Communications (RTC)) erstellen, wenn Sie Ihre Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="ba12b-113">Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="ba12b-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="ba12b-114">Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für eine Enterprise Edition-Bereitstellung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="ba12b-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="ba12b-115">Wenn Sie kein Mitglied der Gruppe SQL Server-Sysadmins sind, müssen Sie die Gruppe anfordern, bis die Datenbankdateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ba12b-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="ba12b-116">Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="ba12b-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="ba12b-117">Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba12b-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


