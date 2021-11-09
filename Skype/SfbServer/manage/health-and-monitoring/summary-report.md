---
title: Zusammenfassender Anrufdiagnosebericht in Skype for Business Server
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Zusammenfassung: Erfahren Sie mehr über den zusammenfassenden Anrufdiagnosebericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: ef50ecde07fdd7354bd97c40bddfe4fb5e762d08
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827568"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Zusammenfassender Anrufdiagnosebericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den zusammenfassenden Anrufdiagnosebericht, der in Skype for Business Server verwendet wird.
  
Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:
  
- Sofortnachrichten
    
- Anwendungsfreigabe
    
- Dateiübertragung
    
- Audio
    
- Video
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Zugriff auf den zusammenfassenden Anrufdiagnosebericht

Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte. Über den zusammenfassenden Anrufdiagnosebericht können Sie auf den [Diagnosebericht über Peer-to-Peer-Aktivitäten in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie im Abschnitt "Peer-to-Peer-Sitzungszusammenfassung" des Berichts auf die Metrik "Fehlerrate" klicken. Sie können auch auf den Diagnosebericht über [Konferenzen in Skype for Business Server](conference-diagnostic-report.md) zugreifen, indem Sie auf eine der folgenden Konferenzmetriken klicken:
  
- Sitzungsfehlerrate insgesamt
    
- Fehlerrate für Konferenzzustandsobjekt
    
- MCU-Fehlerrate
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts

Der zusammenfassende Anrufdiagnosebericht enthält Diagramme, in denen fehlerraten für die verschiedenen in Skype for Business Server verwendeten Modalitäten verglichen werden. Die Spalten in diesen Diagrammen sind eigentlich Hotlinks. Wenn Sie beispielsweise auf die Chatspalte für Peer-to-Peer-Sitzungen klicken, führen Sie einen Drilldown zu einer Instanz des [Diagnoseberichts über Peer-to-Peer-Aktivitäten in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)durch, einem Bericht, der zusätzliche Details zu allen Chatsitzungen enthält, die im zusammenfassenden Anrufdiagnosebericht enthalten sind.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Anrufdiagnosebericht nach Kriterien wie dem Registrierungspool oder den in der Sitzung verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Anrufdiagnosebericht verwenden können.
  
**Filter im Zusammenfassenden Anrufdiagnosebericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-zu-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.
  
**Metriken für Peer-zu-Peer-Sitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Sitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die stattgefunden haben.  <br/> |
|**Fehlerrate** <br/> |Nein  <br/> |Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-zu-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-zu-Peer-Sitzungen enthält.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.
  
**Metriken für Konferenzsitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenzen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzen, die stattgefunden haben.  <br/> |
|**Konferenzsitzungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der Konferenzsitzungen, die durchgeführt wurden.  <br/> |
|**Sitzungsfehlerrate insgesamt** <br/> |Nein  <br/> |Der Prozentsatz der Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.  <br/> |
|**Konferenzzustandsobjekt-Sitzungen** <br/> |Nein  <br/> |Die Anzahl der auf Konferenzzustandsobjekten basierenden Sitzungen, bei denen Fehler aufgetreten sind.  <br/> |
|**Fehlerrate für Konferenzzustandsobjekt** <br/> |Nein  <br/> |Der Prozentsatz der auf Konferenzzustandsobjekten basierenden Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.  <br/> |
|**MCU-Sitzungen** <br/> |Nein  <br/> |Die Gesamtzahl der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.  <br/> |
|**MCU-Fehlerrate** <br/> |Nein  <br/> |Der Prozentsatz der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.  <br/> |
   

