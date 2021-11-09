---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Aktivieren der Archivierung von Chatinhalten und Webkonferenzinhalten (Besprechungen) müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.
ms.openlocfilehash: d09f398dfa6b0d6441c7b3e9f40dc9928c37ba09
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852549"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Zum Aktivieren der Archivierung von Chatinhalten und Webkonferenzinhalten (Besprechungen) müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie Ihrer Topologie einen Archivierungsserver hinzufügen, muss der Topologie-Generator in der Lage sein, den Archivierungsdateispeicher einzurichten und DACLs (Discretionary Access Control Lists) für die Dateifreigabe zu konfigurieren, die für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter ["Datei Storage Support"](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in der Dokumentation zur Unterstützung und SQL Server Platzierung von [Daten und Protokolldateien](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Unterstützungsdokumentation.