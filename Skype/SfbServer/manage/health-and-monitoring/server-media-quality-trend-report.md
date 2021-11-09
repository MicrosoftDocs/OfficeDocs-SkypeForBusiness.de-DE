---
title: Trendbericht über Medienqualität des Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Zusammenfassung: Erfahren Sie mehr über den Trendbericht zur Medienqualität des Servers in Skype for Business Server.'
ms.openlocfilehash: 03091deedf502c4a6d9d65dc5e9f14532a9147ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851018"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Trendbericht über Medienqualität des Servers in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Trendbericht zur Medienqualität des Servers in Skype for Business Server.
  
Der Trendbericht über Medienqualität des Servers bietet Ihnen die Möglichkeit, bis zu fünf Server mit QoE-Metriken wie Anrufvolumen, Prozentsatz schlechter Anrufe, Paketverlust und Jitter grafisch zu vergleichen. Dies erleichtert die Identifizierung von Servern mit schlechter Leistung, die Identifizierung von Servern, die nicht ausgelastet sind, oder die Identifizierung von Servern, die überlastet sind.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Zugreifen auf den Trendbericht über Medienqualität des Servers

Auf den Trendbericht über Medienqualität des Servers kann über einen der folgenden Berichte zugegriffen werden:
  
- [Bericht über Serverleistung in Skype for Business Server](server-performance.md) (durch Klicken auf die Trendmetrik)
    
- [Anrufdetailbericht in Skype for Business Server](call-detail-report.md) (durch Klicken auf die A/V-Edgeservermetrik. Wenn der Anrufer oder Angerufene ein Server ist, können Sie auch den Trendbericht über Medienqualität des Servers erreichen, indem Sie auf den Endpunktnamen klicken.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Optimale Nutzung des Trendberichts zur Medienqualität des Servers

Wenn Sie im [Serverleistungsbericht in Skype for Business Server](server-performance.md) für einen bestimmten Server auf die Trendmetrik klicken, wird der Trendbericht über Medienqualität des Servers geöffnet. Es wird jedoch nur eine leere Instanz dieses Berichts angezeigt. Der Server, den Sie im Serverleistungsbericht ausgewählt haben, wird nicht auf dem Bildschirm angezeigt. Stattdessen müssen Sie diesen Server aus der Dropdownliste "Server" auswählen. Beachten Sie auch, dass das Dropdownmenü "Server" die Option "Alle auswählen" enthält. Diese Option funktioniert nicht, wenn Sie mehr als 5 Server haben. Der Trendbericht über Medienqualität des Servers kann nur Daten für maximal 5 Server gleichzeitig anzeigen.
  
In den Diagrammen, die im Trendbericht über Medienqualität des Servers angezeigt werden, sind die Punkte mit der Bezeichnung "Anruflautstärke" und "Prozentsatz der Anrufe schlechter Qualität" Hotlinks. Durch Klicken auf einen Punkt im Diagramm wird eine Instanz des [Anruflistenberichts in Skype for Business Server](call-list-report-0.md) geöffnet, in der die Gesamtzahl der Anrufe (oder Anrufe schlechter Qualität) für den angegebenen Zeitraum angezeigt wird.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Trendbericht über Medienqualität des Servers verwenden können.
  
**Filter im Trendbericht über Medienqualität des Servers**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Intervall "Täglich" mit dem Startdatum 07.08.2015 und dem Enddatum 28.09.2015 auswählen, werden daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. a. Daten insgesamt 31 Tage). <br/> |
|**Servertyp** <br/> | Typ des Servers, der an dem Anruf beteiligt ist. Gültige Werte sind: <br/>  Vermittlungsserver <br/>  A/V-Konferenzserver <br/>  A/V-Edgeserver <br/>  Gateway (Vermittlungsserver) <br/>  Gateway (Umgehung des Vermittlungsservers) <br/>  AS-Konferenzserver <br/> |
|**Server** <br/> |Name des servers, der an der Sitzung beteiligt ist; Diese Dropdownliste wird basierend auf dem Wert des Servertypfilters automatisch ausgefüllt. Sie können beim Kompilieren eines Berichts bis zu 5 verschiedene Server auswählen.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Teilnehmer am internen oder am externen Netzwerk angemeldet war. Gültige Werte sind: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**Netzwerktyp** <br/> | Gibt den Netzwerktyp an, mit dem der Teilnehmer verbunden war. Gültige Werte sind: <br/>  [Alle] <br/>  Wired <br/>  Wireless <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Teilnehmer während der Sitzung eine VPN-Verbindung (Virtual Private Network) verwendet hat. Gültige Werte sind: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Trendbericht über Medienqualität des Servers bereitgestellt werden.
  
**Metriken des Trendberichts über Medienqualität des Servers**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Nein  <br/> |Durchschnittliche Mos-Beeinträchtigung (Mittlere Optionsbewertung) während eines Anrufs. Beeinträchtigungswerte können zwischen einem Niedrigen von 0,0 und einem Hoch von 5,0 liegen. Ein Wert von 0,5 oder weniger stellt eine akzeptable Beeinträchtigung dar. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Skype for Business Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Roundtrip (ms)** <br/> |Nein  <br/> |Durchschnittliche Zeit (in Millisekunden), die ein Real-Time Transportprotokollpaket benötigt, um zu einem Endpunkt und dann zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Paketverlust** <br/> |Nein  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   

