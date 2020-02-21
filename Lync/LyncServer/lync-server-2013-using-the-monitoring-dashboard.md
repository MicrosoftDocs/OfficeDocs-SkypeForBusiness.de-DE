---
title: 'Lync Server 2013: Verwenden des Monitoring-Dashboards'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 697023ef7c93191cbe13aa0abf4c175240e70ae9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Verwenden des Monitoring-Dashboards in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Das Monitoring-Dashboard bietet Administratoren einen schnellen Überblick über die Microsoft lync Server 2013 Systemintegrität und Systemnutzung. Im Dashboard wird eine Zusammenfassung wichtiger Systemmetriken für folgende Werte angezeigt:

  - Gesamtwerte für den aktuellen Tag. Beachten Sie, dass die für den aktuellen Tag angezeigten Werte Daten repräsentieren, die von Mitternacht bis zum aktuellen Zeitpunkt aufgezeichnet wurden (basierend auf der Ortszeit des Berichtsservers). Dies bedeutet, dass Sie in der Regel Daten für einen Teil des Tags, und nicht für einen Zeitraum von 24 Stunden sehen. Wenn z. B. die Ortszeit des Servers 08:00 Uhr ist, sehen Sie acht Stunden an Daten, da zwischen Mitternacht und der aktuellen Urzeit 08:00 Uhr acht Stunden verstrichen sind.

  - Gesamtwerte für die Woche sowie Trendgesamtwerte für die letzten sechs Wochen.

  - Gesamtwerte für den Monat sowie Trendgesamtwerte für die letzten sechs Monate (nur für die Systemauslastung).

