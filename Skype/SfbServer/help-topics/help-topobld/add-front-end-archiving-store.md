---
title: Hinzufügen des Front-End-Archivierungsspeichers
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Die Archivierung erfordert eine unterstützte 64-Bit-Version der Microsoft SQL Server-Datenbanksoftware zum Speichern der Archivierungsdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befinden soll, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz sein. oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216716"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="666f4-104">Hinzufügen des Front-End-Archivierungsspeichers</span><span class="sxs-lookup"><span data-stu-id="666f4-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="666f4-105">Die Archivierung erfordert eine unterstützte 64-Bit-Version der Microsoft SQL Server-Datenbanksoftware zum Speichern der Archivierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="666f4-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="666f4-106">Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befinden soll, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz sein. oder eine benannte Instanz, die Sie angeben).</span><span class="sxs-lookup"><span data-stu-id="666f4-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="666f4-107">Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen.</span><span class="sxs-lookup"><span data-stu-id="666f4-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="666f4-108">Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsverfahrens enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="666f4-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="666f4-109">Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren.</span><span class="sxs-lookup"><span data-stu-id="666f4-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="666f4-110">Wenn Sie kein Mitglied der SQL Server sysadmin-Gruppe sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="666f4-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="666f4-111">Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="666f4-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="666f4-112">Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="666f4-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


