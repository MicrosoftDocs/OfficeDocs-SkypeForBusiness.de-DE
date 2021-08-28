---
title: Verwenden des PstN-Direktroutingberichts für CQD
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
description: Verwenden Sie Microsoft Teams PSTN Direct Routing-Bericht (Microsoft Teams Call Quality Dashboard, CQD) PSTN Direct Routing, um PSTN-Anrufe in ihrem Netzwerk zu überwachen Microsoft Teams.
ms.openlocfilehash: 18e24690fe86bf7efd511bea674c3d3d7eba3e43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635059"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Verwenden des PstN-Direktroutingberichts für CQD

Neu im März 2020 ist, dass wir unseren herunterladbaren Power BI-Abfragevorlagen für CQD einen PstN Direct Routing-Bericht (Microsoft Teams Call Quality Dashboard, [CQD)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)hinzugefügt haben. 


Der CQD PSTN Direct Routing Report (CQD PSTN Direct Routing Report.pbit) hilft Ihnen, die Verwendungsmuster und die Qualität Ihrer PSTN-Dienste zu verstehen. Verwenden Sie diesen Bericht zum Überwachen der Dienstnutzung, Informationen über Ihren Session Border Controller (SBC), den Telefoniedienst, Netzwerkparameter und Details zum Netzwerkeffektivitätsverhältnis. Diese Informationen können Ihnen dabei helfen, Probleme zu erkennen, einschließlich des Grunds für verworfene Anrufe. So können Sie beispielsweise sehen, wann die Lautstärke sinkt oder wie viele Anrufe betroffen sind und aus welchem Grund.


Der PstN-Direktroutingbericht für das CQD-Format enthält vier Abschnitte:

  - [PSTN-Übersicht](#pstn-overview)

  - [Servicedetails](#service-details)

  - [Netzwerkeffektivitätsverhältnis](#network-effectiveness-ratio)

  - [Netzwerkparameter](#network-parameters)

## <a name="highlights"></a>Highlights

1. Analysieren nach Anruftyp, SBC, Anrufer- und Anruferland

   Im Bericht CQD PSTN Direct Routing werden Zuverlässigkeits- und Nutzungsmetriken für alle SBCs in Ihrem Mandanten für die letzten 7, 30 oder 180 Tage (6 Monate) zusammengefasst. Sie können Daten nach Anruftyp, SBC, Anrufer- und Anruferland analysieren. Wenn Sie an einem bestimmten SBC oder Land interessiert sind, können Sie Änderungen an Trends im ausgewählten Zeitraum erkennen.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot der filter available in the CQD PSTN Direct Routing report":::
   
2. Nachverfolgen von Trends

    Die Analyse von Trends ist unerlässlich, wenn Sie versuchen, die Nutzung von Dienstleistungen und die Zuverlässigkeit zu verstehen. Stündlich gegebene Trends bieten einen genauen Blick auf die tägliche Leistung, wodurch Vorfälle in Echtzeit identifiziert werden können. Bei täglichen Trends können Sie Ihren Dienstzustand langfristig betrachten. Es ist wichtig, dass Sie mit einer geeigneten Daten granularität zwischen diesen beiden Modi wechseln können. Der Bericht PSTN-Direktrouting für AQD-Nachrichten enthält eine Übersicht über die 6-Monat-Trends, Tagestrends für 7 und 30 Tage sowie Stündtrends, damit Sie die Leistung auf den einzelnen Ebenen analysieren können.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot of trends graphs in CQD PSTN Direct Routing report":::

3. Drill through to SBC or user level

   Wir haben Drillthrough-Funktionen für viele Datenkategorien im AQD aufbauen, mit denen Sie die Nutzung oder Zuverlässigkeitsverteilung auf SBC- oder Benutzerebene schnell verstehen können. Mithilfe von Drillthrough können Sie Probleme an interessanten Themen schnell finden und die Auswirkungen der realen Benutzer verstehen. Die Features des PstN Direct Routing-Berichts für das CQD-Routing führen einen Drilldown zu den Metriken "Dienstdetails" und "Netzwerkeffektivitätsverhältnis" durch. Klicken Sie auf den Datenpunkt, an dem Sie interessiert sind, um Drilldowns zu Details auf SBC- oder Benutzerebene anzuzeigen.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot showing drill-through capability on a data point":::


## <a name="pstn-overview"></a>PSTN-Übersicht

Der PstN-Direktroutingbericht für AQD enthält die folgenden Informationen zum Gesamtzustand des Diensts für die letzten 180 Tage.
![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report1.png)

Wenn Sie z. B. an der Gesamtverwendung und Integrität aller eingehenden Anrufe interessiert sind, die über SBC abc.bca.adatum.biz mit den USA als internem Land gehen, gehen Sie wie folgt vor:

| **Herausrufen** | **Beschreibung**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Sie können die oben angezeigten Filter verwenden, um einen Drilldown zu starten und ByotIn als Anruftyp auszuwählen, abc.bca.contoso.com Session Boarder Controller und USA als internes Land auszuwählen. |
| 2            | Nutzungstrend für die letzten 180 Tage. Einen Verwendungsdetailbericht finden Sie auf der Seite "Dienstdetails".                                                                     |
| 3            | Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days. Sie finden den Detailbericht auf der Seite Netzwerkparameter.                           |
| 4            | Gleichzeitiger Anruf- und täglich aktiver Benutzer-Trend für die letzten 180 Tage. Mithilfe dieses Diagramms können Sie die maximale Lautstärke des Diensts besser verstehen.                            |
| 5            | Top Call End Reason affected service quality for the past 180 days. Details zum Dienstzustand finden Sie auf der Seite Network Effective Ratio (NER).                    |

## <a name="service-details"></a>Servicedetails

Diese Seite enthält Trends bei der Dienstnutzung pro Tag und eine Aufschlüsselung des Benutzerfeedbacks nach geografischer Position.

  - **Aufrufe gesamter Versuche –** Aufrufe aller Versuche in diesem Zeitraum, einschließlich erfolgloser und fehlgeschlagener Aufrufe

  - **Verbundene Anrufe gesamt –** Gesamtzahl der verbundenen Anrufe in diesem Zeitraum

  - **Gesamtminuten –** Gesamtminutenverwendung in diesem Zeitraum

  - **Täglich aktive Benutzer (DAILY Active Users, DAU) –** Die Anzahl der täglich aktiven Benutzer, die an diesem Tag mindestens einen verbundenen Anruf tätigt haben

  - **Gleichzeitige Anrufe –** Maximale Anzahl gleichzeitiger aktiver Anrufe in einer Minute

  - **Benutzerfeedback –** Die Bewertung "Meinen Anruf bewerten" stammt vom Benutzer. 3-5 wird als ein guter Anruf angesehen. 1-2 wird als ein schlechter Anruf angesehen.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report2.png)

Zum Beispiel:

1.  Wenn Sie sehen, dass die durchschnittliche Anrufdauer am 14.02.2020 auf 0 sinkt, können Sie zunächst überprüfen, ob die Anruflautstärke normal aussieht, und prüfen, ob es einen großen Unterschied zwischen den Gesamtanrufen und den Gesamtanrufversuchen gibt. Wechseln Sie dann zur Seite Netzwerkeffektivitätsverhältnis, um in Fehlergründe für Anrufe zu investieren.

2.  Wenn auf der Karte für Benutzerfeedback zunehmend rote Punkte angezeigt werden, könnten Sie zur Seite Netzwerkeffektivitätsverhältnis und zu Netzwerkparameter wechseln, um zu sehen, ob Anomalien vorhanden sind und Sie ein Ticket mit MS Service Desk lösen könnten.

## <a name="network-effectiveness-ratio"></a>Netzwerkeffektivitätsverhältnis

Dies ist die gleiche Metrik, die im Dashboard Gesamtzustand angezeigt wird. Sie können stündlich NER-Nummer mit Detail für betroffene Anrufe für beide Anrufrichtungen (eingehend/ausgehend) im Diagramm Effektivität pro Stunde im Netzwerk und Diagramm zum Beenden des Anrufs unten überprüfen.

  - **NER** – Die Fähigkeit (%) eines Netzwerks, Anrufe zu liefern, indem die Anzahl der gesendeten Anrufe im Vergleich zur Anzahl der an einen Empfänger zugestellten Anrufe gemessen wird.

  - **SIP-Antwortcode–** Der Anrufstatus wird als dreistelliger ganzzahliger Antwortcode angezeigt.

  - **Microsoft-Antwortcode**– Ein von der Microsoft-Komponente gesendeter Antwortcode.

  - **Beschreibung** – Die Grundphase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.

  - **Anzahl betroffener Anrufe** – Die Gesamtzahl der Anrufe wurde im ausgewählten Zeitraum beeinflusst.

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report3.png)
> 
Zum Beispiel:

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report4.png)

Wenn Tages-NER am 05.02.2020 ein Einbruch hat, können Sie auf das Datum klicken, und andere Diagramme zoomen auf dieses bestimmte Datum.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report5.png)

