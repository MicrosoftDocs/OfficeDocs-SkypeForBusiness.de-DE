---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 72f8ad131d016d9e14e556b6618ba837a02c7d27
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685378"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie Ihrer Topologie einen Archivierungs Server hinzufügen, muss der Topologie-Generator in der Lage sein, den Archivierungsdatei Speicher einzurichten und DACLs (Discretionary Access Control Lists) für die Dateifreigabe zu konfigurieren, die für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie in der Unterstützungsdokumentation unter [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) und in der Bereitstellungsdokumentation unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx). Ausführliche Informationen zur Kollokation der Dateifreigabe finden Sie in der Unterstützungsdokumentation unter [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx).


