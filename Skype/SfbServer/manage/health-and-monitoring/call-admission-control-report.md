---
title: Aufrufen des Berichts über Anrufsteuerung in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Zusammenfassung: Erfahren Sie mehr über die aufrufen Admission Control-Berichte in Skype für Business Server verwendet.'
ms.openlocfilehash: f6f68e74c584496de0256b0fad8e2deae7dcc253
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902696"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Aufrufen des Berichts über Anrufsteuerung in Skype für Business Server
 
**Zusammenfassung:** Lernen Sie die aufrufen Admission Control-Berichte in Skype für Business Server verwendet.
  
Der Bericht über Anrufsteuerung bietet Informationen über Peer-to-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die über die Anrufsteuerung eingeführt wurden. Die Anrufsteuerung bietet Administratoren eine Möglichkeit, Kommunikationssitzungen auf der Grundlage von Bandbreitenbeschränkungen zuzulassen (oder nicht zuzulassen). Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken. Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.
  
## <a name="accessing-the-call-admission-control-report"></a>Öffnen des Berichts über Anrufsteuerung

Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite für Überwachungsberichte zu. Vom Bericht über Anrufsteuerung aus können Sie einen Drilldown zu einem der folgenden Berichte durchführen:
  
- Konferenzdetailbericht – zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine konferenzsitzung. 
    
- Peer-zu-Peer-Sitzungsbericht - zum Öffnen dieses Berichts klicken Sie auf die Metrik Details für eine Peer-zu-Peer-Sitzung.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Optimales Nutzen des Berichts über Anrufsteuerung

Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste „Anrufkategorie“ den Eintrag „Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden“ aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:
  
Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.
  
Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.
  
**Anrufsteuerungsbericht - Filter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Aktivitätstyp** <br/> | Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/> |
|**Anrufkategorie** <br/> | Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Anruf durch Anrufsteuerung abgelehnt <br/>  Anrufe durch Anrufsteuerung über PSTN umgeleitet <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-to-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für Peer-to-Peer-Sitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.  <br/> |
|**Absenderbenutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**An Benutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
|**Modalitäten** <br/> |Ja  <br/> |Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.  <br/> |
|**Einladungszeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.  <br/> |
|**Antwortzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.  <br/> |
|**Diagnose-ID** <br/> |Ja  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für Konferenzsitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenz-URI** <br/> |Ja  <br/> |Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.  <br/> |
|**Organisator** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**Pool** <br/> |Ja  <br/> |In der Konferenz verwendeter Edgeserver.  <br/> |
|**Startzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Metriken für einzelne Konferenzteilnehmer

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.
  
**Metriken für einzelne Konferenzteilnehmer**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rolle** <br/> |Nein  <br/> |Rolle (z. B. Referent) des Konferenzteilnehmers.  <br/> |
|**Teilnehmer** <br/> |Nein  <br/> |SIP-Adresse des Konferenzteilnehmers.  <br/> |
|**Verbindung** <br/> |Nein  <br/> |Netzwerkverbindungen (in der Regel „From Internal“ oder „From External“) des Teilnehmers.  <br/> |
|**Modalität** <br/> |Nein  <br/> |Konferenztyp (z. B. A/V-Konferenzen).  <br/> |
|**Beitrittszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Beendigungszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   

