---
title: Zusammenfassungsbericht für Medienqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Zusammenfassung: Informationen zum Zusammenfassungsbericht für Medienqualität in Skype for Business Server.'
ms.openlocfilehash: 49c4aba8e5eb69c50282f4c9a1c77027f1a0210d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279753"
---
# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Zusammenfassungsbericht für Medienqualität in Skype for Business Server
 
**Zusammenfassung:** Informationen zum Zusammenfassungsbericht für Medienqualität in Skype for Business Server.
  
Der „Zusammenfassende Bericht über Medienqualität“ ist möglicherweise die beste Option zum Analysieren der Anrufqualität in Ihrer Organisation: In diesem Bericht werden detailliert die QoE-Anrufmetriken (Quality of Experience, QoE) in den folgenden Kategorien aufgeführt:
  
- UC-Peer-to-Peer-Anrufe (wie Skype for Business für Skype for Business-Anruf)
    
- UC-Konferenzsitzungen
    
- PSTN-Konferenzsitzungen
    
- PSTN-Anrufe: Medienumgehung
    
- PSTN-Anrufe (keine Umgehung): UC-Abschnitt
    
- PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt
    
- Andere Anruftypen
    
Beim ersten Öffnen des Berichts wird eine Zusammenfassung zu den einzelnen Kategorien angezeigt. Ohne den Bericht zu verlassen, können Sie jede Kategorie erweitern, um Unterkategorien wie Anrufe von Office Communicator 2007 R2 zu Skype for Business zu sehen. Diese Unterkategorien können Sie anschließend erweitern, um Details zu jedem in diesen Unterkategorien getätigten Anruf anzuzeigen.
  
In Skype for Business Server wird der Zusammenfassungsbericht für Medienqualität die Daten in drei Anruftypen weiter unterteilt: Audioanrufe, Videoanrufe und Anwendungsfreigabe Anrufe. Für jeden Anruftyp gibt es im Bericht einen eigenen Bereich und eigenen benutzerdefinierten Satz von Anrufmetriken.
  
Im „Zusammenfassenden Bericht über Medienqualität“ können Sie Filter anwenden, mit denen Sie die Anrufqualität zwischen verkabelten und drahtlosen Anrufen, internen und externen Anrufen sowie VPN- und Nicht-VPN-Anrufen vergleichen können.
  
## <a name="accessing-the-media-quality-summary-report"></a>Zugreifen auf den „Zusammenfassenden Bericht über Medienqualität“

Auf den „Zusammenfassenden Bericht über Medienqualität“ kann auf der Startseite „Überwachungsberichte“ zugegriffen werden. Sie können einen Drilldown zum [Bericht Anrufliste in Skype for Business Server](call-list-report-0.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:
  
- Anruflautstärke
    
- Prozentsatz der Anrufe schlechter Qualität
    
Auf den „Zusammenfassenden Bericht über Medienqualität“ können Sie auch zugreifen, indem Sie auf eine beliebige der folgenden Audioanrufmetriken klicken:
  
- Roundtrip (ms)
    
- Beeinträchtigung (MOS)
    
- Paketverlust
    
- Jitter (ms)
    
- Ausblendungsverhältnis der Reparatur
    
- Streckungsverhältnis der Reparatur
    
- Komprimierungsverhältnis der Reparatur
    
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im zusammenfassenden Bericht über Medienqualität die zurückgegebenen Daten nach Zugriffstyp (d. h. interner oder externer Zugriff) oder nach Netzwerkverbindung (Kabel- oder Funkverbindung) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im „Zusammenfassenden Bericht über Medienqualität“ verwenden können.
  
**Filter im „Zusammenfassenden Bericht über Medienqualität“**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Zugriffstyp** <br/> | Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Intern <br/>  Extern <br/> |
|**Netzwerktyp** <br/> | Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Verkabelt <br/>  Funk <br/> |
|**VPN** <br/> | Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  VPN <br/>  Nicht-VPN <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Zusammenfassenden Bericht über Medienqualität angegeben werden.
  
**Metriken im „Zusammenfassenden Bericht über Medienqualität“: Zusammenfassung der Audioanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-to-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anruflautstärke (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anruflautstärke (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anruflautstärke (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Roundtrip (ms)** <br/> |Nein  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Nein  <br/> |Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder weniger gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In Skype for Business Server wird eine Reihe von Algorithmen Vorhersagen, wie Nutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Paketverlust** <br/> |Nein  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Nein  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
   
**Metriken im „Zusammenfassenden Bericht über Medienqualität“: Zusammenfassung der Videoanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-to-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anruflautstärke (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anruflautstärke (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anruflautstärke (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Durchschnittliche Bitrate (KBit/s)** <br/> |Nein  <br/> |Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).  <br/> |
|**Niedrige Bitrate %** <br/> |Nein  <br/> |Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.  <br/> |
|**Verlust ausgehender Pakete** <br/> |Nein  <br/> |RTP-Paketverluste (Real-Time Transport Protocol) bei ausgehenden Paketen. (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Eingefrorene Frames %** <br/> |Nein  <br/> |Prozentsatz der "fixierten" Frames In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.  <br/> |
|**Durchschnittliche ausgehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.  <br/> |
|**Durchschnittliche eingehende Framerate** <br/> |Nein  <br/> |Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.  <br/> |
|**Niedrige eingehende Framerate %** <br/> |Nein  <br/> |Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.  <br/> |
|**Clientintegrität %** <br/> ||Zeigt die relative Integrität des Clientgeräts während des Anrufs an.  <br/> |
   
**Metriken im „Zusammenfassenden Bericht über Medienqualität“: Zusammenfassung der Anwendungsfreigabeanrufe**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Anruftyp/Endpunkttyp** <br/> |Nein  <br/> | Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen: <br/>  UC-Peer-to-Peer-Anrufe <br/>  UC-Konferenzsitzungen <br/>  PSTN-Konferenzsitzungen <br/>  PSTN-Anrufe: Medienumgehung <br/>  PSTN-Anrufe (keine Umgehung): UC-Abschnitt <br/>  PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt <br/>  Andere Anruftypen <br/> |
|**Anruflautstärke** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe pro Anruftyp.  <br/> |
|**Prozentsatz der Anrufe schlechter Qualität** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).  <br/> |
|**Anruflautstärke (Funkanruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.  <br/> |
|**Anruflautstärke (VPN-Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.  <br/> |
|**Anruflautstärke (externer Anruf)** <br/> |Nein  <br/> |Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).  <br/> |
|**Jitter (ms)** <br/> |Nein  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Durchschnittliche relative unidirektionale Verzögerung** <br/> |Nein  <br/> |Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.  <br/> |
|**Durchschnittliche Latenz der RDP-Kachelverarbeitung** <br/> |Nein  <br/> |Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung. Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an und bezieht Netzwerklatenz mit ein. Ein überlasteter Konferenzserver weist gegebenenfalls höhere durchschnittliche Verzögerungen auf.  <br/> |
|**Ungültige Kacheln insgesamt %** <br/> |Nein  <br/> |Gesamtprozentsatz schlechter RDP-Kacheln.  <br/> |
   

