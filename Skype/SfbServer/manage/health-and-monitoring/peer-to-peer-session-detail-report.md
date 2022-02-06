---
title: Detailbericht über Peer-to-Peer-Sitzungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Zusammenfassung: Erfahren Sie mehr über den Detailbericht über Peer-to-Peer-Sitzungen in Skype for Business Server.'
---

# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Detailbericht über Peer-to-Peer-Sitzungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Detailbericht über Peer-to-Peer-Sitzungen in Skype for Business Server.
  
Der Detailbericht über Peer-zu-Peer-Sitzungen gibt detaillierte Informationen über eine Peer-zu-Peer-Sitzung zurück. Wenn Sie beispielsweise eine Sofortnachrichtensitzung auswählen, gibt der Bericht Ihnen die Anzahl an Nachrichten an, die jeweils von den beiden an der Sitzung beteiligten Benutzern gesendet wurden.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Zugriff auf den Detailbericht über Peer-zu-Peer-Sitzungen

Sie können über die folgenden Berichte (die alle über die Startseite für Überwachungsberichte aufgerufen werden können) auf den  Detailbericht über Peer-zu-Peer-Sitzungen zugreifen:
  
- Inventurbericht über IP-Telefone
    
- Bericht über Benutzeraktivität
    
- Bericht über Anrufsteuerung
    
- Fehlerlistenbericht 
    
Über den Detailbericht über Peer-to-Peer-Sitzungen können Sie [auf den Diagnosebericht in Skype for Business Server](diagnostic-report.md) zugreifen, indem Sie auf die Metrik "Diagnosebericht (Details)" klicken. Sie können zudem auf den Bericht über häufigste Fehler zugreifen, indem Sie auf eine der folgenden beiden Metriken klicken:
  
- Antwort
    
- Diagnose-ID
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Optimale Verwendung des Detailberichts über Peer-zu-Peer-Sitzungen

Der Detailbericht über Peer-zu-Peer-Sitzungen enthält zahlreiche Metriken, mit denen die Systemadministratoren möglicherweise zum Teil nicht vertraut sind. Häufig können Sie jedoch ein Tooltip mit einer kurzen Beschreibung der Metrik anzeigen, indem Sie den Mauszeiger über die Bezeichnung der jeweiligen Metrik bewegen.
  
Beachten Sie, dass die tatsächlichen Metriken, die in einem bestimmten Bericht angezeigt werden, von der ausgewählten Peer-zu-Peer-Sitzung abhängen. So wird für eine Audio-/Videositzung ein anderer Satz an Metriken ausgegeben als für eine Sofortnachrichtensitzung.
  
Sie können den Mauszeiger auch über die Antwortcode- und Diagnose-ID-Metriken bewegen, um eine Beschreibung der folgenden Werte anzuzeigen:
  
## <a name="filters"></a>Filter

Keine. Der Detailbericht über Peer-zu-Peer-Sitzungen kann nicht gefiltert werden.
  
## <a name="session-information-metrics"></a>Sitzungsinformationen – Metriken

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen angegeben werden.
  
**Sitzungsinformationen – Metriken**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Pool-FQDN** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers in der Sitzung.  <br/> |
|**Zeitpunkt der Einladung** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzungseinladung ursprünglich gesendet wurde.  <br/> |
|**Antwortzeit** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.  <br/> |
|**Von Benutzer** <br/> |SIP-Adresse des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Von Benutzer-Agent** <br/> |Die vom Endpunkt des Benutzers verwendete Software, der die Sitzung initiiert hat.  <br/> |
|**Von Benutzer intern** <br/> |Gibt an, ob der Benutzer, der die Sitzung initiiert hat, am internen Netzwerk angemeldet war.  <br/> |
|**Von Benutzer mit Telefonapparat** <br/> |Gibt an, ob der Endpunkt des Benutzers, der die Sitzung initiiert hat, mit seinem Desktoptelefon integriert ist.  <br/> |
|**Sitzungspriorität** <br/> |Die der Sitzung zugewiesene Priorität. Gültige Prioritäten umfassen "Unbekannt", "Nicht dringend", "Normal", "Dringend" und "Notfall".  <br/> |
|**Antwortcode** <br/> |Bei fehlgeschlagener Sitzung gesendeter SIP-Antwortcode.  <br/> |
|**Front-End** <br/> |Name des in der Konferenz verwendeten Front-End-Servers.  <br/> |
|**Zeitpunkt der Erfassung** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzungsinformationen erfasst wurden.  <br/> |
|**Endzeit** <br/> |Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.  <br/> |
|**An Benutzer** <br/> |SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
|**To user agent** (An Benutzer-Agent) <br/> |Die vom Endpunkt des Benutzers verwendete Software, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
|**An Benutzer intern** <br/> |Gibt an, ob der Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde, am internen Netzwerk angemeldet war.  <br/> |
|**An Benutzer mit Telefonapparat** <br/> |Gibt an, ob der Endpunkt des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde, mit seinem Desktoptelefon integriert ist.  <br/> |
|**Wiederholungsversuch der Sitzung** <br/> |Gibt an, ob die Sitzung ein Wiederholungsversuch einer zuvor fehlgeschlagenen Sitzung ist.  <br/> |
|**Diagnose-ID** <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Halten Sie den Mauszeiger über die ID-Nummer, um zusätzliche Information zu dieser ID anzuzeigen.  <br/> |
   
## <a name="metrics-for-modalities"></a>Metriken für Modalitäten

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeder Sitzungsmodalität angegeben werden.
  
**Metriken für Modalitäten**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Modalitäten** <br/> |Nein  <br/> |In der Sitzung verwendete Modalitäten, z. B. Instant Messaging (IM), Audio oder Dateiübertragung.  <br/> |
|**Nachrichten "Von Benutzer"** <br/> |Nein  <br/> |Anzahl der gesendeten Nachrichten des Benutzers, der die Sitzung initiiert hat.  <br/> |
|**Nachrichten "An Benutzer"** <br/> |Nein  <br/> |Anzahl der gesendeten Nachrichten des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Metriken für Diagnoseberichte

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeden Diagnosebericht angegeben werden.
  
**Metriken für Diagnoseberichte**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Klicken Sie auf dieses Element, um den Diagnosebericht für die Sitzung anzuzeigen.  <br/> |
|**Berichtszeit** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.  <br/> |
|**Anforderung** <br/> |Nein  <br/> |SIP-Anforderungstyp, z. B. INVITE oder BYE.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.  <br/> |
|**Inhaltstyp** <br/> |Nein  <br/> |In der Konferenz verwendeter Medieninhaltstyp. Ein gängiger Inhaltstyp ist beispielsweise "Application/sdp". SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen des Multimediasitzungsaufbaus verwendet wird.  <br/> |
|**Berichtet von** <br/> |Nein  <br/> |Computer (d. h. Client oder Server), der das Problem berichtet hat.  <br/> |
   

