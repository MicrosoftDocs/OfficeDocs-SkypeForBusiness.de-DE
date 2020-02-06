---
title: Hinzufügen eines SQL Server-Speichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Für den Archivierungs Server ist eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware erforderlich, um die Archivdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie möchten für die neue SQL Server-Datenbank verwenden (bei der es sich um die Standardinstanz oder eine benannte Instanz handelt, die Sie angeben).
ms.openlocfilehash: d4fcb526abf0eb1ef961f5790b574a9f30a80b87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821287"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="c8be2-104">Hinzufügen eines SQL Server-Speichers für den Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="c8be2-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="c8be2-105">Für den Archivierungs Server ist eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware erforderlich, um die Archivdaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c8be2-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="c8be2-106">Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie möchten für die neue SQL Server-Datenbank verwenden (bei der es sich um die Standardinstanz oder eine benannte Instanz handelt, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="c8be2-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="c8be2-107">Wenn das Konto, das zum Veröffentlichen der Topologie verwendet wird, über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8be2-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="c8be2-108">Sie können die Datenbank auch später als Teil der Installationsprozedur oder auf andere Weise erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8be2-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="c8be2-109">Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für die Archivierung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="c8be2-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="c8be2-110">Wenn Sie kein Mitglied der Gruppe SQL Server-Sysadmins sind, müssen Sie die Gruppe anfordern, bis die Datenbankdateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8be2-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="c8be2-111">Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="c8be2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="c8be2-112">Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8be2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