Aus dem NER-Trend "Guter Prozentsatz pro Stunde" können Sie feststellen, dass das Einbruch um 21:00 Uhr erfolgt. Klicken Sie dann erneut, um auf Stunde 21 zu zoomen, und aktivieren Sie Effekt-Anrufdetails, um zu sehen, wie viele Anrufe in dieser Stunde fehlgeschlagen sind und welche Gründe für das Ende des Anrufs liegen. Sie können mit dem Schießen mit Selbstshooter bei SBC-Problemen beginnen oder Service Desk melden, wenn das Problem nicht im Zusammenhang mit SBC steht.

## <a name="network-parameters"></a>Netzwerkparameter

Alle Netzwerkparameter werden von der Direct Routing-Schnittstelle zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter Vorbereiten des Unternehmensnetzwerks für [Microsoft Teams](prepare-network.md)und Unter Kunden-Edge finden Sie Informationen Microsoft Edge empfohlenen Werte.

  - **Jitter** – Ist das Maß für die Variation der Verzögerungszeit bei der Netzwerkverteilung in Millisekunden, die mithilfe von RTCP (The RTP Control Protocol) zwischen zwei Endpunkten berechnet wird.

  - **Packet Loss** – Ist ein Maß für das Paket, das nicht ankommt; wird zwischen zwei Endpunkten berechnet.

  - **Latenz** (auch als Roundtripzeit bezeichnet) ist die Dauer, die es dauert, bis ein Signal gesendet wird, zuzüglich der Zeit, die es dauert, bis die Bestätigung des Signals empfangen wurde. Diese Zeitverzögerung besteht aus den Weitergabezeiten zwischen den beiden Punkten eines Signals.

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report6.png)

Zum Beispiel:

Wenn bei einem der vier Diagramme (Latenz, Jitter, Paketverlustrate, Nach Wählverzögerung) für ein bestimmtes Datum eine Spitzengeschwindigkeit angezeigt wird, z. B. Latenz am 14.02.2020, klicken Sie auf den Datumspunkt. Und das Trenddiagramm mit Stunden am unteren Rand wird aktualisiert und zeigt die Stundenzahl an. Sie können die SBCs überprüfen oder ein Ticket bei MS Service Desk erheben.

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Verwandte Themen

[Verwenden Power BI zum Analysieren von AQD-Daten für Microsoft Teams](CQD-PSTN-report.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)