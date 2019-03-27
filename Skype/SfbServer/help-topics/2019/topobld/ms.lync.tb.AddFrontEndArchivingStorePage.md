---
title: Hinzufügen des Front-End-Archivierungsspeichers
ms.reviewer: ''
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
ROBOTS: NOINDEX, NOFOLLOW
description: Archivierung erfordert eine unterstützte 64-Bit-Edition von Microsoft SQL Server-Datenbanksoftware die archivierten Daten gespeichert. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, zusätzlich zu der Instanz von SQL SE (engl.) Rver, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: e43d7de6598a24306cc9622f24bea0b2b7e7cc25
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879420"
---
# <a name="add-front-end-archiving-store"></a>Hinzufügen des Front-End-Archivierungsspeichers

Archivierung erfordert eine unterstützte 64-Bit-Edition von Microsoft SQL Server-Datenbanksoftware die archivierten Daten gespeichert. Sie können wählen Sie zuvor definierte SQL Server-Datenbank für die Archivierung verwendet werden, oder definieren eine neue SQL Server-Datenbank durch angeben einen vollqualifizierten Domänennamen (FQDN) des Servers, auf dem SQL Server-Datenbank befinden, zusätzlich zu der Instanz von SQL SE (engl.) Rver, die Sie für die neue SQL Server-Datenbank verwenden möchten (das sein können, die Standardinstanz oder eine benannte Instanz, die Sie angeben).

> [!NOTE]
> Wenn das Konto verwendet, um die Topologie zu veröffentlichen der ausreichenden Benutzerrechte und-Berechtigungen verfügt, können Sie die Überwachungsdatenbank erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens.

> [!NOTE]
> Zum Installieren und die Datenbanken auf dem SQL Server-basierten Server für die Überwachung bereitzustellen, müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie nicht Mitglied der Gruppe der SQL Server-Sysadmin sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie ein Mitglied der Gruppe Sysadmins hergestellt werden können, sollten Sie sich an den Datenbankadministrator SQL Server bereitstellen, mit dem Skript konfigurieren und Bereitstellen der Datenbanken. Ausführliche Informationen über die Benutzerrechte und Berechtigungen, mit denen Sie die Verfahren durchführen müssen, finden Sie unter [Berechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


