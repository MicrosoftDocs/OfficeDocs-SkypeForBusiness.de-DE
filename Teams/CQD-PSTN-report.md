---
title: Verwenden des CQD PSTN Direct Routing-Berichts
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
localization_priority: Normal
description: Verwenden Sie den Microsoft Teams Call Quality Dashboard (CQD))-PstN Direct Routing-Bericht, um PSTN-Anrufe in Microsoft Teams zu überwachen und zu behandeln.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094979"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Verwenden des CQD PSTN Direct Routing-Berichts

Neu im März 2020 haben wir unseren herunterladbaren Power BI-Abfragevorlagen für [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen CQD (Call Quality Dashboard, CQD) PSTN Direct Routing-Bericht hinzugefügt. 


Der CQD PSTN Direct Routing Report (CQD PSTN Direct Routing Report.pbit) hilft Ihnen, die Verwendungsmuster und die Qualität Ihrer PSTN-Dienste zu verstehen. Verwenden Sie diesen Bericht, um die Dienstnutzung, Informationen zu Ihrem Session Border Controller (SBC), den Telefoniedienst, Netzwerkparametern und Details zum Netzwerkeffektivitätsverhältnis zu überwachen. Diese Informationen können Ihnen helfen, Probleme zu identifizieren, einschließlich des Grunds für verworfene Anrufe. So können Sie beispielsweise sehen, wann die Lautstärke sinkt oder wie viele Anrufe betroffen sind und aus welchem Grund.


Der CQD PSTN Direct Routing Report enthält vier Abschnitte:

  - [Übersicht über DAS FESTNETZ](#pstn-overview)

  - [Servicedetails](#service-details)

  - [Netzwerkeffektivitätsverhältnis](#network-effectiveness-ratio)

  - [Netzwerkparameter](#network-parameters)

## <a name="highlights"></a>Highlights

1. Analysieren nach Anruftyp, SBC, Anrufer- und Anruferland

   Der Bericht CQD PSTN Direct Routing aggregiert Zuverlässigkeits- und Nutzungsmetriken für alle SBCs in Ihrem Mandanten für die letzten 7, 30 oder 180 Tage (6 Monate). Sie können Daten nach Anruftyp, SBC, Anrufer- und Anruferland analysieren. Wenn Sie an einem bestimmten SBC oder Land interessiert sind, können Sie Trendsänderungen im ausgewählten Zeitraum erkennen.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot der im Bericht "CQD PSTN Direct Routing" verfügbaren Filter":::
   
2. Nachverfolgen von Trends

    Trendsanalyse ist bei dem Versuch, die Dienstnutzung und Zuverlässigkeit zu verstehen, von wesentlicher Bedeutung. Stundentrends bieten einen genauen Blick auf die tägliche Leistung, wodurch Vorfälle in Echtzeit identifiziert werden können. Mit täglichen Trends können Sie ihren Dienstzustand langfristig sehen. Es ist wichtig, zwischen diesen beiden Modi mit entsprechender Daten granularität wechseln zu können. Der CQD PSTN Direct Routing-Bericht bietet eine Übersicht über sechsmonatige Trends, tägliche 7- und 30-Tage-Trends sowie Stündtrends, damit Sie die Leistung auf jeder Ebene analysieren können.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot von Trendsdiagrammen im CQD PSTN Direct Routing Report":::

3. Drill through to SBC or user level

   Wir haben drill-through-Funktionen für viele Datenkategorien in CQD verbessert, wodurch Sie die Verwendung oder Zuverlässigkeitsverteilung auf SBC- oder Benutzerebene schnell verstehen können. Mithilfe von Drillthrough können Sie Probleme schnell auf den Punkt bringen und die auswirkungen der echten Benutzer verstehen. Die Features des CQD PSTN Direct Routing-Berichts führen einen Drillthrough zu den Metriken "Dienstdetails" und "Netzwerkeffektivitätsverhältnis" durch. Klicken Sie auf den Datenpunkt, an dem Sie interessiert sind, um einen Drilldown zu SBC- oder Details auf Benutzerebene zu erstellen.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot der Drill-Through-Funktion an einem Datenpunkt":::


## <a name="pstn-overview"></a>Übersicht über DAS FESTNETZ

Der CQD PSTN Direct Routing Report enthält die folgenden Informationen zum Gesamtzustand des Diensts für die letzten 180 Tage.
![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report1.png)

Wenn Sie z. B. an der allgemeinen Nutzung und Integrität aller eingehenden Anrufe interessiert sind, die über SBC abc.bca.adatum.biz usa als internes Land gehen:

| **Herausrufen** | **Beschreibung**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Sie können die Filter oben verwenden, um einen Drilldown zu erstellen und ByotIn als Anruftyp, abc.bca.contoso.com als Session Boarder Controller und USA als internes Land auszuwählen. |
| 2            | Nutzungstrend für die letzten 180 Tage. Sie finden den Nutzungsdetailsetailbericht auf der Seite Dienstdetails.                                                                     |
| 3            | Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days. Sie finden den Detailbericht auf der Seite Netzwerkparameter.                           |
| 4            | Trend "Gleichzeitiger Anruf" und "Täglich aktiver Benutzer" für die letzten 180 Tage. Dieses Diagramm kann Ihnen dabei helfen, die maximale Lautstärke des Diensts zu verstehen.                            |
| 5            | Die Dienstqualität der letzten 180 Tage war von der Obersten Anrufende-Ursache betroffen. Details zum Dienstzustand finden Sie auf der Seite Network Effective Ratio(NER).                    |

## <a name="service-details"></a>Servicedetails

Auf dieser Seite werden die Trends der Dienstnutzung pro Tag und das Benutzerfeedback nach geografischen Standorten angezeigt.

  - **Gesamtversuchsaufrufe –** Gesamtversuchsaufrufe in diesem Zeitraum, einschließlich erfolg- und fehlgeschlagener Aufrufe

  - **Verbundene Anrufe insgesamt –** Summe verbundener Anrufe in diesem Zeitraum

  - **Gesamtminuten –** Gesamtminutennutzung in diesem Zeitraum

  - **Tägliche aktive Benutzer (DAU) –** Anzahl der täglich aktiven Benutzer, die an diesem Tag mindestens einen verbundenen Anruf gemacht haben

  - **Gleichzeitige Anrufe –** Max. gleichzeitige aktive Anrufe in einer Minute

  - **Benutzerfeedback –** Die Bewertung "Mein Anruf bewerten" stammt vom Benutzer. 3-5 wird als guter Anruf betrachtet. 1-2 wird als ungültiger Anruf betrachtet.

![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report2.png)

Beispiel:

1.  Wenn die durchschnittliche Anrufdauer am 14.02.2020 auf 0 sinkt, können Sie zuerst überprüfen, ob die Anruflautstärke normal aussieht, und prüfen, ob es eine große Diskrepanz zwischen den gesamten Verbindungsanrufen und den Gesamtanrufen gibt. Wechseln Sie dann zur Seite Netzwerkeffektivitätsverhältnis, um aus Gründen des Anruffehlers zu investieren.

2.  Wenn auf der Benutzerfeedbackkarte zunehmend rote Punkte angezeigt werden, können Sie zur Seite Netzwerkeffektivitätsverhältnis und Netzwerkparameter wechseln, um zu sehen, ob Anomalien vorhanden sind und Sie ein Ticket mit MS Service Desk lösen können.

## <a name="network-effectiveness-ratio"></a>Netzwerkeffektivitätsverhältnis

Dies ist die gleiche Metrik, die im Dashboard Gesamtzustand angezeigt wird. Sie können die Stündlich-NN-Nummer mit den betroffenen Anrufdetails für beide Anrufanrufrichtungen (ein-/ausgehend) im unten angegebenen Diagramm zur Effektivität des Stundennetzwerks und zum Ende des Anrufs überprüfen.

  - **NER** – Die Fähigkeit (%) eines Netzwerks, um Anrufe zu senden, indem sie die Anzahl der an einen Empfänger gesendeten Anrufe im Vergleich zur Anzahl der an einen Empfänger übermittelten Anrufe misst.

  - **SIP-Antwortcode**: Ein dreistelliger ganzzahliger Antwortcode zeigt den Anrufstatus an.

  - **Microsoft-Antwortcode**– Ein Von der Microsoft-Komponente gesendeter Antwortcode.

  - **Beschreibung** – Die Grundphase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.

  - **Anzahl der betroffenen Anrufe** – Die Gesamtanzahl der Anrufe wurde während des ausgewählten Zeitraums betroffen.

> ![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report3.png)
> 
Beispiel:

![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report4.png)

Wenn daily NER am 05.02.2020 einen Dip hat, können Sie auf das Datum klicken, und andere Diagramme zoomen auf dieses bestimmte Datum.

![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report5.png)

Im NER Good Percentage Hourly Trend können Sie feststellen, dass der Dip um 21:00 Uhr erfolgt. Klicken Sie dann erneut, um auf Stunde 21 zu zoomen, und überprüfen Sie Effektierte Anrufdetails, um zu sehen, wie viele Anrufe in dieser Stunde fehlgeschlagen sind und was die Gründe für das Anrufende sind. Sie können mit der Selbstproblemaufnahme bei allen SBC-Problemen beginnen oder sich an Service Desk melden, wenn das Problem nicht mit SBC zusammenhing.

## <a name="network-parameters"></a>Netzwerkparameter

Alle Netzwerkparameter werden von der Direct Routing-Schnittstelle bis zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter Vorbereiten des Netzwerks Ihrer Organisation für [Microsoft Teams,](prepare-network.md)und sehen Sie sich die empfohlenen Werte von Customer Edge zu Microsoft Edge an.

  - **Jitter** – Ist das Millisekundenmaß für die Variation der Verzögerungszeit für die Netzwerkweitergabe, die zwischen zwei Endpunkten mithilfe von RTCP (RtP-Steuerelementprotokoll) berechnet wird.

  - **Paketverlust** – Ist ein Maß für das Paket, das nicht eintrifft; es wird zwischen zwei Endpunkten berechnet.

  - **Latenz –** (auch als Roundtripzeit bezeichnet) ist die Dauer, die es dauert, bis ein Signal gesendet wird, zuzüglich der Zeit, die es dauert, bis die Bestätigung dieses Signals empfangen wird. Diese Zeitverzögerung besteht aus den Übertragungszeiten zwischen den beiden Punkten eines Signals.

> ![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report6.png)

Beispiel:

Wenn in einem der vier Diagramme (Latenz, Jitter, Paketverlustrate, Nachwählverzögerung) für ein bestimmtes Datum eine Spitzenspitze angezeigt wird, z. B. Latenz am 14.02.2020, klicken Sie auf den Datumspunkt. Und das Stundentrenddiagramm unten wird aktualisiert, um die Stundenzahl zu zeigen. Sie können die SBCs überprüfen oder ein Ticket bei MS Service Desk lösen.

![Screenshot: PSTN CQD-Bericht](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams](CQD-PSTN-report.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)