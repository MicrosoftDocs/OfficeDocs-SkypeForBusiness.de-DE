---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Standard Edition Serverbereitstellung installiert automatisch die erforderliche Microsoft SQL Server Express Datenbanksoftware und SQL Server Datenbank. Daher sind alle Optionen bereits ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: 211e3213489d26682e12b8b39955ad4e1577abf6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776775"
---
# <a name="add-front-end-sql-server-store"></a>Hinzufügen des SQL Server-Speichers des Front-Ends

Eine Standard Edition Serverbereitstellung installiert automatisch die erforderliche Microsoft SQL Server Express Datenbanksoftware und SQL Server Datenbank. Daher sind alle Optionen bereits ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.

Der Front-End-Pool einer Enterprise Edition Serverbereitstellung erfordert eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware für die Back-End-Datenbank. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (dies kann die Standardinstanz oder eine benannte Instanz sein, die Sie angeben). Sie können auch die Spiegelung für den SQL Server Speicher aktivieren und einen Spiegelungszeugen für automatisches Failover angeben.

Ausführliche Informationen zur Unterstützung von SQL Server finden Sie in der Dokumentation zur Unterstützung von [Datenbanksoftware und Clustering.](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) Ausführliche Informationen zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [Konfigurieren SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Back-End-Datenbank (Echtzeitkommunikation, RTC) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs.

> [!NOTE]
> Um die Datenbanken auf dem SQL Server-basierten Server für eine Enterprise Edition Bereitstellung zu installieren und bereitzustellen, müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server Sysadmins sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht mitglied der Gruppe "sysadmins" werden können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).