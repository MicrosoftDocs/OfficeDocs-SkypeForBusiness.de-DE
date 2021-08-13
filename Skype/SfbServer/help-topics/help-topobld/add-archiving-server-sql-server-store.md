---
title: Hinzufügen eines SQL Server-Speichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware, um die Archivdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (dies kann die Standardinstanz oder eine benannte Instanz sein, die Sie angeben).
ms.openlocfilehash: 471001fbd003211c1f4d47e36c7ad434277ff383f3a262a5a10376d3b6dee617
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315861"
---
# <a name="add-archiving-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Archivierungsserver

Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware, um die Archivdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (dies kann die Standardinstanz oder eine benannte Instanz sein, die Sie angeben).

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt, im Rahmen des Installationsvorgangs oder als Teil eines anderen Vorgangs erstellen.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Archivierung müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server Sysadmins sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht mitglied der Gruppe "sysadmins" werden können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in der Bereitstellungsdokumentation.