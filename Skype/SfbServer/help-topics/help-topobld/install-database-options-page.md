---
title: Seite "Datenbank installieren" – Optionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:'
ms.openlocfilehash: 6b9ad2dc1dd91eeb0834c43394f00221d687d0d66058c5037e6d90c83cd10bad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321717"
---
# <a name="install-database-options-page"></a>Seite „Datenbank installieren“ – Optionen

Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die ihren Anforderungen und Richtlinien bezüglich der Platzierung von Daten und Protokolldateien auf Ihren SQL Server Computern am besten entspricht.

 Automatisches Bestimmen des Speicherorts der **Datenbankdatei:** Die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz auf dem SQL Server bestimmt und die Datenbank und Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden Sie SQL Server Instanzstandardeinstellungen:** Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen in SQL Server zu platzieren. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 **Us these path on target SQL Server:** Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Siehe auch

[Platzierung von SQL Server-Daten und Protokolldatei](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)