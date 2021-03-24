---
title: Hinzufügen eines SQL Server-Speichers für den Monitoring Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (die die Standardinstanz sein kann). oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: 34d5353d78a781fb1462cc908e37e12a0e7d0c5b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100111"
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Überwachungsserver

Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware, um die Überwachungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (die die Standardinstanz sein kann). oder eine benannte Instanz, die Sie angeben).

Ausführliche Informationen zur SQL Server finden Sie unter [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) in der Supportability-Dokumentation. Ausführliche Informationen zur Überwachungsdatenbank, einschließlich der Kollokation der Überwachungsdatenbank, finden Sie unter Supported [Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Supportability-Dokumentation, Planning[for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in der Planungsdokumentation und SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. > Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Überwachung müssen Sie Mitglied der SQL Server-sysadmins-Gruppe für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server sysadmin-Gruppe sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der sysadmins-Gruppe werden können, sollten Sie ihrem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in der Bereitstellungsdokumentation.