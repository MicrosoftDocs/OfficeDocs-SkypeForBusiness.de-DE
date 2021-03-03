---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Bei einer Standard Edition-Serverbereitstellung wird automatisch die erforderliche Microsoft SQL Server -Datenbanksoftware und die SQL Server installiert. Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811625"
---
# <a name="add-front-end-sql-server-store"></a>Hinzufügen des SQL Server-Speichers des Front-Ends

Bei einer Standard Edition-Serverbereitstellung wird automatisch die erforderliche Microsoft SQL Server -Datenbanksoftware und die SQL Server installiert. Daher werden alle Optionen vorab aufgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.

Der Front-End-Pool einer Enterprise Edition-Serverbereitstellung erfordert eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware für die Back-End-Datenbank. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, und die Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (dies kann die Standardinstanz sein) oder einer benannten Instanz, die Sie angeben). Sie können auch die Spiegelung im SQL Server aktivieren und einen Spiegelungszeugen für das automatische Failover angeben.

Ausführliche Informationen zur unterstützung SQL Server finden Sie unter [Datenbanksoftware- und Clusterunterstützung](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in der Unterstützungsdokumentation. Ausführliche Informationen zum Einrichten SQL Server für die Back-End-Datenbank finden Sie unter SQL Server [in](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Back-End-Datenbank (Echtzeitkommunikation, RTC) beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für eine Enterprise Edition-Bereitstellung müssen Sie Mitglied der Gruppe SQL Server sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server sysadmins sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt sind. Wenn Sie nicht Mitglied der Gruppe "sysadmins" werden können, sollten Sie ihrem SQL Server das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


