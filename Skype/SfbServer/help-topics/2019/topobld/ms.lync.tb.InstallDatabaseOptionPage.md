---
title: Seite "Datenbank installieren" – Optionen
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:'
---

# <a name="install-database-options-page"></a>Seite „Datenbank installieren“ – Optionen

Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien in Ihrem SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die ihren Anforderungen und Richtlinien bezüglich der Platzierung von Daten und Protokolldateien auf Ihren SQL Server Computern am besten entspricht.

 **Automatisches Bestimmen des Speicherorts der Datenbankdatei**: Die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz auf dem SQL Server bestimmt und die Datenbank und Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden Sie SQL Server Instanzstandardeinstellungen**: Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen in SQL Server zu platzieren. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 **Wir haben diesen Pfad auf ziel SQL Server**: Wählen Sie diese Option aus, um Ihre eigenen Pfade für SQL Server Datenbank und Protokolldateien zu definieren, indem Sie den vollständigen Pfad zum Laufwerk und Ordner eingeben, in dem die Datenbank und die Protokolldateien abgelegt werden.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Siehe auch

[Platzierung von SQL Server-Daten und Protokolldatei](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)