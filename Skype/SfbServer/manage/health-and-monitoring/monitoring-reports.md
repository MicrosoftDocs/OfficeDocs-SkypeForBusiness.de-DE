---
title: Verwenden von Überwachungsberichten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: 'Zusammenfassung: Erfahren Sie mehr über Überwachungsberichte in Skype for Business Server.'
ms.openlocfilehash: 32e16d02f458ca36fb18b52790966c68a354503e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827765"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a>Verwenden von Überwachungsberichten in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie mehr über Überwachungsberichte in Skype for Business Server.
  
Skype for Business Server enthält eine Reihe von Standardberichten, die von Microsoft SQL Server Reporting Service veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.
  
Um diese Berichte verwenden zu können, müssen Sie Überwachungsberichte auf einem Computer installieren, auf dem eine Instanz des SQL Server.
  
## <a name="in-this-section"></a>In diesem Abschnitt

- [Verwenden des Überwachungsdashboards in Skype for Business Server](monitoring-dashboard.md) Bietet Administratoren einen schnellen Überblick über den Systemzustand und die Systemnutzung.
    
- [Systemverwendungsberichte in Skype for Business Server](system-usage-reports.md) Stellt Informationen zur Systemnutzung basierend auf den von Skype for Business Server gesammelten Daten zur Systemnutzung zur Verfügung.
    
- [Anrufdiagnoseberichte (pro Benutzer) in Skype for Business Server](call-diagnostic-reports-per-user.md) Stellt Benutzerinformationen zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen zur Verfügung.
    
- [Anrufdiagnoseberichte in Skype for Business Server](call-diagnostic-reports.md) Stellt zusammenfassende Informationen und Diagnosedaten für Peer-zu-Peer- und Konferenzsitzungen mit Fehlgeschlagenen zur Verfügung.
    
- [Diagnoseberichte über Medienqualität in Skype for Business Server](media-quality-diagnostic-reports.md) Stellt Informationen zur Anrufqualität sowie Diagnose- und Problembehandlungsinformationen für fehlgeschlagene Anrufe zur Verfügung.
    
## <a name="locating-records"></a>Suchen von Datensätzen

Überwachungsberichte zeigen nur eine begrenzte Anzahl von Datensätzen gleichzeitig auf dem Bildschirm an. Die tatsächliche Anzahl der auf einem Bildschirm angezeigten Datensätze variiert je nach Bericht. Zum Anzeigen der Datensätze, die derzeit nicht auf dem Bildschirm angezeigt werden, können Sie das standardmäßige Vorwärts- und Rückwärtssteuerelement (das sich auf der Symbolleiste jedes Berichts befindet) verwenden, mit dem Sie die Daten durchdsichten können. Sie können auch schnell zur ersten oder letzten Seite des Datasets springen.
  
Neben der Verwendung der Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation können Sie auch zu jeder beliebigen Seite im Dataset navigieren, indem Sie einfach in das Feld **Aktuelle Seite** die Seitennummer eingeben und dann die EINGABETASTE drücken.
  
Sie können aber nicht nur in den Daten blättern. Jeder Bericht bietet eine eingeschränkte Suchfunktion für Datensätze. Für die Suche nach Datensätzen anhand eines bestimmten Werts geben Sie den gewünschten Wert in das Feld **Suchen** ein, und klicken Sie dann auf **Suchen**. Die Daten werden nun durchsucht. Die Suchfunktion wird bei der ersten gefundenen Instanz des Werts, den Sie in das Feld **Suchen** eingegeben haben, angehalten. Klicken Sie auf **Weiter**, um nach dem nächsten Datensatz zu suchen, der die Suchkriterien erfüllt.
  
Wie bereits erwähnt, weisen die Monitoring Server-Berichte nur die grundlegendsten Suchfunktionen auf. Beispielsweise können Sie nicht angeben, in welchem Feld nach dem Wert gesucht werden soll. Der Suchmechanismus sucht automatisch in jedem Feld jedes Datensatzes nach Übereinstimmungen. Die Verwendung von Platzhaltern ist bei der Suche nicht möglich, und bei allen Suchvorgängen wird nach Teilübereinstimmungen gesucht. Wenn Sie also nach „111“ suchen, wird nicht nur der Wert „111“ zurückgegeben, sondern auch die Werte „11100“, „811“, „3112“, „611A5B“ sowie alle anderen Felder, die den Wert „111“ irgendwo in diesem Feld aufweisen.
  
