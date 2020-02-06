---
title: Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Zusammenfassung: Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server.'
ms.openlocfilehash: 0f8b5321b482d78d9dc833471323ae842c247246
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798072"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server.
  
> [!CAUTION]
> Diese Funktion wird mit Cisco Unified Communications Manager (CallManager oder CUCM) Version 10,5 unter Verwendung von Trunks-Setup über TCP getestet. Vergewissern Sie sich, dass die CUCM-Umgebung diese Kriterien erfüllt, bevor Sie fortfahren. 
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Arbeit mit einem VIS konfiguriert werden kann. Andere Einstellungen und/oder Verwendungsmöglichkeiten von alternativen CUCM-Funktionen können auch zum Erzielen des gleichen Ergebnisses herangezogen werden. Es werden keine Empfehlungen hinsichtlich der optimalen Konfiguration für ein bestimmtes Szenario gegeben.
  
Mehrere CUCM-Einstellungen müssen für die Interoperabilität mit dem VIS bestätigt oder geändert werden. Führen Sie die folgenden Schritte aus, um sicherzustellen, dass Sie keine erforderlichen Einstellungen übersehen.
  
### <a name="configure-the-cucm"></a>Konfigurieren von CUCM

1. Melden Sie sich bei CUCM an, und navigieren Sie zu Cisco\>Unified cm Administration\>– Anrufweiterleitung –\>Klasse der Steuerung – Partition.
    
2. Geben Sie auf dem Bildschirm „Partition Configuration“ (Partitionskonfiguration) den Namen der Partition sowie eine Beschreibung ein und klicken Sie auf **Add New** (Neu hinzufügen).
    
3. Navigieren Sie zu Cisco Unified cm Administration\>– Anrufweiterleitung\>– Klasse des Steuer\>Elements – aufrufen des Suchbereichs.
    
4. Geben Sie auf dem Bildschirm „Calling Search Space Configuration“ (Konfiguration des Anrufsuchbereichs) den Namen des Anrufsuchbereichs und unter „Selected Partitions“ (Ausgewählte Partitionen) den Namen der soeben erstellten Partition ein. Klicken Sie abschließend auf **Save** (Speichern).
    
5. Navigieren Sie zu Cisco Unified cm Administration\>-System\>-Security\>-SIP Trunk Security Profile.
    
6. Legen Sie auf dem Bildschirm „SIP Trunk Security Profile Configuration“ (Konfiguration des SIP-Trunk-Sicherheitsprofils) die Informationen des SIP-Trunk-Sicherheitsprofils wie im Folgenden angegeben fest. Klicken Sie dann auf **Add New** (Neu hinzufügen).
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Device Security Mode (Gerätesicherheitsmodus)  <br/> |Non Secure (Nicht sicher)  <br/> |
   |Incoming Transport Type (Typ des eingehenden Transportprotokolls)  <br/> |TCP + UDP  <br/> |
   |Outgoing Transport Type (Typ des ausgehenden Transportprotokolls)  <br/> |TCP  <br/> |
   |Incoming Port (Eingehender Port)  <br/> |5060  <br/> |
   
7. Navigieren Sie zu Cisco Unified cm Administration\>-Device\>-Device Settings\>-SIP-Profil.
    
8. Geben Sie auf dem Bildschirm „SIP Profile Configuration“ (Konfiguration des SIP-Profils) die Informationen des SIP-Profils wie im Folgenden angegeben ein. 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Description (Beschreibung)  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Scrollen Sie auf demselben Bildschirm nach unten zum Abschnitt SDP-Profilinformationen. Die Option **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** (SDP-Bandbreitenänderung auf Sitzungsebene für Early Offer und Neueinladungen) ist standardmäßig auf „TIAS and AS“ (TIAS und AS) eingestellt. Ändern Sie diese Option auf „TIAS only“ (Nur TIAS). Wenn Sie diese Option bei der Standardeinstellung beließen, wird Skype for Business Server die Informationen zur Bandbreiten Modifizierung in der SIP-Nachricht nicht verstehen. TIAS steht für „Transport Independent Application Specific“ (transportunabhängig anwendungsspezifisch) und AS für „Application Specific“ (anwendungsspezifisch). Diese SIP-Optionen sind in RFC3890 festgelegt.
    
10. Scrollen Sie auf demselben Bildschirm weiter nach unten. Wählen Sie unter der trunk-spezifischen Konfiguration des SIP-Profils **Early offer Support für Sprach-und Videoanrufe** aus, und legen Sie die Option auf die **obligatorische Option (Insert MTP falls erforderlich)** fest. Dadurch wird es CUCM möglich, einen ausgehenden SIP-Anruf mit einem frühen Angebot einzurichten. Ein neues Feature in CUCM 8,5 und darüber hinaus ist die Unterstützung der Einrichtung für ausgehende Anrufe mit einem frühen Angebot, ohne dass ein Media Termination Point (MTP) erforderlich ist.
    
11. Überprüfen Sie im Abschnitt „SIP Options ping“ (SIP-Optionen-Ping), ob das Kontrollkästchen neben „Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'“ (Optionen-Ping zur Überwachung des Zielstatus für Trunks mit Diensttyp 'Keiner' aktivieren (Standard)) aktiviert ist.
    
12. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **Add New** (Neu hinzufügen).
    
13. Navigieren Sie zu Cisco Unified cm Administration\>-Device\>-trunk. 
    
14. Stellen Sie das Geräteprotokoll auf „SIP“ ein und klicken Sie auf **Next** (Weiter).
    
