---
title: Verwenden des CQD PSTN Direct Routing-Berichts
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Verwenden Sie den CQD PSTN Direct-Routing Bericht, um PSTN-Anrufe in Microsoft Teams zu überwachen und zu beheben.
ms.openlocfilehash: a3a7d84a21858b8cb2039f3f5bb6efde6b9adaaa
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221749"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Verwenden des CQD PSTN Direct Routing-Berichts

Neu im März 2020 haben wir unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen CQD PSTN Direct-Routing Bericht hinzugefügt. 


Der CQD PSTN Direct Routing-Bericht (CQD PSTN Direct Routing Report. PBit) hilft Ihnen, die Verwendungsmuster und die Qualität ihrer PSTN-Dienste zu verstehen. Verwenden Sie diesen Bericht, um die Dienstnutzung zu überwachen, Informationen zu Ihrem Session Border Controller (SBC), zum Telefoniedienst, zu den Netzwerkparametern und zu den Details des Netzwerk Effektivitäts Verhältnisses. Diese Informationen können Ihnen helfen, Probleme zu erkennen, einschließlich des Grunds für gelöschte Anrufe. So können Sie beispielsweise feststellen, ob die Lautstärke sinkt oder wie viele Anrufe betroffen sind und aus welchem Grund.


Der CQD PSTN Direct Routing-Bericht besteht aus vier Abschnitten:

  - [PSTN-Übersicht](#pstn-overview)

  - [Dienst Details](#service-details)

  - [Netzwerk-Effektivitäts Rate](#network-effectiveness-ratio)

  - [Netzwerkparameter](#network-parameters)

## <a name="highlights"></a>Hebt

1. Analysieren nach Anruftyp, SBC, Anrufer und Land des berufenen

   Der CQD PSTN Direct Routing-Bericht aggregiert die Zuverlässigkeits-und Nutzungs Metrik für alle SBCS Ihres Mandanten für die letzten 7, 30 oder 180 Tage (6 Monate). Sie können Daten nach Anruftyp, SBC, Rufnummernanzeige und Anruf Land analysieren. Wenn Sie an einem bestimmten SBC oder Land interessiert sind, werden Sie in der Lage sein, Änderungen an den Trends für den ausgewählten Zeitraum zu erkennen.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot der im CQD PSTN Direct Routing-Bericht verfügbaren Filter":::
   
2. Nachvollziehen von Trends

    Die Trendanalyse ist wichtig, wenn Sie versuchen, die Dienstnutzung und Zuverlässigkeit zu verstehen. Stündliche Trends bieten einen Einblick in die tägliche Leistung, die bei der Ermittlung von echtzeitereignissen hilft. Mit den täglichen Trends können Sie Ihre Dienst Integrität aus einer langfristigen Perspektive sehen. Es ist wichtig, in der Lage zu sein, zwischen diesen beiden Modi mit der entsprechenden Datengranularität zu wechseln. Der CQD PSTN Direct Routing-Bericht bietet eine Übersicht über sechs Monats Trends, 7-und 30-Tage-Tagestrends sowie stündliche Trends, damit Sie die Leistung auf jeder Ebene analysieren können.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot der Trenddiagramme in CQD PSTN Direct Routing-Bericht":::

3. Drillthrough zur SBC-oder Benutzerebene

   Wir haben in CQD in vielen Datenkategorien eine Drill-Through-Funktion erstellt, mit der Sie die Verwendung oder Zuverlässigkeits Verteilung auf SBC-oder Benutzerebene schnell verstehen können. Durch die Verwendung von Drill-Through können Sie Probleme schnell poinpoint und die Auswirkungen des realen Benutzers verstehen. Die CQD PSTN Direct Routing-Berichtsfeatures durchlaufen die Metriken Dienstdetails und Netzwerk Effektivitäts Verhältnis. Klicken Sie auf den Datenpunkt, an dem Sie interessiert sind, um die Details auf SBC-oder Benutzerebene zu durchlaufen.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot mit Drill-Through-Funktion auf einem Datenpunkt":::


## <a name="pstn-overview"></a>PSTN-Übersicht

Der CQD PSTN Direct-Routing Bericht enthält die folgenden Informationen zum Gesamtzustand des Diensts für die letzten 180 Tage.
![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report1.png)

Wenn Sie beispielsweise an der allgemeinen Nutzung und der Integrität für alle eingehenden Anrufe interessiert sind, die über SBC-ABC.BCA.adatum.biz mit uns als internes Land laufen, gehen Sie wie folgt vor:

| **Anrufen** | **Beschreibung**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Sie können die Filter oben verwenden, um einen Drilldown durchführen und ByotIn als Anruftyp, ABC.BCA.contoso.com als Sitzungs Boarder-Controller und US als internes Land auszuwählen. |
| 2            | Verwendungs Trend für die letzten 180 Tage. Sie finden den Verwendungs Detailbericht auf der Seite "Dienstdetails".                                                                     |
| 3            | Nach Wahl Verzögerung, Latenz, Jitter und Paketverlust Trend für die letzten 180 Tage. Sie finden den Detailbericht auf der Seite Netzwerkparameter.                           |
| 4            | Gleichzeitiger Anruf und Trend des täglichen aktiven Benutzers für die letzten 180 Tage. Dieses Diagramm kann Ihnen helfen, die maximale Lautstärke des Diensts zu verstehen.                            |
| 5            | Der Grund für den oberen Anruf Ende hat die Servicequalität in den letzten 180 Tagen beeinträchtigt. Sie finden die Details zum Dienststatus auf der Seite Netzwerk effektives Verhältnis (ner).                    |

## <a name="service-details"></a>Dienst Details

Auf dieser Seite werden die Trends für die Dienst Verwendung pro Tag und die Aufteilung der Benutzer Feedback nach geografischen Informationen angezeigt.

  - **Aufrufe für Gesamt Versuch –** Aufrufe für Gesamt Versuch in diesem Zeitraum, einschließlich Erfolg und fehlgeschlagener Anrufe

  - **Verbundene Anrufe insgesamt –** Gesamtzahl der verbundenen Anrufe in diesem Zeitraum

  - **Gesamtanzahl der Minuten –** Gesamt Minuten Verbrauch in diesem Zeitbereich

  - **Tägliche aktive Nutzer (Dau) –** Die Anzahl des täglichen aktiven Benutzers, der an diesem Tag mindestens einen verbundenen Anruf getätigt hat

  - **Gleichzeitige Anrufe –** Max. gleichzeitiger aktiver Anrufe in einer Minute

  - **Nutzer Feedback –** Die Punktzahl "meinen Anruf bewerten" stammt vom Nutzer. 3-5 wird als guter Anruf angesehen. 1-2 wird als schlechter Anruf angesehen.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report2.png)

Beispiel:

1.  Wenn die durchschnittliche Anrufdauer bei 02/14/2020 auf 0 fällt, können Sie zuerst überprüfen, ob die Anruflautstärke normal aussieht, und sehen, ob es eine große Diskrepanz zwischen Gesamt-Connect-anrufen und totalen Versuchs aufrufen gibt. Wechseln Sie dann zur Seite Netzwerk-Effektivitäts Rate, um aus Gründen des Anruf Fehlers zu investieren.

2.  Wenn in der Benutzer Feedback Karte steigende rote Punkte angezeigt werden, können Sie zur Seite Netzwerk-Effektivitäts Rate und Netzwerk Parameter wechseln, um festzustellen, ob es Anomalien gibt, und Sie können ein Ticket mit MS Service Desk auslösen.

## <a name="network-effectiveness-ratio"></a>Netzwerk-Effektivitäts Rate

Dies ist die gleiche Metrik, die im allgemeinen Status-Dashboard angezeigt wird. Sie können die Anzahl der stündlichen Unternehmen mit betroffenen Anrufdetails für beide Anruf Richtungen (eingehend/ausgehend) über das stündliche Netzwerk-Effektivitäts Verhältnis und das Grund Diagramm für das Ende des Anrufs nach unten prüfen.

  - **Ner** -die Fähigkeit (%) eines Netzwerks, um Anrufe zu übermitteln, indem Sie die Anzahl der Anrufe im Vergleich zur Anzahl der Anrufe an einen Empfänger messen.

  - **SIP-Antwortcode**– ein dreistelliger ganzzahliger Antwortcode zeigt den Anrufstatus an.

  - **Microsoft Response Code**– ein Antwortcode, der von der Microsoft-Komponente gesendet wurde.

  - **Beschreibung** – die Grund Phase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.

  - **Anzahl der betroffenen Anrufe** – die Gesamtzahl der Anrufe wurde während des ausgewählten Zeitbereichs beeinträchtigt.

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report3.png)
> 
Beispiel:

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report4.png)

Wenn Sie täglich ein Bad auf 02/05/2020 haben, können Sie auf das Datum klicken, und andere Diagramme Zoomen auf das jeweilige Datum.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report5.png)

