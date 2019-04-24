---
title: Konfigurieren von CUCM für die Interoperation mit Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Zusammenfassung: Konfigurieren Sie CUCM Skype für Business Server entwickelt.'
ms.openlocfilehash: 630ab5165c3c7bb3a64663d54ef750fe9275f932
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219659"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Konfigurieren von CUCM für die Interoperation mit Skype für Business Server
 
**Zusammenfassung:** Konfigurieren von CUCM Skype für Business Server entwickelt.
  
> [!CAUTION]
> Diese Funktion wird getestet, mit Cisco Unified Communications Manager (CallManager oder CUCM) Version 10.5 Trunks von setup über TCP. Vergewissern Sie sich, dass die CUCM-Umgebung diese Kriterien erfüllt, bevor Sie fortfahren. 
  
Die hier beschriebenen Einstellungen Präsentationsstil nur als Beispiele wie CUCM konfiguriert werden kann einen VIS. entwickelt Andere Einstellungen und/oder Verwendungsmöglichkeiten von alternativen CUCM-Funktionen können auch zum Erzielen des gleichen Ergebnisses herangezogen werden. Es werden keine Empfehlungen hinsichtlich der optimalen Konfiguration für ein bestimmtes Szenario gegeben.
  
Mehrere CUCM-Einstellungen müssen für die Interoperabilität mit dem VIS bestätigt oder geändert werden. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass Sie keine erforderlichen Einstellungen übersehen.
  
### <a name="configure-the-cucm"></a>Konfigurieren von CUCM

1. Melden Sie sich an CUCM, und navigieren Sie zu Cisco Unified CM Administration-\>Call Routing -\>Klasse der Steuerelement -\>Partition.
    
2. Geben Sie auf dem Bildschirm „Partition Configuration“ (Partitionskonfiguration) den Namen der Partition sowie eine Beschreibung ein und klicken Sie auf **Add New** (Neu hinzufügen).
    
3. Navigieren Sie zu Cisco Unified CM Administration-\>Call Routing -\>Klasse von Steuerelement -\>Suche Speicherplatz aufrufen.
    
4. Geben Sie auf dem Bildschirm „Calling Search Space Configuration“ (Konfiguration des Anrufsuchbereichs) den Namen des Anrufsuchbereichs und unter „Selected Partitions“ (Ausgewählte Partitionen) den Namen der soeben erstellten Partition ein. Klicken Sie abschließend auf **Save** (Speichern).
    
5. Navigieren Sie zu Cisco Unified CM Administration-\>System -\>Security -\>SIP-Trunk Security-Profil.
    
6. Legen Sie auf dem Bildschirm „SIP Trunk Security Profile Configuration“ (Konfiguration des SIP-Trunk-Sicherheitsprofils) die Informationen des SIP-Trunk-Sicherheitsprofils wie im Folgenden angegeben fest. Klicken Sie dann auf **Add New** (Neu hinzufügen).
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Device Security Mode (Gerätesicherheitsmodus)  <br/> |Non Secure (Nicht sicher)  <br/> |
   |Incoming Transport Type (Typ des eingehenden Transportprotokolls)  <br/> |TCP + UDP  <br/> |
   |Outgoing Transport Type (Typ des ausgehenden Transportprotokolls)  <br/> |TCP  <br/> |
   |Incoming Port (Eingehender Port)  <br/> |5060  <br/> |
   
7. Navigieren Sie zu Cisco Unified CM Administration -\>Gerät -\>Gerät Einstellungen -\>SIP-Profil.
    
8. Geben Sie auf dem Bildschirm „SIP Profile Configuration“ (Konfiguration des SIP-Profils) die Informationen des SIP-Profils wie im Folgenden angegeben ein. 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Description (Beschreibung)  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Führen Sie auf der gleichen Seite einen Bildlauf nach unten zum Abschnitt SDP-Profilinformationen. Die Option **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** (SDP-Bandbreitenänderung auf Sitzungsebene für Early Offer und Neueinladungen) ist standardmäßig auf „TIAS and AS“ (TIAS und AS) eingestellt. Ändern Sie diese Option auf „TIAS only“ (Nur TIAS). Wenn Sie die Standardeinstellung dieser Option lassen, wird die Bandbreite Modifiziererinformationen in der SIP-Nachricht von Skype für Business Server nicht verstehen. TIAS steht für „Transport Independent Application Specific“ (transportunabhängig anwendungsspezifisch) und AS für „Application Specific“ (anwendungsspezifisch). Diese SIP-Optionen sind in RFC3890 festgelegt.
    
10. Klicken Sie auf der gleichen Seite einen Bildlauf weiter. Wählen Sie unter der SIP-Profil-Trunk-Workflowkonfiguration **Frühe bieten Unterstützung für Audio- und Videoanrufe** , und legen Sie diese auf die Option **obligatorisch (Einfügen MTP, falls erforderlich)** . Dadurch CUCM zum Einrichten eines ausgehenden Anrufs SIP mit Early anbieten. Ein neues Feature in CUCM 8,5 und darüber hinaus ist, dass es ausgehenden Anruf Setup mit Early bieten ohne Media Beendigung Point (MTP) unterstützt.
    
11. Überprüfen Sie im Abschnitt „SIP Options ping“ (SIP-Optionen-Ping), ob das Kontrollkästchen neben „Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'“ (Optionen-Ping zur Überwachung des Zielstatus für Trunks mit Diensttyp 'Keiner' aktivieren (Standard)) aktiviert ist.
    
12. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **Add New** (Neu hinzufügen).
    
13. Navigieren Sie zu Cisco Unified CM Administration -\>Gerät -\>Trunk. 
    
