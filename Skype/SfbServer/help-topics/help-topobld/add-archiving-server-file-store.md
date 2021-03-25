---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Um die Archivierung von Chat- und Besprechungsinhalten zu aktivieren, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.
ms.openlocfilehash: bd904a746cad5765fafa42d8bff6ea0611311a32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119854"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Um die Archivierung von Chat- und Besprechungsinhalten zu aktivieren, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie Ihrer Topologie einen Archivierungsserver hinzufügen, muss der Topologie-Generator in der Lage sein, den Archivierungsdateispeicher und die DACLs (Discretionary Access Control Lists) für die Dateifreigabe für den Dateispeicher zu konfigurieren. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in der Supportability-Dokumentation und unter SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Unterstützungsdokumentation.