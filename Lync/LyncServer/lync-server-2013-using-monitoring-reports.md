---
title: 'Lync Server 2013: Verwenden von Überwachungsberichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Verwenden von Überwachungsberichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Lync Server 2013 enthält eine Reihe von Standardberichten, die vom Microsoft SQL Server-Berichterstattungsdienst veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.

Um diese Berichte verwenden zu können, müssen Sie Überwachungsberichte auf einem Computer installieren, auf dem eine Instanz von SQL Server ausgeführt wird.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Mithilfe des Überwachungs Dashboards in lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   erhalten Administratoren einen schnellen Überblick über den Systemstatus und die Systemnutzung.

  - [Berichte zur Systemnutzung in lync Server 2013](lync-server-2013-system-usage-reports.md)   bietet Informationen zur Systemnutzung auf der Grundlage von CDR-Daten, die von lync Server erfasst werden.

  - [Anruf Diagnoseberichte (pro Benutzer) in lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   bietet benutzerspezifische Informationen zu fehlgeschlagenen Peer-to-Peer-und Konferenzsitzungen.

  - [Anruf Diagnoseberichte in lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   bietet Zusammenfassungsinformationen und Diagnosedaten für fehlerhafte Peer-to-Peer-und Konferenzsitzungen.

  - [Diagnoseberichte für Medienqualität in lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   enthält Informationen zur Anrufqualität sowie zu Diagnose-und Problembehandlungsinformationen für fehlgeschlagene Anrufe.

</div>

<div>

## <a name="locating-records"></a>Suchen von Datensätzen

In Monitoring Server-Berichten wird jeweils immer nur eine begrenzte Anzahl von Datensätzen auf dem Bildschirm angezeigt. Die tatsächlich auf einem Bildschirm angezeigte Anzahl von Datensätzen hängt vom jeweiligen Bericht ab. Wenn Sie die Datensätze anzeigen möchten, die aktuell nicht auf dem Bildschirm sichtbar sind, können Sie die standardmäßigen Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation (die in der Symbolleiste jedes Berichts vorhanden sind) verwenden, mit denen Sie in den Daten blättern können. Darüber hinaus können Sie schnell zur ersten oder letzten Seite des Datasets springen.

Neben der Verwendung der Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation können Sie auch zu jeder beliebigen Seite im Dataset navigieren, indem Sie einfach in das Feld **Aktuelle Seite** die Seitennummer eingeben und dann die EINGABETASTE drücken.

Sie können aber nicht nur in den Daten blättern. Jeder Bericht bietet eine eingeschränkte Suchfunktion für Datensätze. Um anhand eines bestimmten Wertes nach Datensätzen zu suchen, geben Sie den gewünschten Wert in das Feld **Suchen** ein und klicken Sie dann auf **Suchen**. Die Daten werden nun durchsucht. Die Suchfunktion wird bei der ersten gefundenen Instanz des Werts, den Sie in das Feld **Suchen** eingegeben haben, angehalten. Klicken Sie auf **Weiter**, um nach dem nächsten Datensatz zu suchen, der die Suchkriterien erfüllt.

Wie bereits erwähnt, weisen die Monitoring Server-Berichte nur die grundlegendsten Suchfunktionen auf. Beispielsweise können Sie nicht angeben, in welchem Feld nach dem Wert gesucht werden soll. Der Suchmechanismus sucht automatisch in jedem Feld jedes Datensatzes nach Übereinstimmungen. Die Verwendung von Platzhaltern ist bei der Suche nicht möglich und bei allen Suchvorgängen wird nach Teilübereinstimmungen gesucht. Wenn Sie also nach „111“ suchen, wird nicht nur der Wert „111“ zurückgegeben, sondern auch die Werte „11100“, „811“, „3112“, „611A5B“  sowie alle anderen Felder, die den Wert „111“  irgendwo in diesem Feld aufweisen.

Berichte sind so konfiguriert, dass ein Standardsatz von Datensätzen angezeigt wird. Beispielsweise enthält der Bericht über Benutzerregistrierung standardmäßig Benutzerregistrierungsaktivitäten der letzten Woche. Dies kann in manchen Fällen zu einem Bericht ohne Datensätze führen. In diesem Fall bedeutet dies, dass in der letzten Woche keine Benutzerregistrierungen stattgefunden haben. Falls die Meldung „Es stimmen keine Ergebnisse mit den Berichtfiltern überein“ angezeigt wird, sollten Sie die Filterwerte ändern (legen Sie z. B. als Zeitraum nicht die letzte Woche, sondern den letzten Monat fest) und die Abfrage erneut ausführen. Ausführliche Informationen finden Sie unter „Filtern von Daten“ weiter unten in diesem Thema.

</div>

<div>

## <a name="filtering-data"></a>Filtern von Daten

Es wird immer wieder vorkommen, dass Sie nur einen Teil der Datensätze anzeigen möchten. Beispielsweise nur Peer-to-Peer-Sitzungen anstelle von Peer-to-Peer-Sitzungen und Konferenzsitzungen. Entsprechend werden Sie hin und wieder die Anzahl der zurückgegebenen Datensätze reduzieren müssen. In einem Bericht können standardmäßig nur die ersten 1.000 Datensätze eines Datasets angezeigt werden. Zu diesem Zweck gibt es in den meisten Berichten eine Reihe von Filteroptionen. Wenn Sie beispielsweise nur Datensätze für den Zeitraum vom 1. Januar 2011 bis zum 15. Januar 2011 anzeigen möchten, können Sie in den meisten Berichten „1. Januar 2011“ in das Feld **Von** und „15. Januar 2011“ in das Feld **Bis** eingeben. Wenn Sie dann auf **Bericht anzeigen** klicken, werden die zurückgegebenen Daten auf Aktivitäten beschränkt, die zwischen dem 1. Januar 2011 und dem 15. Januar 2011 stattfanden.

Die verfügbaren Filter hängen vom jeweils angezeigten Bericht ab. Ausführliche Informationen zu einem bestimmten Bericht finden Sie im Hilfethema für diesen Bericht.

</div>

<div>

## <a name="exporting-data"></a>Exportieren von Daten

Bei den Überwachungsberichten gibt es mindestens zwei verschiedene Methoden zum Exportieren der Berichtsdaten. Sie können die Option **Exportieren** in der Symbolleiste verwenden, die oben in jedem Bericht angezeigt wird. Wählen Sie zur Verwendung dieser Option in der Dropdownliste **Format auswählen** das gewünschte Exportformat aus. Die folgenden Formate sind verfügbar:

  - XML-Datei mit Berichtsdaten

  - CSV (Komma als Trennzeichen)

  - Acrobat (PDF)-Datei

  - MHTML (Webarchiv)

  - Excel

  - TIFF-Datei

  - Word

Klicken Sie nach der Auswahl eines Formats auf **Exportieren**. Klicken Sie auf **Speichern**, wenn das Dialogfeld **Dateidownload** angezeigt wird. Wählen Sie im Dialogfeld **Speichern unter** einen Zielordner aus, geben Sie einen Dateinamen ein und klicken Sie dann auf **Speichern**.

Wenn Sie Microsoft OneNote installiert haben, können Sie die Berichtsdaten auch nach OneNote kopieren. Klicken Sie dazu in der Symbolleiste mit der rechten Maustaste auf die Schaltfläche **Bericht anzeigen**. Wählen Sie im Dialogfeld **Speicherort in OneNote auswählen** den Bereich in OneNote aus, in den Sie die Daten kopieren möchten und klicken Sie dann auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

