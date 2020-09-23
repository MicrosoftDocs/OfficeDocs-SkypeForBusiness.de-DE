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
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll, um die Archivierung sowohl von Chat Inhalten (Instant Messaging) als auch von Webkonferenzen (Meeting) zu ermöglichen. Sie können eine vorhandene Dateifreigabe für den Archivierungsdatei Speicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, sowie einen Ordnernamen für die neue Dateifreigabe.
ms.openlocfilehash: 22f7de704b3d7a611d4601df4c14ed75f7466c1c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217426"
---
# <a name="add-archiving-server-file-store"></a>Hinzufügen eines Dateispeichers für den Archivierungsserver

Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Kopien aller Webkonferenzinhalte verwendet werden soll, um die Archivierung sowohl von Chat Inhalten (Instant Messaging) als auch von Webkonferenzen (Meeting) zu ermöglichen. Sie können eine vorhandene Dateifreigabe für den Archivierungsdatei Speicher verwenden oder eine neue Dateifreigabe angeben, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers angeben, auf dem sich die Dateifreigabe befinden soll, sowie einen Ordnernamen für die neue Dateifreigabe.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. > Wenn Sie Ihrer Topologie einen Archivierungsserver hinzufügen, muss der Topologie-Generator in der Lage sein, den Archivierungsdatei Speicher einzurichten und DACLs (Discretionary Access Control Lists) für die Dateifreigabe zu konfigurieren, die für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter [Unterstützung der Dateispeicherung](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in der Dokumentation zur Unterstützung und [SQL Server der Daten-und Protokolldatei Platzierung](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in der Unterstützungsdokumentation.


