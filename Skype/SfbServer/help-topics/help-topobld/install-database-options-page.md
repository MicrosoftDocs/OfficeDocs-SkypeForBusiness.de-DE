---
title: Seite "Datenbank installieren" – Optionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Sie konfigurieren Erweiterte Optionen für die Platzierung von Datenbank-und Protokolldateien auf Ihrem SQL Server. Die verfügbaren Optionen lauten:'
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215306"
---
# <a name="install-database-options-page"></a>Seite "Datenbank installieren" – Optionen

Sie konfigurieren Erweiterte Optionen für die Platzierung von Datenbank-und Protokolldateien auf Ihrem SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die Ihren Anforderungen und Richtlinien in Bezug auf die Daten-und Protokolldatei Platzierung auf Ihren SQL Server Computern am besten entspricht.

 **Speicherort der Datenbankdatei automatisch bestimmen**: die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz im SQL Server bestimmt und die Datenbank und die Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden Sie SQL Server Instanz-Standard**Einstellungen: Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen unter SQL Server zu platzieren. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 **Uns diesen Pfad auf Ziel SQL Server**: Wählen Sie diese Option aus, um eigene Pfade für SQL Server Datenbank-und Protokolldateien zu definieren, indem Sie den vollständigen Pfad zum Laufwerk und Ordner eingeben, in dem die Datenbank-und Protokolldateien gespeichert werden sollen.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Siehe auch

[Platzierung von SQL Server-Daten und Protokolldatei](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
