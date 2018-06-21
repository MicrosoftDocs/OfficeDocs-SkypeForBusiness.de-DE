---
title: Hinzufügen von Front-End-Archivierungsspeichers
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Archivierung erfordert eine unterstützte 64-Bit-Edition von Microsoft SQL Server-Datenbanksoftware die archivierten Daten gespeichert. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, zusätzlich zu der Instanz von SQL SE (engl.) Rver, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: 0dc4192c2eb6e7d9569094d6b03c7fb5fcebf6ad
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990035"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="c35a8-104">Hinzufügen von Front-End-Archivierungsspeichers</span><span class="sxs-lookup"><span data-stu-id="c35a8-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="c35a8-105">Archivierung erfordert eine unterstützte 64-Bit-Edition von Microsoft SQL Server-Datenbanksoftware die archivierten Daten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c35a8-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="c35a8-106">Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, zusätzlich zu der Instanz von SQL SE (engl.) Rver, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="c35a8-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c35a8-107">Wenn das Konto verwendet, um die Topologie zu veröffentlichen der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Überwachungsdatenbank erstellen, wenn Sie Ihre Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c35a8-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="c35a8-108">Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens.</span><span class="sxs-lookup"><span data-stu-id="c35a8-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c35a8-109">Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für die Überwachung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="c35a8-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="c35a8-110">Wenn Sie nicht Mitglied der Gruppe der SQL Server-Sysadmin sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c35a8-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="c35a8-111">Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c35a8-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="c35a8-112">Ausführliche Informationen über die Benutzerrechte und Berechtigungen, mit denen Sie die Verfahren durchführen müssen, finden Sie unter [Berechtigungen für SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c35a8-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

