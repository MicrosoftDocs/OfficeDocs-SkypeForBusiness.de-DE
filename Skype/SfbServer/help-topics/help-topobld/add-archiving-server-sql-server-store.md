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
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Archivierungsserver erfordert eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware zum Speichern der Archivdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befindet, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz oder eine benannte Instanz sein,
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217436"
---
# <a name="add-archiving-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Archivierungsserver

Archivierungsserver erfordert eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware zum Speichern der Archivdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befindet, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz oder eine benannte Instanz sein,

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt, im Rahmen des Installationsvorgangs oder als Teil eines anderen Vorgangs erstellen.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server zur Archivierung müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe "SQL Server Sysadmins" sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