Berichte sind so konfiguriert, dass ein Standardsatz von Datensätzen angezeigt wird. Beispielsweise enthält der Bericht über Benutzerregistrierung standardmäßig Benutzerregistrierungsaktivitäten für die letzte Woche. Dies kann in manchen Fällen zu einem Bericht ohne Datensätze führen. In diesem Fall bedeutet dies, dass in der letzten Woche keine Benutzerregistrierungen ausgeführt wurden. Wenn die Meldung "Keine Ergebnisse stimmen mit den Berichtsfiltern überein" angezeigt wird, versuchen Sie, die Filterwerte zu ändern (z. B. den Zeitraum in den letzten Monat anstelle der letzten Woche zu ändern), und führen Sie die Abfrage erneut aus. Ausführliche Informationen finden Sie unter "Filtern von Daten" weiter unten in diesem Thema.
  
## <a name="filtering-data"></a>Filtern von Daten

Es wird immer wieder vorkommen, dass Sie nur einen Teil der Datensätze anzeigen möchten. Beispielsweise nur Peer-zu-Peer-Sitzungen anstelle von Peer-zu-Peer-Sitzungen und Konferenzsitzungen. Entsprechend werden Sie hin und wieder die Anzahl der zurückgegebenen Datensätze reduzieren müssen. In einem Bericht können standardmäßig nur die ersten 1.000 Datensätze eines Datasets angezeigt werden. Zu diesem Zweck gibt es in den meisten Berichten eine Reihe von Filteroptionen. Wenn Sie beispielsweise nur Datensätze für den Zeitraum vom 1. Januar 2011 bis zum 15. Januar 2011 anzeigen möchten, können Sie in den meisten Berichten „1. Januar 2011“ in das Feld **Von** und „15. Januar 2011“ in das Feld **Bis** eingeben. Wenn Sie dann auf **Bericht anzeigen** klicken, werden die zurückgegebenen Daten auf Aktivitäten beschränkt, die zwischen dem 1 Januar 2011 und dem 15. Januar 2011 stattfanden.
  
Die verfügbaren Filter hängen vom jeweils angezeigten Bericht ab. Ausführliche Informationen zu einem bestimmten Bericht finden Sie im Hilfethema für diesen Bericht.
  
## <a name="exporting-data"></a>Exportieren von Daten

In den Monitoring Server-Berichten gibt es mindestens zwei verschiedene Methoden zum Exportieren der Berichtsdaten. Sie können die Option **Exportieren** in der Symbolleiste verwenden, die oben in jedem Bericht angezeigt wird. Wählen Sie zur Verwendung dieser Option in der Dropdownliste **Format auswählen** das gewünschte Exportformat aus. Die folgenden Formate sind verfügbar:
  
- XML-Datei mit Berichtsdaten
    
- CSV (Komma als Trennzeichen)
    
- Acrobat (PDF)-Datei
    
- MHTML (Webarchiv)
    
- Excel
    
- TIFF-Datei
    
- Word
    
Klicken Sie nach der Auswahl eines Formats auf **Exportieren**. Klicken Sie auf **Speichern**, wenn das Dialogfeld **Dateidownload** angezeigt wird. Wählen Sie im Dialogfeld **Speichern unter** einen Zielordner aus, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Speichern**.
  
Wenn Sie Microsoft OneNote installiert haben, können Sie die Berichtsdaten nach OneNote kopieren. Klicken Sie dazu in der Symbolleiste mit der rechten Maustaste auf die Schaltfläche **Bericht anzeigen**. Wählen Sie im Dialogfeld **Speicherort in OneNote auswählen** den Bereich in OneNote aus, in den Sie die Daten kopieren möchten, und klicken Sie dann auf **OK**.
  

