---
title: Anruflistenbericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Zusammenfassung: Erfahren Sie mehr über den Anruflistenbericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: 8deb14cc8d2b8ff4b47701502de414d7460a81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817075"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Anruflistenbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Anruflistenbericht, der in Skype for Business Server verwendet wird.
  
Der Anruflistenbericht bietet QoE (Quality of Experience)-Metriken für einzelne Anrufe, die in Ihrer Organisation vorgenommen und empfangen werden. Beachten Sie, dass die tatsächlich gemeldeten Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen. Wenn Sie beispielsweise den Bericht aus dem Gerätebericht [in Skype for Business Server](device-report.md)öffnen, werden Metriken wie die folgenden angezeigt, die auch im Gerätebericht gemeldet werden:
  
- Mikrofon des Anrufers
    
- Anruferlautsprecher
    
- Mikrofon des Ansprechers
    
- Lautsprecher des Ansprechers
    
- Verhältnis der Sprachumschaltzeit 
    
Wenn Sie jedoch den Anruflistenbericht aus dem Standortbericht [in Skype for Business Server](location-report.md)öffnen, wird keine dieser Metriken angezeigt. stattdessen werden Metriken wie die folgenden angezeigt:
  
- Roundtrip (ms)
    
- Beeinträchtigung (MOS)
    
- Paketverlust
    
- Jitter (ms)
    
Dies sind die Metriken, die im Standortbericht gemeldet werden. Im Anruflistenbericht können Sie jedoch immer auf die Metrik "Details" klicken, um vollständige QoE-Informationen für jeden Anruf zur Verfügung zu stellen.
  
## <a name="accessing-the-call-list-report"></a>Zugreifen auf den Anruflistenbericht

Auf den Anruflistenbericht kann über einen der folgenden Berichte zugegriffen werden:
  
- Der [Standortbericht in Skype for Business Server](location-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
- Der [Gerätebericht in Skype for Business Server](device-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
- The [Media Quality Summary Report in Skype for Business Server](summary.md) (by clicking the Call volume or Poor call percentage metric)
    
- Der [Bericht über Serverleistung in Skype for Business Server](server-performance.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz der Anrufe schlechter Qualität")
    
Über den Anruflistenbericht können Sie auf den Anrufdetailbericht [in Skype for Business Server](call-detail-report.md) zugreifen, indem Sie auf die Metrik "Details" klicken.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Optimale Nutzung des Anruflistenberichts

Wenn Sie sich nicht merken können, welche Metriken im Anruflistenbericht (z. B. die Sprachumschaltzeit des Verhältnisses) tatsächlich gemessen werden, halten Sie die Maus über die Metrikbeschriftung. Anschließend wird ein QuickInfo mit einer kurzen Beschreibung der Metrik angezeigt.
  
## <a name="filters"></a>Filter

Keine. Sie können den Anruflistenbericht nicht filtern.
  
## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Anruflistenbericht für jeden Anruf bereitgestellt werden.
  
**Metriken im Anruflistenbericht**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Details** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, werden im Bericht zusätzliche Informationen zum Anruf angezeigt.  <br/> |
|**Caller** <br/> |Ja  <br/> |Die SIP-Adresse der Person, die den Anruf initiiert hat.  <br/> |
|**Ankrufer** <br/> |Ja  <br/> |Die SIP-Adresse der Person, die angerufen wurde.  <br/> |
|**Start time** <br/> |Ja  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**Endzeit** <br/> |Ja  <br/> |Datum und Uhrzeit des Endes des Anrufs.  <br/> |
|**Benutzer-Agent des Anrufers** <br/> |Ja  <br/> |Software, die vom Endpunkt der Person verwendet wird, die den Anruf initiiert hat.  <br/> |
|**Benutzer-Agent des Angerufenen** <br/> |Ja  <br/> |Software, die vom Endpunkt der Person verwendet wird, die angerufen wurde.  <br/> |
|**Roundtrip (ms)** <br/> |Ja  <br/> |Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**Beeinträchtigung (MOS)** <br/> |Ja  <br/> |Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In Skype for Business Server prognostizieren einige Algorithmen, wie Benutzer einen Anruf bewertet hätten.  <br/> Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Paketverlust** <br/> |Ja  <br/> |Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Jitter** <br/> |Ja  <br/> |Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Ausblendungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**Streckungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.  <br/> |
|**Komprimierungsverhältnis der Reparatur** <br/> |Ja  <br/> |Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.  <br/> |
|**Konnektivität** <br/> |Ja  <br/> | Typ der Funkkommunikationsverbindung. In der Regel ist dies eine der folgenden: <br/>  Relay <br/>  Direkt <br/> |
   

