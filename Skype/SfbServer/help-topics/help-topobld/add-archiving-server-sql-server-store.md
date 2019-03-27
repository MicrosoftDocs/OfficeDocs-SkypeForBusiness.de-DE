---
title: Hinzufügen eines SQL Server-Speichers für den Archivierungsserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition von der SQL Server-Datenbanksoftware zum Speichern der Daten archivieren. Sie können entweder auswählen eine zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden soll, oder definieren eine neue SQL Server-Datenbank durch einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, und die Instanz von SQL Server angeben, Sie möchten für die neue SQL Server-Datenbank verwendet (werden kann die Standardinstanz oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: c8b8c9545b5c3957250dbb696dc7fba7a3dccdb4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899729"
---
# <a name="add-archiving-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Archivierungsserver

Der Archivierungsserver erfordert eine unterstützte 64-Bit-Edition von der SQL Server-Datenbanksoftware zum Speichern der Daten archivieren. Sie können entweder auswählen eine zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden soll, oder definieren eine neue SQL Server-Datenbank durch einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, und die Instanz von SQL Server angeben, Sie möchten für die neue SQL Server-Datenbank verwendet (werden kann die Standardinstanz oder eine benannte Instanz, die Sie angeben).

> [!NOTE]
> Wenn das Konto, mit dem Veröffentlichen der Topologie, der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können auch die Datenbank des Installationsvorgangs später erstellen oder auf andere Weise.

> [!NOTE]
> Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für die Archivierung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie ein Mitglied der SQL Server-Gruppe Sysadmins nicht sind, müssen Sie anfordern, der Gruppe hinzugefügt werden soll, bis die Datenbankdateien bereitgestellt werden. Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken. Ausführliche Informationen über die Benutzerrechte und Berechtigungen, mit denen Sie die Verfahren durchführen müssen, finden Sie unter [Berechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


