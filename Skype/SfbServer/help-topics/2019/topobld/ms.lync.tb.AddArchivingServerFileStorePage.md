---
title: Hinzufügen eines Dateispeichers für den Archivierungsserver
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: a2948f40e449d3b7326e622e22d9e657dcb4f96c
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19996895"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver
 
Um eine Archivierung des Inhalts von Chats und Webkonferenzen zu ermöglichen, müssen Sie eine Dateifreigabe angeben, die als Dateispeicher der Kopien aller Webkonferenz- bzw. Besprechungsinhalte dienen soll. Sie können als Archivierungsdateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
  
> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie einen Archivierungsserver Ihrer Topologie hinzufügen, müssen Topology Builder werden der Datei Archivierungsspeicher einrichten und Konfigurieren von freigegebenen Zugriffssteuerungslisten (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein. 
  
Ausführliche Informationen zur Speicherung von Unterstützung für Dateifreigaben finden Sie unter [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in der Unterstützungsdokumentation und [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zum Verbinden der Dateifreigabe finden Sie unter [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation.
  

