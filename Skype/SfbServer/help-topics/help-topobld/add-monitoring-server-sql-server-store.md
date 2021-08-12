---
title: Hinzufügen eines SQL Server-Speichers für den Monitoring Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (dies kann die Standardinstanz oder eine benannte Instanz sein, die Sie angeben).
ms.openlocfilehash: 550223a9d3145cdf85711f2df4546f730c1a08553d3847691812ca4bdf8b9f14
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331293"
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Überwachungsserver

Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zu der Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (dies kann die Standardinstanz oder eine benannte Instanz sein, die Sie angeben).

Ausführliche Informationen zur Unterstützung SQL Server finden Sie in der Dokumentation zur Unterstützung von [Datenbanksoftware und Clustering.](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) Ausführliche Informationen zur Überwachungsdatenbank, einschließlich der Kollokation der Überwachungsdatenbank, finden Sie unter ["Unterstützter Serverspeicherort"](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Dokumentation zur Unterstützung,["Planning for Monitoring"](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in der Planungsdokumentation und SQL Server der Platzierung von [Daten und Protokolldateien](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. > Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Überwachung müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server Sysadmin-Gruppe sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht mitglied der Gruppe "sysadmins" werden können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in der Bereitstellungsdokumentation.