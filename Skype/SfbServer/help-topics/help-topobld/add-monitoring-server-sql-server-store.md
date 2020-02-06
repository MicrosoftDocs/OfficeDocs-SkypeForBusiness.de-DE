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
- NOCSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Der Monitoring Server erfordert eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zur Instanz von SQL. Server, den Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben).
ms.openlocfilehash: f1950b01aba29ddff6c7622a6fead726bf835ef3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820747"
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Monitoring Server

Der Monitoring Server erfordert eine unterstützte 64-Bit-Version der SQL Server-Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befindet, zusätzlich zur Instanz von SQL. Server, den Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben).

Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter Unterstützung für [Daten Bank Software und Clusterunterstützung](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in der Dokumentation zur Unterstützung. Details zur Überwachungsdatenbank, einschließlich der Zusammenstellung der Überwachungsdatenbank, finden Sie unter [unterstützter Server Standort](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Dokumentation zur Unterstützung,[Planen der Überwachung](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in der Planungsdokumentation und in der [SQL Server-Daten-und Protokolldatei Platzierung](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie die Überwachungsdatenbank erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs. > Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für die Überwachung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server-Gruppe sysadmin sind, müssen Sie die Gruppe anfordern, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen. Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen dieser Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


