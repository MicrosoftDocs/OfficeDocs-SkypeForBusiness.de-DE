---
title: Hinzufügen des Front-End-Archivierungsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server-Datenbanksoftware erforderlich, um die Archivierungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank für die Archivierung auswählen oder eine neue SQL Server-Datenbank definieren, indem Sie neben der Instanz von SQL SE einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll. RVer haben, das Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben).
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820927"
---
# <a name="add-front-end-archiving-store"></a>Hinzufügen des Front-End-Archivierungsspeichers

Für die Archivierung ist eine unterstützte 64-Bit-Version der Microsoft SQL Server-Datenbanksoftware erforderlich, um die Archivierungsdaten zu speichern. Sie können entweder eine zuvor definierte SQL Server-Datenbank für die Archivierung auswählen oder eine neue SQL Server-Datenbank definieren, indem Sie neben der Instanz von SQL SE einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers angeben, auf dem sich die SQL Server-Datenbank befinden soll. RVer haben, das Sie für die neue SQL Server-Datenbank verwenden möchten (bei der es sich um die Standardinstanz oder um eine benannte Instanz handelt, die Sie angeben).

> [!NOTE]
> Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Benutzerrechte und Berechtigungen verfügt, können Sie die Überwachungsdatenbank erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens.

> [!NOTE]
> Wenn Sie die Datenbanken auf dem SQL Server-basierten Server für die Überwachung installieren und bereitstellen möchten, müssen Sie Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-basierten Server sein, auf dem Sie die Datenbankdateien installieren. Wenn Sie kein Mitglied der SQL Server-Gruppe sysadmin sind, müssen Sie anfordern, dass Sie der Gruppe hinzugefügt werden, bis die Datenbankdateien bereitgestellt werden. Wenn Sie nicht Mitglied der Gruppe Sysadmins werden können, sollten Sie dem SQL Server-Datenbankadministrator das Skript zum Konfigurieren und Bereitstellen der Datenbanken zur Verfügung stellen. Details zu den Benutzerrechten und Berechtigungen, die Sie zum Ausführen der Verfahren benötigen, finden Sie unter [Bereitstellungsberechtigungen für SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in der Bereitstellungsdokumentation.


