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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Für den Archivierungs Server ist eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware erforderlich, um die Archivdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie möchten für die neue SQL Server-Datenbank verwenden (bei der es sich um die Standardinstanz oder eine benannte Instanz handelt, die Sie angeben).
ms.openlocfilehash: 232b363e3a43f0cd58783a829bfe672434385fa8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698670"
---
# <a name="add-archiving-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Archivierungsserver

Für den Archivierungs Server ist eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware erforderlich, um die Archivdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, und die Instanz von SQL Server, die Sie möchten für die neue SQL Server-Datenbank verwenden (bei der es sich um die Standardinstanz oder eine benannte Instanz handelt, die Sie angeben).

> [!NOTE]
> Wenn das Konto, das zum Veröffentlichen der Topologie verwendet wird, über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen. Sie können die Datenbank auch später als Teil der Installationsprozedur oder auf andere Weise erstellen.

> [!NOTE]
> Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für die Archivierung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server-Sysadmins sind, müssen Sie die Gruppe anfordern, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen. Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


