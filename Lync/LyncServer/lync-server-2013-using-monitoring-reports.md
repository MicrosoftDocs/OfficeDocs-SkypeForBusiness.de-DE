---
title: 'Lync Server 2013: Verwenden von Überwachungsberichten'
TOCTitle: Verwenden von Überwachungsberichten
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558662(v=OCS.15)
ms:contentKeyID: 49294412
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Überwachungsberichten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Lync Server 2013 enthält einen Satz Standardberichte, die von Microsoft SQL Server Reporting Services veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.

Zur Verwendung dieser Berichte müssen Sie Monitoring-Berichte auf einem Computer installieren, auf dem eine Instanz von SQL Server ausgeführt wird.

## In diesem Abschnitt

  - [Verwenden des Monitoring-Dashboards](lync-server-2013-using-the-monitoring-dashboard.md)   Ermöglicht Administratoren einen schnellen Überblick zu Systemintegrität und Systemauslastung.

  - [Systemauslastungsberichte in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Liefern Systemauslastungsinformationen basierend auf den von Lync Server gesammelten KDS-Daten.

  - [Anrufdiagnoseberichte (pro Benutzer) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Liefern benutzerbezogene Informationen zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen.

  - [Anrufdiagnoseberichte in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Liefern zusammenfassende Informationen und Diagnosedaten zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen.

  - [Medienqualitäts-Diagnoseberichte in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Liefern Informationen zur Anrufqualität sowie Diagnose- und Problembehandlungsinformationen für fehlerhafte Anrufe.

## Suchen von Datensätzen

In Monitoring Server-Berichten wird jeweils immer nur eine begrenzte Anzahl von Datensätzen auf dem Bildschirm angezeigt. Die tatsächlich auf einem Bildschirm angezeigte Anzahl von Datensätzen hängt vom jeweiligen Bericht ab. Wenn Sie die Datensätze anzeigen möchten, die aktuell nicht auf dem Bildschirm sichtbar sind, können Sie die standardmäßigen Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation (die in der Symbolleiste jedes Berichts vorhanden sind) verwenden, mit denen Sie in den Daten blättern können. Darüber hinaus können Sie schnell zur ersten oder letzten Seite des Datasets springen.

Neben der Verwendung der Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation können Sie auch zu jeder beliebigen Seite im Dataset navigieren, indem Sie einfach in das Feld **Aktuelle Seite** die Seitennummer eingeben und dann die EINGABETASTE drücken.

Sie können aber nicht nur in den Daten blättern. Jeder Bericht bietet eine eingeschränkte Suchfunktion für Datensätze. Für die Suche nach Datensätzen anhand eines bestimmten Werts geben Sie den gewünschten Wert in das Feld **Suchen** ein, und klicken Sie dann auf **Suchen** . Die Daten werden nun durchsucht. Die Suchfunktion wird bei der ersten gefundenen Instanz des Werts, den Sie in das Feld **Suchen** eingegeben haben, angehalten. Klicken Sie auf **Weiter** , um nach dem nächsten Datensatz zu suchen, der die Suchkriterien erfüllt.

Wie bereits erwähnt, weisen die Monitoring Server-Berichte nur die grundlegendsten Suchfunktionen auf. Beispielsweise können Sie nicht angeben, in welchem Feld nach dem Wert gesucht werden soll. Der Suchmechanismus sucht automatisch in jedem Feld jedes Datensatzes nach Übereinstimmungen. Die Verwendung von Platzhaltern ist bei der Suche nicht möglich, und bei allen Suchvorgängen wird nach Teilübereinstimmungen gesucht. Wenn Sie also nach „111“ suchen, wird nicht nur der Wert „111“ zurückgegeben, sondern auch die Werte „11100“ , „811“ , „3112“ , „611A5B“ sowie alle anderen Felder, die den Wert „111“ irgendwo in diesem Feld aufweisen.

Berichte sind so konfiguriert, dass ein Standardsatz von Datensätzen angezeigt wird. Beispielsweise enthält der Bericht über Benutzerregistrierung standardmäßig Benutzerregistrierungsaktivitäten für die letzte Woche. Dies kann in manchen Fällen zu einem Bericht ohne Datensätze führen. In diesem Fall bedeutet dies, dass in der letzten Woche keine Benutzerregistrierungen ausgeführt wurden. Falls die Meldung **Es stimmen keine Ergebnisse mit den Berichtfiltern überein** angezeigt wird, sollten Sie die Filterwerte ändern (legen Sie z. B. als Zeitraum nicht die letzte Woche, sondern den letzten Monat fest) und die Abfrage erneut ausführen. Ausführliche Informationen finden Sie unter "Filtern von Daten" weiter unten in diesem Thema.

## Filtern von Daten

Es wird immer wieder vorkommen, dass Sie nur einen Teil der Datensätze anzeigen möchten. Beispielsweise nur Peer-zu-Peer-Sitzungen anstelle von Peer-zu-Peer-Sitzungen und Konferenzsitzungen. Entsprechend werden Sie hin und wieder die Anzahl der zurückgegebenen Datensätze reduzieren müssen. In einem Bericht können standardmäßig nur die ersten 1.000 Datensätze eines Datasets angezeigt werden. Zu diesem Zweck gibt es in den meisten Berichten eine Reihe von Filteroptionen. Wenn Sie beispielsweise nur Datensätze für den Zeitraum vom 1. Januar 2011 bis zum 15. Januar 2011 anzeigen möchten, können Sie in den meisten Berichten „1. Januar 2011“ in das Feld **Von** und „15. Januar 2011“ in das Feld **Bis** eingeben. Wenn Sie dann auf **Bericht anzeigen** klicken, werden die zurückgegebenen Daten auf Aktivitäten beschränkt, die zwischen dem 1 Januar 2011 und dem 15. Januar 2011 stattfanden.

Die verfügbaren Filter hängen vom jeweils angezeigten Bericht ab. Ausführliche Informationen zu einem bestimmten Bericht finden Sie im Hilfethema für diesen Bericht.

## Exportieren von Daten

In den Monitoring Server-Berichten gibt es mindestens zwei verschiedene Methoden zum Exportieren der Berichtsdaten. Sie können die Option **Exportieren** in der Symbolleiste verwenden, die oben in jedem Bericht angezeigt wird. Wählen Sie zur Verwendung dieser Option in der Dropdownliste **Format auswählen** das gewünschte Exportformat aus. Die folgenden Formate sind verfügbar:

  - XML-Datei mit Berichtsdaten

  - CSV (Komma als Trennzeichen)

  - Acrobat (PDF)-Datei

  - MHTML (Webarchiv)

  - Excel

  - TIFF-Datei

  - Word

Klicken Sie nach der Auswahl eines Formats auf **Exportieren** . Klicken Sie auf **Speichern** , wenn das Dialogfeld **Dateidownload** angezeigt wird. Wählen Sie im Dialogfeld **Speichern unter** einen Zielordner aus, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Speichern** .

Wenn Sie Microsoft OneNote installiert haben, können Sie die Berichtsdaten nach OneNote kopieren. Klicken Sie dazu in der Symbolleiste mit der rechten Maustaste auf die Schaltfläche **Bericht anzeigen** . Wählen Sie im Dialogfeld **Speicherort in OneNote auswählen** den Bereich in OneNote aus, in den Sie die Daten kopieren möchten, und klicken Sie dann auf **OK** .

