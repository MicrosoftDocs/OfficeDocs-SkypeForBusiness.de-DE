---
title: Trend Bericht zur Server Medienqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Zusammenfassung: erfahren Sie mehr über den Trend Bericht zur Server Medienqualität in Skype for Business Server.'
ms.openlocfilehash: 0ed819c40088c03ca1882ed035b416bf1427e840
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279830"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Trend Bericht zur Server Medienqualität in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Trend Bericht zur Server Medienqualität in Skype for Business Server.
  
Mit dem „Trendbericht über Medienqualität des Servers“ haben Sie die Möglichkeit, bis zu fünf Server anhand von Quality of Experience (QoE)-Metriken, wie beispielsweise Anrufvolumen, Prozentsatz der Anrufe schlechter Qualität, Paketverlust und Jitter grafisch zu vergleichen. So ist es einfacher, die leistungsschwachen, nicht voll ausgelasteten oder die überbeanspruchten Server zu identifizieren.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Zugreifen auf den „Trendbericht über Medienqualität des Servers“

Auf den „Trendbericht über Medienqualität des Servers“ kann über einen der folgenden Berichte zugegriffen werden:
  
- [Bericht zur Server Leistung in Skype for Business Server](server-performance.md) (durch Klicken auf die Trend Metrik)
    
- [Anruf Detail Bericht in Skype for Business Server](call-detail-report.md) (durch Klicken auf die A/V-Edgeserver-Metrik. Wenn es sich bei dem Anrufer oder angerufenen um einen Server handelt, können Sie auch den Bericht "Server Quality Media Trend" erreichen, indem Sie auf den Endpunktnamen klicken.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Optimale Nutzung des „Trendberichts über Medienqualität des Servers“

Wenn Sie im [Berichtserver Leistung in Skype for Business Server](server-performance.md) für einen bestimmten Server auf die Trend Metrik klicken, wird der Trendbericht "Server Medienqualität" geöffnet. Es wird jedoch nur eine leere Instanz dieses Berichts angezeigt. der auf dem Serverleistungsbericht ausgewählte Server wird nicht auf dem Bildschirm angezeigt. Stattdessen müssen Sie diesen Server aus der Dropdownliste Server auswählen. Beachten Sie auch, dass die Dropdownliste "Server" eine Option "Alles auswählen" enthält. Diese Option funktioniert nicht, wenn Sie mehr als 5 Server haben; im Trend Bericht zur Server Medienqualität können nur Daten für maximal 5 Server gleichzeitig angezeigt werden.
  
In den Diagrammen, die mit dem Trend Bericht "Server Medienqualität" angezeigt werden, sind die Punkte mit der Bezeichnung Anrufvolumen und schlechter Anruf Prozentsatz Hotlinks; Wenn Sie auf einen Punkt im Diagramm klicken, wird eine Instanz des [Anruflisten Berichts in Skype for Business Server](call-list-report-0.md) geöffnet, in dem die Gesamt Anrufe (oder schlechte Anrufe) für den angegebenen Zeitraum angezeigt werden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im „Trendbericht über Medienqualität des Servers“ verwenden können.
  
**Filter im „Trendbericht über Medienqualität des Servers“**

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
  
**Metriken im „Trendbericht über Medienqualität des Servers“**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Nein  <br/> |Durchschnittliche Anzahl von MOS (Mean Option Score) Verschlechterung während eines Anrufs. Die Werte für die Verschlechterung können von einem Tiefstwert von 0,0 bis zu einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder einer kleineren stellt eine akzeptable Verschlechterung dar. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Skype for Business Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Nutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Roundtrip (ms)** <br/> |Nein  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein Real-Time Transport Protocol-Paket (RTP) benötigt, um zu einem Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Paketverlust** <br/> |Nein  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   

