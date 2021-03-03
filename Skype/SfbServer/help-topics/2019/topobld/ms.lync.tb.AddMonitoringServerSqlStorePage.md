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
description: Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (dies kann die Standardinstanz sein) oder einer benannten Instanz, die Sie angeben).
ms.openlocfilehash: a96dced5bfae5e8381ea28874d295dcfe146d33e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807735"
---
# <a name="add-monitoring-server-sql-server-store"></a>Hinzufügen eines SQL Server-Speichers für den Überwachungsserver

Monitoring Server erfordert eine unterstützte 64-Bit-Edition SQL Server Datenbanksoftware zum Speichern der Überwachungsdaten. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Überwachung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (dies kann die Standardinstanz sein) oder einer benannten Instanz, die Sie angeben).

Ausführliche Informationen zur unterstützung SQL Server finden Sie unter [Datenbanksoftware- und Clusterunterstützung](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in der Unterstützungsdokumentation. Ausführliche Informationen zur Überwachungsdatenbank, einschließlich der Kollokation der Überwachungsdatenbank, finden Sie unter "Unterstützter Serverspeicherort" [in](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) der Unterstützungsdokumentation,["Planning for Monitoring"](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in der Planungsdokumentation und [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. > Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Überwachung müssen Sie Mitglied der Gruppe SQL Server sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der Gruppe SQL Server sysadmin sind, müssen Sie anfordern, der Gruppe hinzugefügt zu werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der Gruppe "sysadmins" werden können, sollten Sie ihrem SQL Server das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


