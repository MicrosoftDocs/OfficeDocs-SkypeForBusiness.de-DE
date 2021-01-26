---
title: Anrufsteuerungsbericht in Skype for Business Server
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
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Zusammenfassung: Erfahren Sie mehr über die Anrufsteuerungsberichte, die in Skype for Business Server verwendet werden.'
ms.openlocfilehash: ce7f8e622ece066d58cbc2c23a6423e19b084622
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826525"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Anrufsteuerungsbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Anrufsteuerungsberichte, die in Skype for Business Server verwendet werden.
  
Der Bericht über Anrufsteuerung bietet Informationen über Peer-zu-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die von der Anrufsteuerung implementiert werden. Die Anrufsteuerung bietet Administratoren die Möglichkeit, Kommunikationssitzungen basierend auf Bandbreiteneinschränkungen zu erlauben (oder nicht zu erlauben). Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken. Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.
  
## <a name="accessing-the-call-admission-control-report"></a>Öffnen des Berichts über Anrufsteuerung

Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite Monitoring Server-Berichte zu. Von diesem Bericht aus können Sie einen Drilldown zu folgenden weiteren Berichten durchführen:
  
- Konferenzdetailbericht: Klicken Sie auf die Metrik "Details" einer Konferenzsitzung, um auf diesen Bericht zu zugreifen. 
    
- Detailbericht über Peer-zu-Peer-Sitzungen: Klicken Sie auf die Metrik "Details" für eine Peer-zu-Peer-Sitzung, um auf diesen Bericht zu zugreifen.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Optimales Nutzen des Berichts über Anrufsteuerung

Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste Anrufkategorie den Eintrag Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:
  
Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.
  
Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.
  
**Anrufsteuerungsbericht – Filter**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/17/12015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/13/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf **[Alle]** klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.<br/> |
|**Aktivitätstyp** <br/> | Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/> |
|**Anrufkategorie** <br/> | Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Anruf durch Anrufsteuerung abgelehnt <br/>  Anrufe durch Anrufsteuerung über PSTN umgeleitet <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für Peer-zu-Peer-Sitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.  <br/> |
|**Von Benutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**To user** (An Benutzer) <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
|**Modalitäten** <br/> |Ja  <br/> |Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.  <br/> |
|**Zeitpunkt der Einladung** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.  <br/> |
|**Antwortzeit** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.  <br/> |
|**End time** (Endzeit) <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.  <br/> |
|**Diagnose-ID** <br/> |Ja  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Headers sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.
  
**Metriken für Konferenzsitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenz-URI** <br/> |Ja  <br/> |Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.  <br/> |
|**Organisator** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**Pool** <br/> |Ja  <br/> |In der Konferenz verwendeter Edgeserver.  <br/> |
|**Beginn** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/> |
|**End time** (Endzeit) <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Metriken für einzelne Konferenzteilnehmer

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.
  
**Metriken für einzelne Konferenzteilnehmer**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rolle** <br/> |Nein  <br/> |Rolle (z. B. Referent) des Konferenzteilnehmers.  <br/> |
|**Teilnehmer** <br/> |Nein  <br/> |SIP-Adresse des Konferenzteilnehmers.  <br/> |
|**Konnektivität** <br/> |Nein  <br/> |Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.  <br/> |
|**Modalität** <br/> |Nein  <br/> |Konferenztyp (z. B. A/V-Konferenzen).  <br/> |
|**Zeitpunkt des Beitritts** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.  <br/> |
|**Zeitpunkt der Beendigung** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |
   

