---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: d78058f862d916228f5be723c7edca6e45a1bb61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886803"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > beim Hinzufügen eines Archivierungsservers zu einer Topologie, Topologie-Generator muss möglicherweise der Datei Archivierungsspeicher einrichten und Konfigurieren von freigegebenen Zugriffssteuerungslisten (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie in der Unterstützungsdokumentation unter [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) und in der Bereitstellungsdokumentation unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx). Ausführliche Informationen zur Kollokation der Dateifreigabe finden Sie in der Unterstützungsdokumentation unter [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx).


