---
title: Trendbericht über Medienqualität des Servers in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Zusammenfassung: Erfahren Sie mehr über den Server Trendbericht über Medienqualität in Skype für Business Server 2015.'
ms.openlocfilehash: e257243eed1934cecc39f1feec26b3d83862e8c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server-2015"></a>Trendbericht über Medienqualität des Servers in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Server Trendbericht über Medienqualität in Skype für Business Server 2015.
  
Mit dem „Trendbericht über Medienqualität des Servers“ haben Sie die Möglichkeit, bis zu fünf Server anhand von Quality of Experience (QoE)-Metriken, wie beispielsweise Anrufvolumen, Prozentsatz der Anrufe schlechter Qualität, Paketverlust und Jitter grafisch zu vergleichen. So ist es einfacher, die leistungsschwachen, nicht voll ausgelasteten oder die überbeanspruchten Server zu identifizieren.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Zugreifen auf den „Trendbericht über Medienqualität des Servers“

Auf den „Trendbericht über Medienqualität des Servers“ kann über einen der folgenden Berichte zugegriffen werden:
  
- [Serverperformance Report in Skype für Business Server 2015](server-performance.md) (durch Klicken auf die Trend-Metriken)
    
- [Aufrufdetailbericht in Skype für Business Server 2015](call-detail-report.md) (durch Klicken auf den A / V-Edgeserver Metrik. Wenn der Anrufer oder angerufenen ein Server ist, können Sie auch die Qualität Trendbericht über Servers erreichen durch Klicken auf den Endpunktnamen.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Optimale Nutzung des „Trendberichts über Medienqualität des Servers“

Wenn Sie die Trend-Metriken im [Bericht über Serverleistung in Skype für Business Server 2015](server-performance.md) für einen bestimmten Server klicken, wird der Server Trendbericht über Medienqualität geöffnet. Sehen Sie jedoch nur eine leere Instanz dieses Berichts; Servers, den Sie auf dem Server Performance Report ausgewählt wird nicht auf dem Bildschirm angezeigt werden. Stattdessen müssen Sie diesem Server wählen Sie aus der Dropdownliste Server aus. Beachten Sie außerdem, dass die Dropdownliste Server aus eine Option alle auswählen enthält. Diese Option funktioniert nicht, wenn Sie mehr als 5 Server verfügen. der Server Trendbericht über Medienqualität können nur Daten für maximal 5 Servern zu einem Zeitpunkt angezeigt.
  
Für die Diagramme, die durch den Server Trendbericht über Medienqualität angezeigt die Punkte mit der Bezeichnung Volume aufrufen und Prozentsatz der Anrufe schlechter Hotlinks sind; durch Klicken auf einen Punkt im Diagramm wird eine Instanz des [Call List Report in Skype für Business Server 2015](call-list-report-0.md) , in dem Anrufe gesamt (und der Anrufe schlechter) für den angegebenen Zeitraum geöffnet.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im „Trendbericht über Medienqualität des Servers“ verwenden können.
  
**Server Media Quality Trend Berichtsfilter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.08.2015 und dem Enddatum 28.09.2015 ausgewählt haben, werden Daten für die Tage07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Servertyp** <br/> | Beim Anruf verwendeter Servertyp. Gültige Werte sind: <br/>  Vermittlungsserver <br/>  A/V-Konferenzserver <br/>  A/V-Edgeserver <br/>  Gateway (Vermittlungsserver) <br/>  Gateway (Umgehung des Vermittlungsservers) <br/>  AS-Konferenzserver <br/> |
|**Server** <br/> |Name des in der Sitzung verwendeten Servers. Diese Dropdownliste wird automatisch anhand des Werts des Servertypfilters aufgefüllt. Sie können bei der Erstellung eines Berichts bis zu 5 verschiedene Server auswählen.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Teilnehmer am internen oder am externen Netzwerk angemeldet wurde. Gültige Werte sind: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Teilnehmer verbunden wurde. Gültige Werte sind: <br/>  [Alle] <br/>  Verkabelt <br/>  Funk <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Teilnehmer während der Sitzung eine VPN-Verbindung (Virtual Private Network) verwendete. Gültige Werte sind: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im „Trendbericht über Medienqualität des Servers“ angegeben werden.
  
**Server Media Quality Trend Metriken im Bericht über**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Nein  <br/> |Durchschnittliche Länge der MOS (Mittelwert Option Score)-Beeinträchtigung während eines Anrufs auftraten. Beeinträchtigung Werte liegen zwischen niedrig 0,0 und hoher 5.0; ein Wert von 0,5 oder weniger stellt akzeptable Beeinträchtigung dar. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Skype für Business Server verwendet eine Reihe von Algorithmen vorhergesagt wie Benutzer einen Anruf bewertet haben würde.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Roundtrip (ms)** <br/> |Nein  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein Real-Time Transport Protocol-Paket (RTP) benötigt, um zu einem Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Paketverlust** <br/> |Nein  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   

