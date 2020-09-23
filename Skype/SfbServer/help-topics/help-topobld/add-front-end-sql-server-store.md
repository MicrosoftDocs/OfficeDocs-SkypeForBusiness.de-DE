---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
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
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Bei einer Standard Edition-Server-Bereitstellung wird die erforderliche Microsoft SQL Server Express-Datenbanksoftware und SQL Server Datenbank automatisch installiert. Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216496"
---
# <a name="add-front-end-sql-server-store"></a>Hinzufügen des SQL Server-Speichers des Front-Ends

Bei einer Standard Edition-Server-Bereitstellung wird die erforderliche Microsoft SQL Server Express-Datenbanksoftware und SQL Server Datenbank automatisch installiert. Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.

Für die Front-End-Pool einer Enterprise Edition-Server-Bereitstellung ist eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware für die Back-End-Datenbank erforderlich. Sie können entweder eine zuvor definierte SQL Server Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server Datenbank definieren, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server Datenbank befinden soll, und die Instanz von SQL Server, die Sie für die neue SQL Server Datenbank verwenden möchten (Dies kann die Standardinstanz oder eine benannte Instanz, die Sie angeben). Sie können auch die Spiegelung im SQL Server Speicher aktivieren und einen Spiegelungs Zeugen für das automatische Failover angeben.

Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung von [Daten Bank Software und Cluster](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) Unterstützung in der Unterstützungsdokumentation. Ausführliche Informationen zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [configure SQL Server for lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Back-End-Datenbank (Echtzeitkommunikation, RTC) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server basierten Server für eine Enterprise Edition-Bereitstellung müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe "SQL Server Sysadmins" sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt wurden. Wenn Sie nicht Mitglied der Gruppe "Sysadmins" sein können, sollten Sie Ihrem SQL Server Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


