---
title: Hinzufügen des Front-End-Dateispeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 90860ff365ff1d5ff2279dc32df96f77d9725c895c7587f9606ccfab21364668
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317620"
---
# <a name="add-front-end-file-store"></a>Hinzufügen des Front-End-Dateispeichers

Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.

> [!IMPORTANT]
> Die Dateifreigabe kann sich nicht auf dem Enterprise Edition Front-End-Server befinden, sondern auf einem Standard Edition Server.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen.

> [!IMPORTANT]
> Wenn Sie Ihrer Topologie einen Front-End-Pool der Enterprise Edition oder Standard Edition-Server hinzufügen, muss der Topologie-Generator in der Lage sein, den Dateispeicher einzurichten und die besitzerverwalteten Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) für die Dateifreigabe zu konfigurieren, die als Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter ["Datei Storage Support"](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in der Dokumentation zur Unterstützung und SQL Server Der Platzierung von [Daten und Protokolldateien](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Unterstützungsdokumentation. Ausführliche Informationen zum Entwerfen der Topologie für einen Enterprise Edition-Front-End-Pool finden Sie unter [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in der Bereitstellungsdokumentation.