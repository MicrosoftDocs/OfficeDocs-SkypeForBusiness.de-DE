---
title: Bericht über Serverleistung in Skype for Business Server
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
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 'Zusammenfassung: Erfahren Sie mehr über den Serverleistungsbericht in Skype for Business Server.'
ms.openlocfilehash: 6e13a12452fbdbf650a7e307340269803a2301b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836337"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>Bericht über Serverleistung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über Serverleistung in Skype for Business Server.
  
Der Bericht über Serverleistung enthält eine Liste der Skype for Business Server Server, bei denen der Prozentsatz der Anrufe schlechter Qualität am höchsten war. Der Bericht führt die Server nach Servertyp auf und bietet separate Statistiken für folgende Typen:
  
- Vermittlungsserver
    
- A/V-Konferenzserver
    
- A/V-Edgeserver
    
- Gateway (Vermittlungsserver)
    
- Gateway (Vermittlungsserverumgehung)
    
- Video (einschließlich Videometriken für A/V-Konferenzserver und A/V-Edgeserver)
    
- Anwendungsfreigabe (einschließlich Anwendungsfreigabemetriken für A/V-Konferenzserver und A/V-Edgeserver)
    
Es ist wichtig zu beachten, dass die in diesem Bericht angezeigte Rangfolge relativ ist. Wenn Ihr Server mit der schlechtesten Leistung z. B. einen Anruf schlechter Qualität unter 1.000 Anrufen hatte, dann ist das ein sehr akzeptabler Prozentsatz von 0,1 %. Wenn dieser Server jedoch der Server mit der schlechtesten Leistung ist (d. h., alle anderen Server haben einen Prozentsatz an Anrufen schlechter Qualität unter 0,1 %), dann wird der Server weiterhin im Bericht über Serverleistung aufgeführt.
  
## <a name="accessing-the-server-performance-report"></a>Zugriff auf den Bericht über Serverleistung

Der Zugriff auf den Bericht über Serverleistung erfolgt auf der Startseite für Überwachungsberichte. Sie können einen Drilldown zum [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) ausführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anrufvolumen
    
- Prozentsatz der Anrufe schlechter Qualität
    
Außerdem können Sie den Trendbericht über Medienqualität des Servers anzeigen, indem Sie auf eine der folgenden Metriken klicken:
  
- Trend
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>Optimale Nutzung des Berichts zur Serverleistung

Der Bericht über Serverleistung bietet verschiedene Möglichkeit, die Daten zu filtern. Sie können z. B. nach Netzwerktyp filtern (Anrufe über eine Kabelverbindung im Vergleich zu Anrufen über eine kabellose Verbindung) und nach Zugriffstyp (Anrufe, die von innerhalb der Firewall getätigt wurden im Vergleich zu Anrufen von außerhalb der Firewall). Es ist sinnvoll, diese Filter bei der Auswertung des Berichts über Serverleistung zu nutzen. Beispiel: Angenommen, Sie haben einen Vermittlungsserver, der einen Prozentsatz an Anrufen schlechter Qualität von 3,24 % hat. Wenn Sie sich nur die Funkanrufe ansehen, dann hat derselbe Server einen Prozentsatz an Anrufen schlechter Qualität von fast 20 %. Dies bedeutet, dass der Server Probleme mit Funkanrufen hat, was teilweise dadurch verschleiert wurde, dass der Server keine Probleme mit Kabelanrufen hat.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Bericht über Serverleistung die zurückgegebenen Daten nach Kriterien wie etwa Servertyp oder Netzwerktyp (d. h. Kabel oder Funk) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Daten nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Serverleistung verwenden können.
  
**Filter im Bericht über Serverleistung**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Servertyp** <br/> |Gibt den Typ des Servers an, über dessen Leistung ein Bericht erstellt werden soll. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Vermittlungsserver A/V-Konferenzserver A/V-Edgeserver |
|**Top N** <br/> |Gibt die Anzahl der Server an (basierend auf dem Prozentsatz der Anrufe schlechter Qualität), die in den einzelnen Kategorien angezeigt werden sollen. Wenn Sie z. B. **5** auswählen, werden die fünf Server mit der schlechtesten Leistung angezeigt. Wählen Sie eine der folgenden Optionen aus:<br/> [Alle] 5 10 |
|**Zugriffstyp** <br/> |Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Intern extern |
|**Netzwerktyp** <br/> |Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] Kabelgebundene Drahtlosverbindung |
|**VPN** <br/> |Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:  <br/> [Alle] VPN, kein VPN |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Serverleistung angegeben werden.
  
**Metriken im Bericht über Serverleistung: Zusammenfassung der Audioanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Server** <br/> |Nein  <br/> |Name/IP-Adresse des Servers.  <br/> |
|**Anrufvolumen** <br/> |Nein  <br/> |Gesamtzahl der ausgeführten Anrufe.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Roundtrip (ms)** <br/> |Ja  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Ja  <br/> |Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In Skype for Business Server verwendet der Monitoring Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Paketverlust** <br/> |Ja  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Ja  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   
**Metriken im Bericht über Serverleistung: Zusammenfassung der Videoanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-zu-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anrufvolumen** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anrufvolumen (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anrufvolumen (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anrufvolumen (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Durchschnittliche Bitrate (KBit/s)** <br/> |Nein  <br/> |Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).  <br/> |
|**Niedrige Bitrate %** <br/> |Nein  <br/> |Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.  <br/> |
|**Verlust ausgehender Pakete** <br/> |Nein  <br/> |RTP-Paketverluste (Real-Time Transport Protocol; ein Protokoll für die Übertragung von Audio und Video über das Internet) für ausgehende Pakete. Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Eingefrorene Frames %** <br/> |Nein  <br/> |Prozentsatz der "fixierten" Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.  <br/> |
|**Durchschnittliche ausgehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.  <br/> |
|**Durchschnittliche eingehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.  <br/> |
|**Niedrige eingehende Framerate %** <br/> |Nein  <br/> |Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.  <br/> |
|**Clientintegrität %** <br/> ||Zeigt die relative Integrität des Clientgeräts während des Anrufs an.  <br/> |
   
**Metriken im Bericht über Serverleistung: Zusammenfassung der Anwendungsfreigabeanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-zu-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anrufvolumen** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anrufvolumen (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anrufvolumen (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anrufvolumen (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Durchschnitt relativ unidirektional** <br/> |Nein  <br/> |Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.  <br/> |
|**Durchschnittliche Latenz der RDP-Kachelverarbeitung** <br/> |Nein  <br/> |Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung. Diese Metrik deckt die Netzwerklatenz nicht ab. Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.  <br/> |
|**Insgesamt schlechte Kacheln %** <br/> |Nein  <br/> |Gesamtprozentsatz schlechter RDP-Kacheln.  <br/> |
   

