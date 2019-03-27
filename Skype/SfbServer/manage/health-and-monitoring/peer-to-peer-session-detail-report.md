---
title: Peer-zu-Peer-Sitzungsbericht in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Zusammenfassung: Informationen Sie zu den Detailbericht über Peer-zu-Peer-Sitzungen in Skype für Business Server.'
ms.openlocfilehash: 41d4b7d78c674afbc2136911913e88837a4f5095
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897240"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Peer-zu-Peer-Sitzungsbericht in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Detailbericht über Peer-zu-Peer-Sitzungen in Skype für Business Server.
  
Der Detailbericht über Peer-to-Peer-Sitzungen gibt detaillierte Informationen über eine Peer-to-Peer-Sitzung zurück. Wenn Sie beispielsweise eine Sofortnachrichtensitzung auswählen, gibt der Bericht Ihnen die Anzahl an Nachrichten an, die jeweils von den beiden an der Sitzung beteiligten Benutzern gesendet wurden.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Zugriff auf den Detailbericht über Peer-to-Peer-Sitzungen

Sie können über die folgenden Berichte (die alle über die Startseite für Überwachungsberichte aufgerufen werden können) auf den Detailbericht über Peer-to-Peer-Sitzungen zugreifen:
  
- Inventurbericht über IP-Telefone
    
- Bericht über Benutzeraktivität
    
- Bericht über Anrufsteuerung
    
- Fehlerlistenbericht 
    
Von innerhalb der Peer-zu-Peer-Sitzungsbericht möglich den [Diagnosebericht in Skype für Business Server](diagnostic-report.md) durch Klicken auf die Metrik Diagnosebericht (Details). Sie können zudem auf den Bericht über häufigste Fehler zugreifen, indem Sie auf eine der folgenden beiden Metriken klicken:
  
- Reaktion
    
- Diagnose-ID
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Optimale Verwendung des Detailberichts über Peer-to-Peer-Sitzungen

Der Detailbericht über Peer-to-Peer-Sitzungen enthält zahlreiche Metriken, mit denen die Systemadministratoren möglicherweise zum Teil nicht vertraut sind. Häufig können Sie jedoch ein Tooltip mit einer kurzen Beschreibung der Metrik anzeigen, indem Sie den Mauszeiger über die Bezeichnung der jeweiligen Metrik bewegen.
  
Beachten Sie, dass die tatsächlichen Metriken, die in einem bestimmten Bericht angezeigt werden, von der ausgewählten Peer-to-Peer-Sitzung abhängen. So wird für eine Audio-/Videositzung ein anderer Satz an Metriken ausgegeben als für eine Sofortnachrichtensitzung.
  
Sie können den Mauszeiger auch über die Antwortcode- und Diagnose-ID-Metriken bewegen, um eine Beschreibung der folgenden Werte anzuzeigen:
  
## <a name="filters"></a>Filter

Keine. Der Detailbericht über Peer-to-Peer-Sitzungen kann nicht gefiltert werden.
  
## <a name="session-information-metrics"></a>Sitzungsinformationen - Metriken

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen angegeben werden.
  
**Sitzungsinformationen - Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Pool-FQDN** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers in der Sitzung.  <br/> |
|**Einladungszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzungseinladung ursprünglich gesendet wurde.  <br/> |
|**Antwortzeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.  <br/> |
|**Absenderbenutzer** <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Von Benutzeragent** <br/> |Software, die vom Endpunkt des Benutzers, der die Sitzung initiiert hat, verwendet wird.  <br/> |
|**Interner Absenderbenutzer** <br/> |Gibt an, ob der Benutzer, der die Sitzung initiiert hat, am internen Netzwerk angemeldet war.  <br/> |
|**Absenderbenutzer mit Telefonapparat** <br/> |Gibt an, ob der Endpunkt des Benutzers, der die Sitzung initiiert hat, mit seinem Desktoptelefon integriert ist.  <br/> |
|**Sitzungspriorität** <br/> |Die der Sitzung zugewiesene Priorität. Gültige Prioritäten sind „Unbekannt“, „Nicht dringend“, „Normal“, „Dringend“ und „Notfall“.  <br/> |
|**Antwortcode** <br/> |SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.  <br/> |
|**Front-End** <br/> |Name des in der Konferenz verwendeten Front-End-Servers.  <br/> |
|**Erfassungszeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzungsinformationen erfasst wurden.  <br/> |
|**Endzeitpunkt** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.  <br/> |
|**An Benutzer** <br/> |SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.  <br/> |
|**Empfängerbenutzeragent** <br/> |Die vom Endpunkt des Benutzers verwendete Software, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
|**Interner Empfängerbenutzer** <br/> |Gibt an, ob der Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde, am internen Netzwerk angemeldet war.  <br/> |
|**Empfängerbenutzer mit Telefonapparat** <br/> |Gibt an, ob der Endpunkt des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde, mit seinem Desktoptelefon integriert ist.  <br/> |
|**Wiederholungsversuch der Sitzung** <br/> |Gibt an, ob die Sitzung ein Wiederholungsversuch einer zuvor fehlgeschlagenen Sitzung ist.  <br/> |
|**Diagnose-ID** <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Halten Sie den Mauszeiger über die ID-Nummer, um zusätzliche Information zu dieser ID anzuzeigen.  <br/> |
   
## <a name="metrics-for-modalities"></a>Metriken für Modalitäten

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen zu jeder Sitzungsmodalität angegeben werden.
  
**Metriken für Modalitäten**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Modalitäten** <br/> |Nein  <br/> |In der Sitzung verwendete Modalitäten, z. B. Chat, Audio oder Dateiübertragung.  <br/> |
|**Nachrichten von Absenderbenutzer** <br/> |Nein  <br/> |Anzahl der gesendeten Nachrichten des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Nachrichten an Empfängerbenutzer** <br/> |Nein  <br/> |Anzahl der gesendeten Nachrichten des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Metriken für Diagnoseberichte

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen zu jeden Diagnosebericht angegeben werden.
  
**Metriken für Diagnoseberichte**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Klicken Sie auf dieses Element, um den Diagnosebericht für die Sitzung anzuzeigen.  <br/> |
|**Berichtszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit der Aufzeichnung des Berichts.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |SIP-Anforderungstyp, z. B. INVITE oder BYE.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Inhaltstyp** <br/> |Nein  <br/> |In der Konferenz verwendeter Medieninhaltstyp. Ein gängiger Inhaltstyp ist beispielsweise „Application/sdp“. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen des Multimediasitzungsaufbaus verwendet wird.  <br/> |
|**Berichtet von** <br/> |Nein  <br/> |Computer (d. h. Client oder Server), der das Problem berichtet hat.  <br/> |
   

