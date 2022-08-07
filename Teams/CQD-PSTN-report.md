---
title: Verwenden des CQD-PSTN-Direct Routing-Berichts
author: CarolynRowe
ms.author: crowe
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
description: Verwenden Sie den PSTN-Direct Routing-Bericht des Microsoft Teams-Anrufqualitätsdashboards (CQD), um PSTN-Anrufe in Microsoft Teams zu überwachen und zu beheben.
ms.openlocfilehash: 7b7205658358cfa3aa90824718c03731fa33a534
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270710"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Verwenden des CQD-PSTN-Direct Routing-Berichts

Der PSTN Direct Routing-Bericht des Microsoft Teams-Anrufqualitätsdashboards (CQD) ist in unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://www.microsoft.com/download/details.aspx?id=102291) verfügbar. 


Der CQD PSTN Direct Routing-Bericht (CQD PSTN Direct Routing Report.pbit) hilft Ihnen, die Nutzungsmuster und die Qualität Ihrer PSTN-Dienste zu verstehen. Verwenden Sie diesen Bericht, um die Dienstnutzung, Informationen zu Ihrem Session Border Controller (SBC), den Telefoniedienst, Netzwerkparameter und Details zum Netzwerkeffektivitätsverhältnis zu überwachen. Diese Informationen können Ihnen helfen, Probleme zu identifizieren, einschließlich des Grunds für abgebrochene Anrufe. So können Sie beispielsweise sehen, wann die Lautstärke sinkt, wie viele Anrufe betroffen sind und aus welchem Grund.


