---
title: Seite "Datenbank installieren" – Optionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien SQL Server. Die verfügbaren Optionen lauten:'
ms.openlocfilehash: 5da2d50bf6571408f63403998443155307d86e2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805735"
---
# <a name="install-database-options-page"></a>Seite „Datenbank installieren“ – Optionen

Sie konfigurieren erweiterte Optionen für die Platzierung von Datenbank- und Protokolldateien SQL Server. Die verfügbaren Optionen lauten:

> [!IMPORTANT]
> Wählen Sie die Option aus, die Ihren Anforderungen und Richtlinien im Zusammenhang mit der Platzierung von Daten und Protokolldateien auf Ihren SQL Server entspricht.

 **Speicherort der Datenbankdatei** automatisch bestimmen: Die Standardoption verwendet einen Algorithmus, der den verfügbaren Speicherplatz auf der SQL Server bestimmt und die Datenbank- und Protokolldateien für eine optimale Leistung verteilt.

 **Verwenden SQL Server Standardeinstellungen** der Instanz: Wählen Sie diese Option aus, um Datenbankdateien und Protokolldateien basierend auf den Instanzeinstellungen auf der SQL Server. Die Optionen werden normalerweise von Ihrem Datenbankadministrator verwaltet und konfiguriert.

 Dieser Pfad im **Ziel-SQL Server:** Wählen Sie diese Option aus, um eigene Pfade für SQL Server-Datenbank- und Protokolldateien zu definieren, indem Sie den vollständigen Pfad zum Laufwerk und Ordner eingeben, in dem die Datenbank- und Protokolldateien abgelegt werden.

> [!IMPORTANT]
> Möglicherweise werden die eingegebenen Pfade während der Installation mithilfe von Algorithmen zur Leistungsoptimierung geändert. Ausführliche Informationen finden Sie unter [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: Klicken Sie auf die Schaltfläche "OK", um die Änderungen zu übernehmen.

 **Abbrechen**: Klicken Sie auf "Abbrechen", um alle Änderungen zu verwerfen und zum Bildschirm "Datenbank installieren" zurückzukehren.

 **Hilfe**: Klicken Sie auf die Schaltfläche "Hilfe", um auf diese Hilfeseite zuzugreifen.

## <a name="see-also"></a>Siehe auch

[Platzierung von SQL Server-Daten und Protokolldatei](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
