---
title: Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Zusammenfassung: Konfigurieren sie CUCM für die Zusammenarbeit mit Skype for Business Server.'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837115"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie CUCM für die Zusammenarbeit mit Skype for Business Server.
  
> [!CAUTION]
> Diese Funktion wird mit Cisco Unified Communications Manager (CallManager oder CUCM) Version 10.5 getestet, bei dem Trunks nur über TCP eingerichtet werden. Stellen Sie sicher, dass die Umgebung cuCM diese Kriterien erfüllt, bevor Sie fortfahren. 
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Verwendung mit einem VIS konfiguriert werden kann. Es können auch andere Einstellungen und/oder Verwendungen alternativer CUCM-Funktionen verwendet werden, um dasselbe Ergebnis zu erzielen. Es wird keine Empfehlung zur optimalen Konfiguration für ein bestimmtes Szenario impliziert.
  
Eine Reihe von CUCM-Einstellungen muss für die Interoperabilität mit dem VIS bestätigt oder geändert werden. Führen Sie die folgenden Verfahren aus, um zu vermeiden, dass erforderliche Einstellungen fehlen.
  
### <a name="configure-the-cucm"></a>Konfigurieren des CUCM

1. Melden Sie sich beim CUCM an, und navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition.
    
2. Geben Sie auf dem Bildschirm "Partitionskonfiguration" den Partitionsnamen und die Beschreibung ein, und klicken Sie auf **"Neu hinzufügen".**
    
3. Navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space.
    
4. Geben Sie auf dem Bildschirm "Konfiguration des Anrufsuchbereichs" den Namen für den aufrufenden Suchbereich ein, und geben Sie in "Ausgewählte Partitionen" den Namen der gerade erstellten Partition ein. Klicken **Sie auf "Speichern",** wenn Sie fertig sind.
    
5. Navigieren Sie zu Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile.
    
6. Legen Sie auf dem Bildschirm "SIP-Trunk-Sicherheitsprofilkonfiguration" die Optionen für informationen zum SIP-Trunk-Sicherheitsprofil wie dargestellt, und klicken Sie auf "Neu **hinzufügen".**
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Gerätesicherheitsmodus  <br/> |Nicht sicher  <br/> |
   |Eingehender Transporttyp  <br/> |TCP + UDP  <br/> |
   |Ausgehender Transporttyp  <br/> |TCP  <br/> |
   |Eingehender Port  <br/> |5060  <br/> |
   
7. Navigieren Sie zu Cisco Unified CM Administration- \> \> Device- Device Settings- \> SIP Profile.
    
8. Legen Sie auf dem Bildschirm "SIP-Profilkonfiguration" die Optionen für die SIP-Profilinformationen wie dargestellt. 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Beschreibung  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Scrollen Sie auf demselben Bildschirm nach unten zum Abschnitt "SDP-Profilinformationen". Der Bandbreitenmodifizierer auf SDP-Sitzungsebene für early **Offer and Re-invites** ist standardmäßig auf TIAS und AS festgelegt. Ändern Sie diese Option nur in TIAS. Wenn Sie diese Option auf die Standardeinstellung festlegen, versteht Skype for Business Server die Informationen zum Bandbreitenmodifizierer in der SIP-Nachricht nicht. TIAS bedeutet transportunabhängige Anwendungsspezifisch, as bedeutet anwendungsspezifisch. Dies sind SIP-Optionen, die in RFC3890 angegeben sind.
    
10. Scrollen Sie auf demselben Bildschirm weiter nach unten. Wählen Sie unter der trunkspezifischen Konfiguration des SIP-Profils die Option "Early **Offer Support for voice and video calls"** aus, und legen Sie sie auf die Option "Obligatorisch" **(MTP** bei Bedarf einfügen) festgelegt. Dadurch kann CUCM einen ausgehenden SIP-Anruf mit early Offer einrichten. Eine neue Funktion in CUCM 8.5 und darüber hinaus ist, dass das Setup ausgehender Anrufe mit early Offer unterstützt wird, ohne dass ein Medienendpunkt (Media Termination Point, MTP) erforderlich ist.
    
11. Stellen Sie sicher, dass im Abschnitt "SIP-Optionen-Ping" das Kontrollkästchen neben "Optionen pingen aktivieren, um den Zielstatus für Trunks mit dem Diensttyp 'None (Default)' zu überwachen" aktiviert ist.
    
12. Wenn Sie fertig sind, klicken Sie auf **"Neu hinzufügen".**
    
13. Navigieren Sie zu Cisco Unified CM Administration- \> Device- \> Trunk. 
    
14. Legen Sie das Geräteprotokoll auf SIP und drücken Sie dann **"Weiter".**
    
15. Legen Sie unter "Geräteinformationen" den Gerätenamen und die Gerätebeschreibung (wahrscheinlich auf etwa SfBVideoInterop_SIPTrunk) und die Liste der Medienressourcengruppen auf eine MRGL fest, die die richtigen Medienressourcen enthält. 
    
