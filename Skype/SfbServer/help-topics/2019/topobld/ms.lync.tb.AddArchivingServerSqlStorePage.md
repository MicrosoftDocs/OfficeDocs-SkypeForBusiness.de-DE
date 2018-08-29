---
title: Hinzufügen eines SQL Server-Speichers Archivierungsserver
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition von der SQL Server-Datenbanksoftware zum Speichern der Daten archivieren. Sie können entweder auswählen eine zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden soll, oder definieren eine neue SQL Server-Datenbank durch einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, und die Instanz von SQL Server angeben, Sie möchten für die neue SQL Server-Datenbank verwendet (werden kann die Standardinstanz oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: 4495db6454dc68d1b46db4d618edba0fea23d0ef
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250602"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="2b5cc-104">Hinzufügen eines SQL Server-Speichers Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="2b5cc-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="2b5cc-105">Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition von der SQL Server-Datenbanksoftware zum Speichern der Daten archivieren.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="2b5cc-106">Sie können entweder auswählen eine zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden soll, oder definieren eine neue SQL Server-Datenbank durch einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, und die Instanz von SQL Server angeben, Sie möchten für die neue SQL Server-Datenbank verwendet (werden kann die Standardinstanz oder eine benannte Instanz, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="2b5cc-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="2b5cc-107">Wenn das Konto, mit dem Veröffentlichen der Topologie, der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) erstellen, wenn Sie Ihre Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="2b5cc-108">Sie können auch die Datenbank des Installationsvorgangs später erstellen oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="2b5cc-109">Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für die Archivierung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="2b5cc-110">Wenn Sie ein Mitglied der SQL Server-Gruppe Sysadmins nicht sind, müssen Sie anfordern, der Gruppe hinzugefügt werden soll, bis die Datenbankdateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="2b5cc-111">Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="2b5cc-112">Ausführliche Informationen über die Benutzerrechte und Berechtigungen, mit denen Sie die Verfahren durchführen müssen, finden Sie unter [Berechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2b5cc-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


