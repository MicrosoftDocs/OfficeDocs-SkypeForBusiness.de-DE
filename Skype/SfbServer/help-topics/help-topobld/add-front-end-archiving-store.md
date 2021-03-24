---
title: Hinzufügen eines Front-End-Archivierungsspeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server zum Speichern der Archivierungsdaten erforderlich. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (die die Standardinstanz sein kann). oder eine benannte Instanz, die Sie angeben).
ms.openlocfilehash: 9f3ee74944ca19f827229bcfcaea2a1e37d2bfcb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107841"
---
# <a name="add-front-end-archiving-store"></a>Hinzufügen eines Front-End-Archivierungsspeichers

Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server zum Speichern der Archivierungsdaten erforderlich. Sie können entweder eine zuvor definierte SQL Server-Datenbank auswählen, die für die Archivierung verwendet werden soll, oder eine neue SQL Server-Datenbank definieren, indem Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll, zusätzlich zur Instanz von SQL Server, die Sie für die neue SQL Server-Datenbank verwenden möchten (die die Standardinstanz sein kann). oder eine benannte Instanz, die Sie angeben).

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die erforderlichen Benutzerrechte und -berechtigungen verfügt, können Sie die Überwachungsdatenbank beim Veröffentlichen Ihrer Topologie erstellen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsverfahrens enthalten ist.

> [!NOTE]
> Zum Installieren und Bereitstellen der Datenbanken auf dem SQL Server-basierten Server für die Überwachung müssen Sie Mitglied der gruppe SQL Server sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server sysadmin-Gruppe sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der sysadmins-Gruppe werden können, sollten Sie ihrem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken bereitstellen. Ausführliche Informationen zu den erforderlichen Benutzerrechten und -berechtigungen zum Ausführen dieser Verfahren finden Sie unter [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in der Bereitstellungsdokumentation.