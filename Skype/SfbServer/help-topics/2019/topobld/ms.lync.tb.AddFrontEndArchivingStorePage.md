---
title: Hinzufügen eines Front-End-Archivierungsspeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server zum Speichern der Archivierungsdaten erforderlich. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (dies kann die Standardinstanz sein) oder einer benannten Instanz, die Sie angeben).
ms.openlocfilehash: a0a9528b141730da91d233774a6c676956c9b19b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833525"
---
# <a name="add-front-end-archiving-store"></a>Hinzufügen eines Front-End-Archivierungsspeichers

Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server zum Speichern der Archivierungsdaten erforderlich. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (dies kann die Standardinstanz sein) oder einer benannten Instanz, die Sie angeben).

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsvorganges enthalten ist.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Überwachung müssen Sie Mitglied der Gruppe SQL Server sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server sysadmin sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt sind. Wenn Sie nicht Mitglied der Gruppe "sysadmins" werden können, sollten Sie ihrem SQL Server das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