14. Stellen Sie das Geräteprotokoll auf „SIP“ ein und klicken Sie auf **Next** (Weiter).
    
15. Wählen Sie unter „Device Information“ (Geräteinformationen) den Namen und die Beschreibung des Geräts aus (z. B. „SfBVideoInterop_SIPTrunk“) und legen Sie für „Media Resource Group List“ (Liste der Medienressourcengruppe) eine MRGL fest, die die richtigen Medienressourcen enthält. 
    
16. Scrollen Sie noch weiter nach unten. Media Beendigung Point (MTP) ist nicht für Videokonferenzen erforderlich, wenn nicht deaktiviert ist, deaktivieren Sie es. Überprüfen Sie die Option zum **Ausführen auf allen aktiven Unified CM-Knoten**. Beachten Sie, dass Sie alle CUCM Knoten der Skype für Business Server-Konfiguration hinzufügen sollten.
    
17. Scrollen Sie nach unten. Legen Sie die Optionen für „Inbound Calls“ (Eingehende Anrufe) und „Connected Party Settings“ (Einstellungen des verbundenen Teilnehmers) wie im Folgenden angegeben fest.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Calling Search Space (Anrufsuchbereich)  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space (AAR-Anrufsuchbereich)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Connected Party Transformation CSS (Transformations-CSS des verbundenen Teilnehmers)  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scrollen Sie noch weiter nach unten. Geben Sie unter im Abschnitt Ziel für SIP-Informationen der SIP-Trunk-Konfiguration die gegenüber Pool-FQDN oder die IP-Adresse des einzelnen gegenüber Servern im Pool (mehrere Einträge hinzufügen). Geben Sie unter „Destination Port“ (Zielport) den Port an, den VIS für Verbindungen von CUCM überwachen soll (Standardwert ist 6001). Geben Sie wie dargestellt auch das vorher erstellte SIP-Trunk-Sicherheitsprofil und SIP-Profil an.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |SIP Trunk Security Profile (SIP-Trunk-Sicherheitsprofil)  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rerouting Calling Search Space (Umleitung des Anrufsuchbereichs)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space (Anrufsuchbereich außerhalb des Dialogs zuweisen)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space (Anrufsuchbereich abonnieren)  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP Profile (SIP-Profil)  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method (DTMF-Signalmethode)  <br/> |RFC 2833  <br/> |
   
19.  Scrollen Sie noch weiter nach unten. Legen Sie die Aufzeichnungsinformationen gemäß den für Ihr System geeigneten Einstellungen fest. Lassen Sie es auf **None**festgelegt werden. 
    
20. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **Add New** (Neu hinzufügen).
    
21. Navigieren Sie zu Cisco Unified CM Administration-\>Call Routing -\>Route/Sammelanschlüsse-\>Routenmuster.
    
22. Geben Sie im Bildschirm Routenkonfiguration Muster der unten angezeigten Muster-Definition-Parameter aus. Führen Sie einen Bildlauf nach unten zum Abschnitt Partei Transformationen aufgerufen und legen Sie die Maske wie dargestellt, und klicken Sie dann auf **Neu hinzufügen** nach Abschluss des.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Routenmuster  <br/> |7779999  <br/> |
    |Route Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Beschreibung  <br/> |Partition für SfBVideoInterop  <br/> |
    |Liste der Gateway-Route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Aufgerufen von Teilnehmern Transform Maske  <br/> |+14257779999  <br/> |
   
23. Navigieren Sie zu Cisco Unified CM Administration-\>Call Routing -\>Routen SIP-Muster.
    
24. Legen Sie im Bildschirm SIP-Muster Routenkonfiguration die Optionen Musterdefinition wie dargestellt, und klicken Sie auf **Neu hinzufügen**.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    | Muster Verwendung <br/> |Domäne-Routing  <br/> |
    |IPv4-Muster  <br/> |Contoso.com (leer lassen, wenn IPv6 verwenden)  <br/> |
    |IPv6-Muster  <br/> |Contoso.com (leer lassen, wenn IPv4 verwenden)  <br/> |
    |Beschreibung  <br/> |SIPRoute Muster mediarv  <br/> |
    |Route Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Liste der SIP-Trunk-Route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Das Kontrollkästchen Block Muster  <br/> |Lassen Sie deaktiviert  <br/> |
   
25. Wenn Sie die Audio- oder Videodatei Bitraten von den Standardeinstellungen geändert haben, müssen Sie diese auf die Standardwerte zurück. Um die Bitrate für Audio-/Videoanrufen festzulegen, navigieren Sie zu Cisco Unified CM Administration -\>System -\>Region Informationen -\>Region. Die Standardwerte sind als Referenz unten aufgeführt:
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Region  <br/> |Standard  <br/> |
    |Liste der bevorzugten Audiocodec  <br/> |Standardeinstellungen des Systems  <br/> |
    |Maximale Bitrate für Audio  <br/> |64 Kbit/s (g. 722, g. 711)  <br/> |
    |Maximale Bitrate für Videoanrufe  <br/> |200000 Kbit/s  <br/> |
    |Maximale Bitrate  <br/> |2000000000 Kbit/s  <br/> |
   
An dieser Stelle wird das video CUCM-Gateway konfiguriert die VIS. entwickelt Entsprechende Konfiguration müssen für jeden VTC ausgeführt werden, die Sie integrieren möchten.
> [!NOTE]
> Um ausfallsicherheit zu verbessern, sollten Sie dieses Gateway CUCM entwickelt einen zweiten Interop Videoserver oder gegenüber Pool zu konfigurieren. Weitere Informationen finden Sie unter [Resiliency Mechanismen](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren einer VTC für die Interoperation mit Skype für Business Server](configure-a-vtc-for-interoperation.md)