16. Scrollen Sie weiter nach unten. Der Medienendpunkt (Media Termination Point, MTP) ist für Videoanrufe nicht erforderlich, wenn er noch nicht deaktiviert ist, deaktivieren Sie ihn. Aktivieren Sie die Option zum **Ausführen auf allen aktiven einheitlichen CM-Knoten.** Bitte beachten Sie, dass Sie alle CUCM-Knoten zur Skype for Business Server-Konfiguration hinzufügen sollten.
    
17. Scrollen Sie weiter nach unten. Legen Sie die Einstellungen für eingehende Anrufe und verbundene Parteien wie dargestellt fest.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Anrufsuchbereich  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Connected Party Transformation CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scrollen Sie weiter nach unten. Geben Sie im Abschnitt "SIP-Informationsziel" der SIP-Trunkkonfiguration den FQDN des VIS-Pools oder die IP-Adresse einzelner VIS-Server im Pool an (hinzufügen mehrerer Einträge). Geben Sie im Zielport den Port an, auf den der VIS auf Verbindungen von CUCM lauscht (der Standardwert ist 6001). Geben Sie außerdem das zuvor erstellte SIP-Trunk-Sicherheitsprofil und das SIP-Profil an, wie dargestellt.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |SIP-Trunk-Sicherheitsprofil  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Erneutes Umleitung des Suchbereichs für Anrufe  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Abonnieren des Suchbereichs für Anrufe  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP-Profil  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF Signaling (Methode)  <br/> |RFC 2833  <br/> |
   
19.  Scrollen Sie weiter nach unten. Legen Sie die Aufzeichnungsinformationen entsprechend Ihrem System. Es ist in Ordnung, es auf Keine festgelegt **zu lassen.** 
    
20. Wenn Sie fertig sind, klicken Sie auf **"Neu hinzufügen".**
    
21. Navigieren Sie zum Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt-Route-Muster. \>
    
22. Geben Sie auf dem Bildschirm "Routenmusterkonfiguration" die unten gezeigten Musterdefinitionsparameter ein. Scrollen Sie nach unten zum Abschnitt "Transformationen des angerufenen Parteien", legen Sie die Maske wie dargestellt fest, und klicken Sie dann auf **"Neu** hinzufügen", wenn Sie fertig sind.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Routenmuster  <br/> |7779999  <br/> |
    |Routenpartition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Beschreibung  <br/> |Partition für SfBVideoInterop  <br/> |
    |Gateway-/Routenliste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |So genannte Partytransformationsmaske  <br/> |+14257779999  <br/> |
   
23. Navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern.
    
24. Legen Sie auf dem Bildschirm "SIP-Routenmusterkonfiguration" die Musterdefinitionsoptionen wie dargestellt, und klicken Sie auf **"Neu hinzufügen".**
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    | Musterverwendung <br/> |Domänenrouting  <br/> |
    |IPv4-Muster  <br/> |contoso.com (bei Verwendung von IPv6 leer lassen)  <br/> |
    |IPv6-Muster  <br/> |contoso.com (bei Verwendung von IPv4 leer lassen)  <br/> |
    |Beschreibung  <br/> |SIPRoute Pattern to mediarv  <br/> |
    |Routenpartition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP-Trunk-/Routenliste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Kontrollkästchen "Muster blockieren"  <br/> |lassen Sie es deaktiviert  <br/> |
   
25. Wenn Sie die Audio- oder Videobitraten von den Standardeinstellungen geändert haben, müssen Sie sie auf die Standardwerte zurücksetzen. Zum Festlegen der Bitrate für Audio-/Videoanrufe navigieren Sie zu Cisco Unified CM Administration- \> System- \> Region Information - \> Region. Die Standardwerte sind unten als Referenz aufgeführt:
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Region  <br/> |Standard  <br/> |
    |Einstellungsliste für Audiocodec  <br/> |System standard  <br/> |
    |Maximale Audiobitrate  <br/> |64 KBit/s (G.722, G.711)  <br/> |
    |Maximale Sitzungsbitrate für Videoanrufe  <br/> |200000 KBit/s  <br/> |
    |Maximale Sitzungsbitrate  <br/> |2000000000 KBit/s  <br/> |
   
An diesem Punkt ist das CUCM-Videogateway für die Verwendung mit dem VIS konfiguriert. Die entsprechende Konfiguration muss auf jedem VTC durchgeführt werden, den Sie integrieren möchten.
> [!NOTE]
> Um die Resilienz zu verbessern, können Sie dieses GATEWAY für die Verwendung mit einem zweiten Video-Interop-Server oder -VIS-Pool konfigurieren. Weitere [Informationen finden Sie unter "Ausfallsicherheitsmechanismen".](../../plan-your-deployment/video-interop-server.md#resiliency)
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server](configure-a-vtc-for-interoperation.md)
