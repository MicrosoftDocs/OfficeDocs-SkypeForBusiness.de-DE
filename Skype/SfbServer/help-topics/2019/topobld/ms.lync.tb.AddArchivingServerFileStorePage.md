---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Aktivieren der Archivierung von Instant Messaging- und Webkonferenzinhalten (Besprechungsinhalten) müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.
ms.openlocfilehash: 352938e9c300c0ff90f41fc004c28d5d21e311d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819585"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Zum Aktivieren der Archivierung von Chat- und Webkonferenzinhalten (Besprechungsinhalten) müssen Sie eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll. Sie können eine vorhandene Dateifreigabe für den Archivierungsdateispeicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, und einen Ordnernamen für die neue Dateifreigabe.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie Ihrer Topologie einen Archivierungsserver hinzufügen, muss der Topologie-Generator in der Lage sein, den Archivierungsdateispeicher und die DACLs (Discretionary Access Control Lists) für die Dateifreigabe für den Dateispeicher zu konfigurieren. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie [unter](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) File [Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in der Unterstützungsdokumentation und SQL Server platzierung von Daten und Protokolldateien in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation.