Ab dem guten prozentualen stündlichen Trend können Sie die DIP-Vorgänge rund um 21:00 finden. Klicken Sie dann erneut, um die Uhrzeit zu verkleinern, und überprüfen Sie die gewünschten Anruf Details, um zu sehen, wie viele Anrufe in dieser Stunde fehlschlugen und was die Gründe für das Anruf Ende sind. Sie können mit der selbst Behebung von Problemen bei SBC beginnen oder an Service Desk melden, wenn das Problem nicht mit SBC in Verbindung steht.

## <a name="network-parameters"></a>Netzwerkparameter

Alle Netzwerkparameter werden von der direkten Routing Schnittstelle zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)und untersuchen der empfohlenen Werte für den Kunden Rand zu Microsoft Edge.

  - **Jitter** – ist das Millisekunden-Maß der Variation in der Verzögerungszeit für die Netzwerk Propagierung, die zwischen zwei Endpunkten mithilfe von RTCP (dem RTP-steuerelementprotokoll) berechnet wird.

  - **Paketverlust** – ist ein Maß für ein Paket, das nicht ankommt; Sie wird zwischen zwei Endpunkten berechnet.

  - **Latenz** – (auch als Roundtrip-Zeit bezeichnet) ist die Zeitdauer, die für das Senden eines Signals benötigt wird, sowie die Zeitdauer, die für die Empfangsbestätigung des Signals benötigt wird. Diese Zeitverzögerung besteht aus den Ausbreitungs Zeiten zwischen den beiden Punkten eines Signals.

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report6.png)

Beispiel:

Wenn Sie eine Spitze in einem der vier Diagramme (Latenz, Jitter, Paketverlust Rate, nach Wahl Verzögerung) für ein bestimmtes Datum sehen, beispielsweise Latenz auf 02/14/2020, klicken Sie auf den Datums Punkt. Und das stündliche Trenddiagramm unten wird aktualisiert, um die stündliche Zahl anzuzeigen. Sie können das SBCS überprüfen oder ein Ticket mit MS Service Desk auslösen.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams](CQD-PSTN-report.md)