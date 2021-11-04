---
title: Seite "Datenbank installieren" – Optionen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:'
ms.openlocfilehash: 39cf85f0c37a9cb3b97e43d09ab6bb5695655ba1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758627"
---
# <a name="install-database-options-page"></a>Seite „Datenbank installieren“ – Optionen

Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die Ihren Anforderungen und Richtlinien bezüglich der Platzierung von Daten und Protokolldateien auf Ihren SQL Server Computern am besten entspricht.

 Automatisches Bestimmen des Speicherorts der **Datenbankdatei:** Die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz auf dem SQL Server bestimmt und die Datenbank und Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden Sie SQL Server Instanzstandardeinstellungen:** Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen in SQL Server zu platzieren. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 **Wir verwenden diesen Pfad auf ziel SQL Server:** Wählen Sie diese Option aus, um Ihre eigenen Pfade für SQL Server Datenbank und Protokolldateien zu definieren, indem Sie den vollständigen Pfad zum Laufwerk und Ordner eingeben, in dem die Datenbank und die Protokolldateien abgelegt werden.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Weitere Informationen

[Platzierung von SQL Server-Daten und Protokolldatei](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)