Der CQD-PSTN-Direct Routing-Bericht umfasst vier Abschnitte:

  - [PSTN-Übersicht](#pstn-overview)

  - [Dienstdetails](#service-details)

  - [Netzwerkeffektivitätsverhältnis](#network-effectiveness-ratio)

  - [Netzwerkparameter](#network-parameters)

## <a name="highlights"></a>Highlights

1. Analysieren nach Anruftyp, SBC, Anrufer und Land des Angerufenen

   Der CQD PSTN Direct Routing-Bericht aggregiert Zuverlässigkeits- und Nutzungsmetriken für alle SBCs auf Ihrem Mandanten für die letzten 7, 30 oder 180 Tage (6 Monate). Sie können Daten nach Anruftyp, SBC, Anrufer und Land des Angerufenen analysieren. Wenn Sie an einem bestimmten SBC oder Land interessiert sind, können Sie Änderungen der Trends im ausgewählten Zeitraum identifizieren.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot der im Bericht &quot;CQD PSTN Direct Routing&quot; verfügbaren Filter.":::
   
2. Nachverfolgen von Trends

    Trendsanalyse ist wichtig, wenn Sie versuchen, die Dienstnutzung und Zuverlässigkeit zu verstehen. Stündliche Trends bieten einen genauen Blick auf die tägliche Leistung, was dazu beiträgt, Echtzeitvorfälle zu identifizieren. Mit den täglichen Trends können Sie Ihren Dienststatus aus einer langfristigen Perspektive betrachten. Es ist wichtig, zwischen diesen beiden Modi mit entsprechender Datengranularität wechseln zu können. Der Bericht "CQD PSTN Direct Routing" bietet eine Übersicht über 6-Monatstrends, tagesaktuelle 7- und 30-Tage-Trends sowie Stündliche Trends, sodass Sie die Leistung auf jeder Ebene analysieren können.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot der Trendsdiagramme im CQD-Bericht &quot;PSTN Direct Routing&quot;.":::

3. Drilldown auf SBC- oder Benutzerebene

   Wir haben drill-through-Funktionen für viele Datenkategorien in CQD erstellt, mit denen Sie die Nutzungs- oder Zuverlässigkeitsverteilung auf SBC- oder Benutzerebene schnell verstehen können. Mithilfe von Drill-Through können Sie Probleme schnell erkennen und die tatsächlichen Auswirkungen der Benutzer verstehen. Die CQD-PSTN-Direct Routing-Berichtfeatures führen einen Drilldown über die Metriken "Service Detail" und "Network Effectiveness Ratio" durch. Klicken Sie auf den Datenpunkt, an dem Sie interessiert sind, um einen Drilldown zu Details auf SBC- oder Benutzerebene zu erhalten.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot der Drill-Through-Funktion an einem Datenpunkt.":::


## <a name="pstn-overview"></a>PSTN-Übersicht

Der CQD-PSTN-Direct Routing-Bericht enthält die folgenden Informationen zum allgemeinen Status des Diensts für die letzten 180 Tage.
![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report1.png)

Wenn Sie z. B. an der allgemeinen Nutzung und Integrität aller eingehenden Anrufe interessiert sind, die über SBC-abc.bca.adatum.biz mit US als internem Land gehen:

| **Anruf aus** | **Beschreibung**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Mithilfe der Filter oben können Sie einen Drilldown ausführen und ByotIn als Anruftyp, abc.bca.contoso.com als Session Boarder Controller und US als internes Land auswählen. |
| 2            | Nutzungstrend der letzten 180 Tage. Sie finden den Nutzungsdetailbericht auf der Seite "Dienstdetails".                                                                     |
| 3            | Trend nach Wählverzögerung, Latenz, Jitter und Paketverlust für die letzten 180 Tage. Der Detailbericht finden Sie auf der Seite "Netzwerkparameter".                           |
| 4            | Der Trend "Gleichzeitiger Anruf" und "Täglich aktiver Benutzer" in den letzten 180 Tagen. Dieses Diagramm kann Ihnen helfen, das maximale Volumen des Diensts zu verstehen.                            |
| 5            | Der wichtigste Grund für das Anrufende hat sich in den letzten 180 Tagen auf die Servicequalität ausgewirkt. Informationen zum Dienststatus finden Sie auf der Seite "Network Effective Ratio(NER)".                    |

## <a name="service-details"></a>Dienstdetails

Diese Seite enthält Dienstnutzungstrends pro Tag und eine Aufschlüsselung des Benutzerfeedbacks nach geografischen Standorten.

  - **Aufrufe des Gesamtversuchs –** Gesamtanzahl der Versuche in diesem Zeitraum, einschließlich erfolgreicher und fehlgeschlagener Aufrufe

  - **Gesamtzahl der verbundenen Anrufe -** Gesamtzahl der verbundenen Anrufe in diesem Zeitraum

  - **Gesamtminuten –** Gesamtminutennutzung in diesem Zeitraum

  - **Daily Active Users(DAU) –** Anzahl der täglich aktiven Benutzer, die an diesem Tag mindestens einen verbundenen Anruf getätigt haben

  - **Gleichzeitige Anrufe –** Max. gleichzeitige aktive Anrufe in einer Minute

  - **Benutzerfeedback –** Die Bewertung "Meinen Anruf bewerten" stammt vom Benutzer. 3-5 gilt als guter Anruf. 1-2 wird als schlechter Anruf betrachtet.

![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report2.png)

Zum Beispiel: 

1.  Wenn die durchschnittliche Anrufdauer am 14.02.2020 auf 0 fällt, können Sie zunächst überprüfen, ob das Anrufvolumen normal aussieht, und feststellen, ob es eine große Abweichung zwischen den Gesamtanrufen und den Gesamtversuchsaufrufen gibt. Wechseln Sie dann zur Seite "Netzwerkeffektivitätsverhältnis", um aufgrund von Anruffehlern zu investieren.

2.  Wenn auf der Benutzerfeedbackkarte immer mehr rote Stellen angezeigt werden, können Sie zur Seite "Netzwerkeffektivitätsverhältnis" und "Netzwerkparameter" wechseln, um festzustellen, ob Anomalien vorliegen, und Sie könnten ein Ticket mithilfe von MS Service Desk auslösen.

## <a name="network-effectiveness-ratio"></a>Netzwerkeffektivitätsverhältnis

Dies ist die gleiche Metrik, die im Dashboard "Gesamtzustand" angezeigt wird. Sie können die stündliche NER-Nummer mit den betroffenen Anrufdetails für beide Anrufanweisungen (eingehend/ausgehend) im nachstehenden Diagramm zur Effektivität des Stündlich-Netzwerks und des Anrufendgrunddiagramms überprüfen.

  - **NER –** Die Fähigkeit (%) eines Netzwerks, Anrufe zu tätigen, indem die Anzahl der gesendeten Anrufe im Vergleich zur Anzahl der Angerufenen gemessen wird.

  - **SIP-Antwortcode**: Ein dreistelliger ganzzahliger Antwortcode zeigt den Anrufstatus an.

  - **Microsoft-Antwortcode**– Ein Antwortcode, der von der Microsoft-Komponente gesendet wurde.

  - **Beschreibung** – Die Grundphase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.

  - **Anzahl der betroffenen Anrufe** – Die Gesamtanzahl der Anrufe, die während des ausgewählten Zeitraums betroffen waren.

> ![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report3.png)
> 
Zum Beispiel: 

![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report4.png)

Wenn daily NER am 05.02.2020 einen Dip hat, können Sie auf das Datum klicken, und andere Diagramme werden auf dieses bestimmte Datum vergrößert.

![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report5.png)

Aus dem NER Good Percentage Hourly Trend können Sie feststellen, dass der Dip um 21:00 Uhr erfolgt. Klicken Sie dann erneut, um auf Stunde 21 zu zoomen, und überprüfen Sie die Details des ausgeführten Anrufs, um zu sehen, wie viele Anrufe in dieser Stunde fehlgeschlagen sind und was die Gründe für das Anrufende sind. Sie können mit Selbstproblemen beginnen, die bei SBC-Problemen auftreten, oder Sie können das Problem an service desk melden, wenn das Problem nicht mit SBC zusammenhängt.

## <a name="network-parameters"></a>Netzwerkparameter

Alle Netzwerkparameter werden von der Direct Routing-Schnittstelle zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden [Sie unter "Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)", und sehen Sie sich die von Customer Edge zu Microsoft Edge empfohlenen Werte an.

  - **Jitter** – Ist das Millisekundenmaß der Variation der Verzögerungszeit für die Netzwerkverteilung, die zwischen zwei Endpunkten mit RTCP (The RTP Control Protocol) berechnet wird.

  - **Paketverlust** – Ist ein Maß für das Paket, das nicht eintreffen konnte; es wird zwischen zwei Endpunkten berechnet.

  - **Latenz** ( auch als Roundtripzeit bezeichnet) ist die Dauer, die für das Senden eines Signals benötigt wird, sowie die Dauer, die für den Empfang der Bestätigung dieses Signals benötigt wird. Diese Zeitverzögerung besteht aus den Verteilungszeiten zwischen den beiden Punkten eines Signals.

> ![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report6.png)

Zum Beispiel: 

Wenn in einem der vier Diagramme (Latenz, Jitter, Paketverlustrate, Nachwahlverzögerung) für ein bestimmtes Datum eine Spitze angezeigt wird, z. B. Latenz am 14.02.2020, klicken Sie auf den Datumspunkt. Und das Stundentrenddiagramm unten wird aktualisiert, um die Stundenzahl anzuzeigen. Sie können die SBCs überprüfen oder ein Ticket beim MS Service Desk erhöhen.

![Screenshot: PSTN-CQD-Bericht.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams](CQD-PSTN-report.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
