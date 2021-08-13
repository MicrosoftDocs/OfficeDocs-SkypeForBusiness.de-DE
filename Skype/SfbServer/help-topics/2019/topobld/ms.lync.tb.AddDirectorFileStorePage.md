---
title: Hinzufügen des Director-Dateispeichers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Directors verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 890a966fa58fb0e32acc32b2c677a250bb5d68819469d45a73baa64f209b6021
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304177"
---
# <a name="add-director-file-store"></a>Hinzufügen des Director-Dateispeichers

Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für Directors verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.

> [!IMPORTANT]
> Wenn Sie Ihrer Topologie Directors hinzufügen, ist für die Topologieveröffentlichung ein entsprechender Zugriff zum Einzurichten des Dateispeichers und zum Konfigurieren besitzerverwalteter Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) für die Dateifreigabe erforderlich, die als Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators und zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.

Ausführliche Informationen zur Speicherunterstützung für Dateifreigaben finden Sie unter ["Datei Storage Support"](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in der Dokumentation zur Unterstützung und SQL Server Platzierung von [Daten und Protokolldateien](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation. Ausführliche Informationen zur gemeinsamen Verwendung der Dateifreigabe finden Sie unter [Unterstützte gemeinsame Serververwendung](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in der Unterstützungsdokumentation. Ausführliche Informationen zum Entwerfen der Topologie für Directors finden Sie unter ["Definieren eines einzelnen Director im Topologie-Generator" in](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) der Bereitstellungsdokumentation.