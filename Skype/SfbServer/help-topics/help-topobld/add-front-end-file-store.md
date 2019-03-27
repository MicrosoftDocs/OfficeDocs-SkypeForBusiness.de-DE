---
title: Hinzufügen des Front-End-Dateispeichers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 086e818483ef56c31c16c49895eeff6f889c0f8e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889543"
---
# <a name="add-front-end-file-store"></a>Hinzufügen des Front-End-Dateispeichers

Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.

> [!IMPORTANT]
> Die Dateifreigabe darf sich nicht auf dem Front-End-Server der Enterprise Edition, kann sich aber auf einem Standard Edition-Server befinden.

> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen.

> [!IMPORTANT]
> Wenn Sie Ihrer Topologie einen Front-End-Pool der Enterprise Edition oder einen Standard Edition-Server hinzufügen, muss der Topologie-Generator in der Lage sein, den Dateispeicher einzurichten und die besitzerverwalteten Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) für die Dateifreigabe zu konfigurieren, die als Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie in der Unterstützungsdokumentation unter [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) und in der Bereitstellungsdokumentation unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx). Ausführliche Informationen zur Kollokation der Dateifreigabe finden Sie in der Unterstützungsdokumentation unter [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx). Ausführliche Informationen zum Entwerfen der Topologie für einen Enterprise Edition-Front-End-Pool finden Sie in der Bereitstellungsdokumentation unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx).


