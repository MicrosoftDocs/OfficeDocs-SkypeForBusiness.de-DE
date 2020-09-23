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
# <a name="add-front-end-archiving-store"></a>Hinzufügen des Front-End-Archivierungsspeichers

Die Archivierung erfordert eine unterstützte 64-Bit-Version der Microsoft SQL Server-Datenbanksoftware zum Speichern der Archivierungsdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befinden soll, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz sein. oder eine benannte Instanz, die Sie angeben).

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsverfahrens enthalten ist.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server sysadmin-Gruppe sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