15. Wählen Sie unter „Device Information“ (Geräteinformationen) den Namen und die Beschreibung des Geräts aus (z. B. „SfBVideoInterop_SIPTrunk“) und legen Sie für „Media Resource Group List“ (Liste der Medienressourcengruppe) eine MRGL fest, die die richtigen Medienressourcen enthält. 
    
16. Scrollen Sie noch weiter nach unten. Media Termination Point (MTP) ist für Video Anrufe nicht erforderlich, wenn Sie nicht bereits deaktiviert sind, deaktivieren Sie Sie. Aktivieren Sie die Option zum **Ausführen auf allen aktiven Unified cm-Knoten**. Beachten Sie bitte, dass Sie alle CUCM-Knoten zur Konfiguration von Skype for Business Server hinzufügen sollten.
    
17. Scrollen Sie nach unten. Legen Sie die Optionen für „Inbound Calls“ (Eingehende Anrufe) und „Connected Party Settings“ (Einstellungen des verbundenen Teilnehmers) wie im Folgenden angegeben fest.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Calling Search Space (Anrufsuchbereich)  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space (AAR-Anrufsuchbereich)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Connected Party Transformation CSS (Transformations-CSS des verbundenen Teilnehmers)  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scrollen Sie noch weiter nach unten. Geben Sie im Abschnitt SIP-Informationsziel der SIP-Trunk-Konfiguration den FQDN des VIS-Pools oder die IP-Adresse einzelner VIS-Server im Pool an (mehrere Einträge hinzufügen). Geben Sie unter „Destination Port“ (Zielport) den Port an, den VIS für Verbindungen von CUCM überwachen soll (Standardwert ist 6001). Geben Sie wie dargestellt auch das vorher erstellte SIP-Trunk-Sicherheitsprofil und SIP-Profil an.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |SIP Trunk Security Profile (SIP-Trunk-Sicherheitsprofil)  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rerouting Calling Search Space (Umleitung des Anrufsuchbereichs)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space (Anrufsuchbereich außerhalb des Dialogs zuweisen)  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space (Anrufsuchbereich abonnieren)  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP Profile (SIP-Profil)  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling Method (DTMF-Signalmethode)  <br/> |RFC 2833  <br/> |
   
19.  Scrollen Sie noch weiter nach unten. Legen Sie die Aufzeichnungsinformationen gemäß den für Ihr System geeigneten Einstellungen fest. Es ist in Ordnung, es auf " **keine**" zu setzen. 
    
20. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **Add New** (Neu hinzufügen).
    
21. Navigieren Sie zu Cisco Unified cm Administration\>– Anrufweiterleitung\>– Route/Route\>-Muster.
    
22. Geben Sie im Bildschirm Routenmuster-Konfiguration die unten gezeigten Muster Definitions Parameter ein. Scrollen Sie nach unten zum Abschnitt benannte Partei Umwandlungen, und legen Sie die Maske wie gezeigt fest, und klicken Sie dann auf **Neu hinzufügen** , wenn Sie fertig sind.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Routenmuster  <br/> |7779999  <br/> |
    |Route-Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Beschreibung  <br/> |Partition für SfBVideoInterop  <br/> |
    |Gateway/Routenliste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Benannte Partei-Transformations Maske  <br/> |+ 14257779999  <br/> |
   
23. Navigieren Sie zu Cisco Unified cm Administration\>– Anrufweiterleitung\>– SIP-Routenmuster.
    
24. Legen Sie im Bildschirm SIP-Routenmuster Konfiguration die Muster Definitions Optionen wie gezeigt fest, und klicken Sie auf **Neu hinzufügen**.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    | Muster Verwendung <br/> |Domänen Routing  <br/> |
    |IPv4-Muster  <br/> |contoso.com (bei Verwendung von IPv6 leer lassen)  <br/> |
    |IPv6-Muster  <br/> |contoso.com (bei Verwendung von IPv4 leer lassen)  <br/> |
    |Beschreibung  <br/> |SIPRoute-Muster zu mediarv  <br/> |
    |Route-Partition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP Trunk/Route-Liste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Kontrollkästchen ' Block Muster '  <br/> |deaktiviert bleiben  <br/> |
   
25. Wenn Sie die Audio-oder Video-Bitraten von den Standardeinstellungen geändert haben, müssen Sie Sie auf die Standardeinstellungen zurücksetzen. Wenn Sie die Bitrate für Audio-und Video Anrufe einstellen möchten, navigieren Sie zu Cisco Unified\>cm Administration\>-System-\>Region Information-Region. Nachfolgend werden die Standardwerte als Referenz angezeigt:
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Region  <br/> |Standard  <br/> |
    |Audiocodec-Einstellungsliste  <br/> |System Standard  <br/> |
    |Maximale Audiobitrate  <br/> |64 Kbit/s (g. 722, g. 711)  <br/> |
    |Maximale Sitzungs-Bitrate für Video Anrufe  <br/> |200000 Kbit/s  <br/> |
    |Maximale Sitzungs-Bitrate  <br/> |2 Milliarden Kbit/s  <br/> |
   
An diesem Punkt ist das CUCM-Video Gateway so konfiguriert, dass es mit dem VIS funktioniert. Die entsprechende Konfiguration muss auf jeder VTC erfolgen, die Sie integrieren möchten.
> [!NOTE]
> Um die Widerstandsfähigkeit zu verbessern, sollten Sie dieses CUCM-Gateway für den Einsatz mit einem zweiten Video-Interop-Server oder VIS-Pool konfigurieren. Weitere Informationen finden Sie unter [Resilienz-Mechanismen](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server](configure-a-vtc-for-interoperation.md)
