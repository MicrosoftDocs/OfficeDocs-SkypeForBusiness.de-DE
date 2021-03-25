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
description: 'Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien auf SQL Server. Die verfügbaren Optionen lauten:'
ms.openlocfilehash: 392db6eb9b882ff66a9f15e1f5c4f0918cb140a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116073"
---
# <a name="install-database-options-page"></a>Seite „Datenbank installieren“ – Optionen

Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien auf SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die Ihren Anforderungen und Richtlinien im Zusammenhang mit der Daten- und Protokolldateiplatzierung auf Ihren SQL Server entspricht.

 **Speicherort der Datenbankdatei** automatisch bestimmen: Die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz auf der SQL Server bestimmt und die Datenbank- und Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden SQL Server Instanz standardwerte**: Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen unter SQL Server. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 **Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by tipping the full path to the drive and folder where the database and log files will be placed.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Siehe auch

[Platzierung von SQL Server-Daten und Protokolldatei](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)