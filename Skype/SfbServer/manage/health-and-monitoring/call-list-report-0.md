---
title: Bericht zur Anrufliste in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Zusammenfassung: erfahren Sie mehr über den Anruflistenbericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: fcf7f0e5f34a48644c8bd3bad3f1f2267afeb63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289329"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Bericht zur Anrufliste in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Anruflistenbericht, der in Skype for Business Server verwendet wird.
  
Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt oder empfangen wurden. Beachten Sie, dass die tatsächlich im Bericht verzeichneten Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen. Wenn Sie beispielsweise den Bericht aus dem [gerätebericht in Skype for Business Server](device-report.md)öffnen, sehen Sie Metriken wie die folgenden Metriken, die auch im gerätebericht angezeigt werden:
  
- Mikrofon des Anrufers
    
- Lautsprecher des Anrufers
    
- Mikrofon des Angerufenen
    
- Lautsprecher des Angerufenen
    
- Anteil Sprachumschaltzeit 
    
Wenn Sie den Anruflistenbericht aber über den [Standortbericht in Skype for Business Server](location-report.md)öffnen, werden keine dieser Metriken angezeigt. Stattdessen werden Metriken wie die folgenden angezeigt:
  
- Roundtrip (ms)
    
- Beeinträchtigung (MOS)
    
- Paketverlust
    
- Jitter (ms)
    
Dies sind Metriken aus dem Standortbericht. Im Anruflistenbericht können Sie jedoch jederzeit auf die Metrikdetails klicken und zu allen Anrufen vollständige QoE-Informationen anzeigen.
  
## <a name="accessing-the-call-list-report"></a>Zugriff auf den Anruflistenbericht

Auf den Anruflistenbericht kann über alle folgenden Berichte zugegriffen werden:
  
- Der [Standortbericht in Skype for Business Server](location-report.md) (durch Klicken auf das Anrufvolumen oder die prozentuale Kennzahl für schlechten Anruf)
    
- Der [gerätebericht in Skype for Business Server](device-report.md) (durch Klicken auf die Lautstärke des Anrufs oder die prozentuale Kennzahl für schlechten Anruf)
    
- Der [Bericht zur Zusammenfassung der Medienqualität in Skype for Business Server](summary.md) (durch Klicken auf die Lautstärke des Anrufs oder die prozentuale Kennzahl für schlechte Anrufe)
    
- Der [Bericht "Server Leistung" in Skype for Business Server](server-performance.md) (durch Klicken auf das Anrufvolumen oder die prozentuale Kennzahl für schlechten Anruf)
    
Innerhalb des Anruflisten Berichts können Sie [in Skype for Business Server auf den Anruf Detailbericht](call-detail-report.md) zugreifen, indem Sie auf die Detail Metrik klicken.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Optimale Verwendung des Anruflistenberichts

Wenn Sie vergessen haben, wofür einige der Anruflistenberichtsmetriken stehen (z. B. der Anteil Sprachumschaltzeit), bewegen Sie den Mauszeiger über die Beschriftung der Metrik, damit eine QuickInfo mit einer kurzen Beschreibung der Metrik angezeigt wird.
  
## <a name="filters"></a>Filter

Keine. Sie können den Anruflistenbericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Anruflistenbericht enthaltenen Informationen für jeden Anruf aufgeführt.
  
**Anruflistenbericht-Metriken**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Beschreibung** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, werden zusätzliche Informationen über den Anruf angezeigt.  <br/> |
|**Anrufer** <br/> |Ja  <br/> |SIP-Adresse der Person, die den Anruf initiiert hat.  <br/> |
|**Callee** <br/> |Ja  <br/> |SIP-Adresse der Person, die angerufen wurde.  <br/> |
|**Startzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit des Endes des Anrufs.  <br/> |
|**Benutzer-Agent des Anrufers** <br/> |Ja  <br/> |Software, die vom Endpunkt der Person, die den Anruf initiiert hat, verwendet wird.  <br/> |
|**Benutzer-Agent des Angerufenen** <br/> |Ja  <br/> |Software, die vom Endpunkt der Person, die angerufen wurde, verwendet wird.  <br/> |
|**Roundtrip (ms)** <br/> |Ja  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Ja  <br/> |Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder weniger gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In Skype for Business Server wird in einer Reihe von Algorithmen prognostiziert, wie Nutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Paketverlust** <br/> |Ja  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter** <br/> |Ja  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
|**Verbindung** <br/> |Ja  <br/> | Typ einer Kommunikationsverbindung über Funk. In der Regel wird damit einer der folgenden Typen bezeichnet: <br/>  Vermittelt <br/>  Direkt <br/> |
   

