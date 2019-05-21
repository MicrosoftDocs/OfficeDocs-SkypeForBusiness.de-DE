---
title: Hinzufügen des SQL Server-Speichers des Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Bei einer Standard Edition-Server Bereitstellung werden die erforderliche Microsoft SQL Server Express-Datenbanksoftware und die SQL Server-Datenbank automatisch installiert. Daher sind alle Optionen vorab ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.
ms.openlocfilehash: 73e1e9351c5d5b6d9b9f596e2b839037b9081e29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275374"
---
# <a name="add-front-end-sql-server-store"></a>Hinzufügen des SQL Server-Speichers des Front-Ends

Bei einer Standard Edition-Server Bereitstellung werden die erforderliche Microsoft SQL Server Express-Datenbanksoftware und die SQL Server-Datenbank automatisch installiert. Daher sind alle Optionen vorab ausgefüllt, und Sie können keine Änderungen an der Standardkonfiguration vornehmen.

Der Front-End-Pool einer Enterprise Edition-Server Bereitstellung erfordert eine unterstützte 64-Bit-Edition der SQL Server-Datenbanksoftware für die Back-End-Datenbank. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Back-End-Datenbank verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, und die Instanz von SQL S. erver, das Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben). Sie können auch die Spiegelung im SQL Server-Speicher aktivieren und einen Spiegelungs Zeugen für das automatische Failover angeben.

Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung für [Daten Bank Software und Clusterunterstützung](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in der Dokumentation zur Unterstützung. Details zum Einrichten von SQL Server für die Back-End-Datenbank finden Sie unter [Konfigurieren von SQL Server für lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das Konto, das zum Veröffentlichen der Topologie verwendet wird, über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie die Back-End-Datenbank (Real-Time Communications (RTC)) erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs.

> [!NOTE]
> Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für eine Enterprise Edition-Bereitstellung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server-Sysadmins sind, müssen Sie die Gruppe anfordern, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen. Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).