Beachten Sie, dass Sie das Cmdlet [Get-csreportingconfiguration "](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) verwenden können, um die URL zurückzugeben, die für den Zugriff auf lync Server 2013-Überwachungsberichte verwendet wird:

    Get-CsReportingConfiguration

Standardmäßig werden im Monitoring-Dashboard Daten für die folgenden Metriken für die aktuelle Woche angezeigt (und Trendgesamtwerte für die letzten sechs Wochen):

<div>

## <a name="system-usage-metrics"></a>Metriken für die Systemauslastung

**Registrierung**

  - Eindeutige Benutzeranmeldungen

**Peer-to-Peer**

  - Sitzungen insgesamt

  - Chatsitzungen

  - Audiositzungen

  - Videositzungen

  - Anwendungsfreigabe

  - Gesamtdauer der Audiositzung in Minuten

  - Durchschn. Dauer der Audiositzung in Minuten

**Konferenz**

  - Konferenzen insgesamt

  - Chatkonferenzen

  - A/V-Konferenzen

  - Anwendungsfreigabekonferenzen

  - Webkonferenzen

  - Organisatoren insgesamt

  - Gesamtdauer der A/V-Konferenzen in Minuten

  - Durchschn. Dauer der A/V-Konferenzen in Minuten

  - PSTN-Konferenzen insgesamt

  - PSTN-Teilnehmer insgesamt

  - PSTN-Teilnehmerminuten insgesamt

Neben den Metriken für die Systemauslastung werden für die folgenden Metriken Gesamtwerte für den aktuellen Tag und die letzten sechs Tage (wenn Sie **Wöchentliche Ansicht** auswählen) bzw. für die aktuelle Woche und die letzten sechs Wochen (wenn Sie **Monatliche Ansicht** auswählen) angezeigt.

</div>

<div>

## <a name="per-user-call-diagnostics"></a>Anrufdiagnose pro Benutzer

**Benutzer mit Anruffehlern**

  - Benutzer insgesamt mit Anruffehlern

  - Konferenzorganisatoren mit Anruffehlern

**Benutzer mit Anrufen schlechter Qualität**

  - Benutzer insgesamt mit Anrufen schlechter Qualität

</div>

<div>

## <a name="call-diagnostics"></a>Anrufdiagnose

Peer-to-Peer

  - Fehler insgesamt

  - Fehlerrate insgesamt

  - Chatfehlerrate

  - Audio-Fehlerrate

  - Anwendungsfreigabe-Fehlerrate

Konferenz

  - Fehler insgesamt

  - Fehlerrate insgesamt

  - Chatfehlerrate

  - A/V-Fehlerrate

  - Anwendungsfreigabe-Fehlerrate

5 Server mit den meisten fehlerhaften Sitzungen

</div>

<div>

## <a name="media-quality-diagnostics"></a>Medienqualitätsdiagnose

Peer-to-Peer

  - Gesamtzahl der Anrufe schlechter Qualität

  - Prozentsatz der Anrufe schlechter Qualität

  - PSTN-Anrufe schlechter Qualität

Konferenz

  - Gesamtzahl der Anrufe schlechter Qualität

  - Prozentsatz der Anrufe schlechter Qualität

  - PSTN-Anrufe schlechter Qualität

Server mit dem höchsten Prozentsatz der Anrufe schlechter Qualität

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>Arbeiten mit dem Monitoring-Dashboard

Wie bereits erwähnt, werden standardmäßig Gesamtwerte für die aktuelle Woche sowie Trendwerte für die letzten sechs Wochen angezeigt. Wenn Sie Gesamtwerte für den aktuellen Monat (sowie Trendwerte für die letzten sechs Monate) vorziehen, klicken Sie in der oberen rechten Ecke des Dashboards auf den Link **Monatliche Ansicht**. Falls Sie monatliche Gesamtwerte anzeigen, wird der Text des Links in **Wöchentliche Ansicht** geändert. Durch Klicken auf diesen Link wechseln Sie wieder zur wöchentlichen Ansicht.

<div>


> [!TIP]  
> Im Monitoring-Dashboard werden Gesamtwerte für die aktuelle Woche (oder den aktuellen Monat) sowie Trendwerte für die letzten sechs Wochen (oder Monate) angezeigt. Diese Zeiträume können nicht geändert werden. Beispielsweise können Sie mit dem Dashboard keine Berichtgesamtwerte für die letzten neun Monate anzeigen.



</div>

Mit den Werten in den Spalten **Diese Woche**, **Dieser Monat** oder **Heute** sind jeweils ausführlichere Informationen verknüpft. Bedenken Sie, dass der Spaltenname und die darin angezeigten Werte oft voneinander abweichen, je nachdem, welche Metrik Sie auswählen und ob Sie die wöchentliche Ansicht oder die monatliche Ansicht ausgewählt haben. Wenn Sie z. B. auf die angezeigten Gesamtwerte für die Metrik **Eindeutige Benutzeranmeldungen** klicken, wird der **Bericht über Benutzerregistrierung** für den angegebenen Zeitraum angezeigt. Durch Klicken auf **Dashboard** können Sie jederzeit wieder zum Monitoring-Dashboard wechseln.

<div>


> [!TIP]  
> Sie können auch auf die Startseite für Monitoring Server Berichte zugreifen, indem Sie auf den Link <STRONG>Berichte</STRONG> in der oberen rechten Ecke des Dashboards klicken.



</div>

In der Spalte **Trend** wird ein einfaches Liniendiagramm mit den Gesamtwerten für die letzten sechs Wochen (oder in Abhängigkeit von der Metrik und dem Zeitintervall für die letzten sechs Tage oder die letzten sechs Monate) angezeigt. Diese einfachen Liniendiagramme enthalten einen unbeschrifteten Datenpunkt für jeden Zeitraum (z. B. einen unbeschrifteten Datenpunkt für jede der letzten sechs Wochen). Sie können jedoch tatsächliche Werte für diese Diagramme abrufen, indem Sie mit dem Mauszeiger auf das Diagramm zeigen. Es wird dann eine QuickInfo mit den maximalen und minimalen Werten im Diagramm angezeigt.

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>Exportieren von Daten aus dem Monitoring-Dashboard

Im Monitoring-Dashboard gibt es eine Reihe von Möglichkeiten zum Exportieren der aktuellen Dashboardansicht. In der Symbolleiste des Dashboards wird ein Symbol für eine Diskette mit einem grünen Pfeil angezeigt. Durch Klicken auf dieses Symbol wird eine Dropdownliste mit den folgenden Datenexportformaten angezeigt:

  - XML-Datei mit Berichtsdaten

  - CSV (Komma als Trennzeichen)

  - PDF

  - MHTML (Webarchiv)

  - Excel

  - TIFF-Datei

  - Word

Klicken Sie auf die gewünschte Exportoption, um die aktuelle Dashboardansicht (und deren Werte) zu exportieren. Lync Server 2013 generiert einen Bericht im angegebenen Format und gibt Ihnen dann die Möglichkeit, den Bericht zu öffnen oder zu speichern. Beachten Sie, dass lync Server standardmäßig das Dashboard für die Bericht **Überwachung** auftitelt und im Ordner "Downloads" speichert. Wenn Sie dem Bericht einen anderen Namen geben oder ihn in einem anderen Ordner speichern möchten, klicken Sie auf den Pfeil neben der Schaltfläche **Speichern** , und klicken Sie dann auf **Speichern**unter. Wenn Sie mit Name **Monitoring Dashboard** in Ordnung sind und der Bericht im Ordner "Downloads" gespeichert ist, können Sie einfach auf die Schaltfläche " **Speichern** " klicken.

Beim Exportieren von Dashboarddaten wird möglicherweise ein Sicherheitshinweis**** angezeigt, dass Ihre aktuellen Einstellungen das Herunterladen dieser Datei nicht zulassen. Führen Sie in diesem Fall die folgenden Aktionen aus:

  - Wählen Sie in Internet Explorer die Option **Internetoptionen** aus.

  - Klicken Sie im Dialogfeld **Internetoptionen** auf der Registerkarte **Sicherheit** auf **Vertrauenswürdige Sites** und dann auf **Sites**.

  - Klicken Sie im Dialogfeld **Vertrauenswürdige Sites** auf **Hinzufügen** , um die lync Server 2013, die lync Server 2013 Berichte ausführt, den Sammlungen vertrauenswürdiger Websites hinzuzufügen.

  - Klicken Sie auf **Schließen** und dann auf **OK**.

Anschließend müssen Sie das Monitoring-Dashboard aktualisieren, damit die Änderungen wirksam werden. Dazu drücken Sie entweder F5 oder klicken in der Symbolleiste des Dashboards auf das Symbol **Aktualisieren**. (Das Symbol **Aktualisieren** ist ein Kreis, in dem sich ein grünes Pfeilpaar befindet.)

Sie können auch eine Excel-Kalkulationstabelle mit Livedatenfeeds erstellen, die Links zu den neuesten Monitoring-Dashboard-Daten enthält. Zum Erstellen einer Livedatenfeed-Datei klicken Sie in der Symbolleiste auf das orangefarbene Symbol **In Datenfeed exportieren**.

Wenn Sie das aktuelle Dashboard drucken möchten, klicken Sie in der Symbolleiste auf das Druckersymbol.

</div>

</div>

<span> </span>

</div>

</div>

</div>

