---
title: Zusammenfassender Bericht über Medienqualität in Skype for Business Server
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
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Zusammenfassung: Erfahren Sie mehr über den Zusammenfassenden Bericht über Medienqualität in Skype for Business Server.'
ms.openlocfilehash: 7ee64f9654e2f21a45c173c4a51ed5e40131b874
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838617"
---
# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Zusammenfassender Bericht über Medienqualität in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Zusammenfassenden Bericht über Medienqualität in Skype for Business Server.
  
Der "Zusammenfassende Bericht über Medienqualität" ist möglicherweise die beste Option zum Analysieren der Anrufqualität in Ihrer Organisation: In diesem Bericht werden detailliert die QoE-Anrufmetriken (Quality of Experience, QoE) in den folgenden Kategorien aufgeführt:
  
- UC-Peer-zu-Peer-Anrufe (z. B. ein Skype for Business zum Skype for Business Anruf)
    
- UC-Konferenzsitzungen
    
- PSTN-Konferenzsitzungen
    
- PSTN-Anrufe: Medienumgehung
    
- PSTN-Anrufe (keine Umgehung): UC-Abschnitt
    
- PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt
    
- Andere Anruftypen
    
Beim ersten Öffnen des Berichts wird eine Zusammenfassung zu den einzelnen Kategorien angezeigt. Ohne den Bericht verlassen zu müssen, können Sie jede Kategorie erweitern, um Unterkategorien wie Anrufe von Office Communicator 2007 R2 bis Skype for Business anzuzeigen. Diese Unterkategorien können Sie anschließend erweitern, um Details zu jedem in diesen Unterkategorien getätigten Anruf anzuzeigen.
  
Im zusammenfassenden Bericht über Medienqualität Skype for Business Server werden die Daten in drei Anruftypen unterteilt: Audioanrufe, Videoanrufe und Anwendungsfreigabeanrufe. Für jeden Anruftyp gibt es im Bericht einen eigenen Bereich und eigenen benutzerdefinierten Satz von Anrufmetriken.
  
Im "Zusammenfassenden Bericht über Medienqualität" können Sie Filter anwenden, mit denen Sie die Anrufqualität zwischen verkabelten und drahtlosen Anrufen, internen und externen Anrufen sowie VPN- und Nicht-VPN-Anrufen vergleichen können.
  
## <a name="accessing-the-media-quality-summary-report"></a>Zugreifen auf den "Zusammenfassenden Bericht über Medienqualität"

Auf den "Zusammenfassenden Bericht über Medienqualität" kann auf der Startseite "Überwachungsberichte" zugegriffen werden. Sie können einen Drilldown zum [Anruflistenbericht in Skype for Business Server](call-list-report-0.md) ausführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anrufvolumen
    
- Prozentsatz der Anrufe schlechter Qualität
    
Auf den "Zusammenfassenden Bericht über Medienqualität" können Sie auch zugreifen, indem Sie auf eine beliebige der folgenden Audioanrufmetriken klicken:
  
- Roundtrip (ms)
    
- Beeinträchtigung (MOS)
    
- Paketverlust
    
- Jitter (ms)
    
- Ausblendungsverhältnis der Reparatur
    
- Streckungsverhältnis der Reparatur
    
- Komprimierungsverhältnis der Reparatur
    
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Bespielsweise können Sie im zusammenfassenden Bericht über Medienqualität die zurückgegebenen Daten nach Zugriffstyp (d. h. interner oder externer Zugriff) oder nach Netzwerkverbindung (Kabel- oder Funkverbindung) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über Medienqualität verwenden können.
  
**Filter im Zusammenfassenden Bericht über Medienqualität**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Wired <br/>  Wireless <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Zusammenfassenden Bericht über Medienqualität angegeben werden.
  
**Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Audioanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-zu-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anrufvolumen** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anrufvolumen (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anrufvolumen (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anrufvolumen (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Roundtrip (ms)** <br/> |Nein  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Nein  <br/> |Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In Skype for Business Server prognostizieren verschiedene Algorithmen, wie Benutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Paketverlust** <br/> |Nein  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   
**Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Videoanrufe**

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
|**Verlust ausgehender Pakete** <br/> |Nein  <br/> |RTP-Paketverluste (Real-Time Transport Protocol) bei ausgehenden Paketen. (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Prozentzahl der eingefrorenen Frames** <br/> |Nein  <br/> |Prozentsatz der "fixierten" Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.  <br/> |
|**Durchschnittliche ausgehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.  <br/> |
|**Durchschnittliche eingehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.  <br/> |
|**Niedrige eingehende Framerate %** <br/> |Nein  <br/> |Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.  <br/> |
|**Clientintegrität %** <br/> ||Zeigt die relative Integrität des Clientgeräts während des Anrufs an.  <br/> |
   
**Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Anwendungsfreigabeanrufe**

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
|**Durchschnittliche Latenz der RDP-Kachelverarbeitung** <br/> |Nein  <br/> |Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung. Ein hoher Durchschnitt spiegelt eine längere Verzögerung bei der Anzeige wider und schließt die Netzwerklatenz ein. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten.  <br/> |
|**Insgesamt schlechte Kacheln %** <br/> |Nein  <br/> |Gesamtprozentsatz schlechter RDP-Kacheln.  <br/> |
   

