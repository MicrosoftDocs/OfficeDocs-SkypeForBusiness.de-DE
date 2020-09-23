---
title: Hinzufügen eines SQL Server-Speichers für den Monitoring Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Monitoring Server erfordert eine unterstützte 64-Bit-Version von SQL Server-Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befindet, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz sein. oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217896"
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Monitoring Server

Monitoring Server erfordert eine unterstützte 64-Bit-Version von SQL Server-Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befindet, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz sein. oder eine benannte Instanz, die Sie angeben).

Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung von [Daten Bank Software und Cluster](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) Unterstützung in der Unterstützungsdokumentation. Ausführliche Informationen zur Überwachungsdatenbank, einschließlich der Zusammenstellung der Überwachungsdatenbank, finden Sie unter [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation,[Planen der Überwachung](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in der Planungsdokumentation und [SQL Server die Platzierung von Daten und Protokolldateien](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. > zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server zur Überwachung müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server sysadmin-Gruppe sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


