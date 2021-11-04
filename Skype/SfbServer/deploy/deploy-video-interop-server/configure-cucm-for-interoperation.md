---
title: Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 'Zusammenfassung: Konfigurieren von CUCM für die Arbeit mit Skype for Business Server.'
ms.openlocfilehash: 809ad19e89f398c507673ec677b4ce882d341327
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741321"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Konfigurieren von CUCM für die Interoperabilität mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie CUCM für die Arbeit mit Skype for Business Server.
  
> [!CAUTION]
> Diese Funktion wird mit Cisco Unified Communications Manager (CallManager, oder CUCM) Version 10.5 getestet, indem nur Trunks über TCP eingerichtet werden. Vergewissern Sie sich, dass die CUCM-Umgebung diese Kriterien erfüllt, bevor Sie fortfahren. 
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Verwendung mit einem VIS konfiguriert werden kann. Andere Einstellungen und/oder Verwendungen alternativer CUCM-Funktionen können ebenfalls verwendet werden, um dasselbe Ergebnis zu erzielen. Es wird keine Empfehlung hinsichtlich der optimalen Konfiguration für ein bestimmtes Szenario impliziert.
  
Eine Reihe von CUCM-Einstellungen muss für die Interoperabilität mit dem VIS bestätigt oder geändert werden. Führen Sie die folgenden Verfahren aus, um fehlende erforderliche Einstellungen zu vermeiden.
  
### <a name="configure-the-cucm"></a>Konfigurieren des CUCM

1. Melden Sie sich bei CUCM an, und navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition.
    
2. Geben Sie im Bildschirm "Partitionskonfiguration" den Partitionsnamen und die Beschreibung ein, und klicken Sie auf **"Neu hinzufügen".**
    
3. Navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space.
    
4. Geben Sie auf dem Bildschirm "Konfiguration des Anrufsuchbereichs" den Namen für den aufrufenden Suchbereich ein, und geben Sie unter "Ausgewählte Partitionen" den Namen der Partition ein, die Sie soeben erstellt haben. Klicken Sie auf **"Speichern",** wenn Sie fertig sind.
    
5. Navigieren Sie zu Cisco Unified CM Administration- \> System- \> Security- \> SIP Trunk Security Profile.
    
6. Legen Sie auf dem Bildschirm "Konfiguration des SIP-Trunksicherheitsprofils" die Optionen für SIP-Trunk-Sicherheitsprofilinformationen wie dargestellt fest, und klicken Sie auf **"Neu hinzufügen".**
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Gerätesicherheitsmodus  <br/> |Nicht sicher  <br/> |
   |Eingehender Transporttyp  <br/> |TCP + UDP  <br/> |
   |Ausgehender Transporttyp  <br/> |TCP  <br/> |
   |Eingehender Port  <br/> |5060  <br/> |
   
7. Navigieren Sie zu Cisco Unified CM Administration- \> Device- \> Device Einstellungen- \> SIP Profile.
    
8. Legen Sie auf dem Bildschirm "SIP-Profilkonfiguration" die Optionen für SIP-Profilinformationen wie dargestellt fest. 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Name  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Beschreibung  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Scrollen Sie auf demselben Bildschirm nach unten zum Abschnitt "SDP-Profilinformationen". Der **SDP-Bandbreitenmodifizierer auf Sitzungsebene für die Option "Early Offer" und "Re-invites"** ist standardmäßig auf TIAS und AS festgelegt. Ändern Sie diese Option nur in TIAS. Wenn Sie diese Option bei der Standardeinstellung belassen, verstehen Skype for Business Server die Informationen zur Bandbreitenmodifizierer in der SIP-Nachricht nicht. TIAS bedeutet Transport Independent Application Specific, as means Application Specific. Hierbei handelt es sich um SIP-Optionen, die in RFC3890 angegeben sind.
    
10. Scrollen Sie auf demselben Bildschirm weiter nach unten. Wählen Sie unter der trunkspezifischen Konfiguration des SIP-Profils die Option **"Early Offer Support for voice and video calls" aus,** und legen Sie sie auf die **Option "Obligatorisch" (bei Bedarf MTP einfügen)** fest. Dadurch kann CUCM einen ausgehenden SIP-Anruf mit frühem Angebot einrichten. Ein neues Feature in CUCM 8.5 und darüber hinaus besteht darin, dass es die Einrichtung ausgehender Anrufe mit early Offer unterstützt, ohne dass ein Medienendpunkt (Media Termination Point, MTP) erforderlich ist.
    
11. Stellen Sie sicher, dass im Abschnitt "SIP-Optionen Ping" das Kontrollkästchen neben "Options Ping to monitor destination status for Trunks with Service Type 'None (Default)' aktiviert ist."
    
12. Wenn Sie fertig sind, klicken Sie auf **"Neu hinzufügen".**
    
13. Navigieren Sie zu Cisco Unified CM Administration- \> Device- \> Trunk. 
    
14. Legen Sie das Geräteprotokoll auf SIP fest, und drücken Sie **"Weiter".**
    
15. Legen Sie unter "Geräteinformationen" den Gerätenamen und die Beschreibung fest (wahrscheinlich auf SfBVideoInterop_SIPTrunk), und legen Sie die Medienressourcen-Gruppenliste auf einen MRGL fest, der die richtigen Medienressourcen enthält. 
    
16. Scrollen Sie weiter nach unten. Der Medienendpunkt (Media Termination Point, MTP) ist für Videoanrufe nicht erforderlich, wenn er noch nicht deaktiviert ist, deaktivieren Sie ihn. Aktivieren Sie die Option zum **Ausführen auf allen aktiven einheitlichen CM-Knoten.** Bitte beachten Sie, dass Sie der Skype for Business Server Konfiguration alle CUCM-Knoten hinzufügen sollten.
    
17. Scrollen Sie weiter nach unten. Legen Sie die Optionen für eingehende Anrufe und Einstellungen verbundene Parteien wie dargestellt fest.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Aufrufen des Suchbereichs  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR-Anrufsuchbereich  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS zur Transformation verbundener Parteien  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scrollen Sie weiter nach unten. Geben Sie im Abschnitt "SIP Information Destination" der SIP-Trunkkonfiguration den FQDN des VIS-Pools oder die IP-Adresse einzelner VIS-Server im Pool an (hinzufügen mehrerer Einträge). Geben Sie im Zielport den Port an, an dem der VIS auf Verbindungen von CUCM lauscht (der Standardwert ist 6001). Geben Sie außerdem das sip-Trunk-Sicherheitsprofil und das SIP-Profil an, das Sie zuvor erstellt haben( siehe Abbildung).
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |SIP-Trunk-Sicherheitsprofil  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Umrouting des Anrufsuchbereichs  <br/> |CSS_SfBVideoInterop  <br/> |
    |Nicht im Dialogfeld angezeigter Suchbereich "Anrufverweisen"  <br/> |CSS_SfBVideoInterop  <br/> |
    |Abonnieren des Suchbereichs für Anrufe  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP-Profil  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF-Signalisierungsmethode  <br/> |RFC 2833  <br/> |
   
19.  Scrollen Sie weiter nach unten. Legen Sie die Aufzeichnungsinformationen entsprechend ihrem System fest. Es ist in Ordnung, es auf **None** festgelegt zu lassen. 
    
20. Wenn Sie fertig sind, klicken Sie auf **"Neu hinzufügen".**
    
21. Navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- \> Route pattern.
    
22. Geben Sie im Bildschirm "Konfiguration des Routenmusters" die unten gezeigten Musterdefinitionsparameter ein. Scrollen Sie nach unten zum Abschnitt "Transformationen aufgerufener Parteien", legen Sie die Maske wie dargestellt fest, und klicken Sie dann auf **"Neu hinzufügen",** wenn Sie fertig sind.
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Routenmuster  <br/> |7779999  <br/> |
    |Routenpartition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Beschreibung  <br/> |Partition für SfBVideoInterop  <br/> |
    |Gateway-/Routenliste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Aufgerufene PartyTransformationsmaske  <br/> |+14257779999  <br/> |
   
23. Navigieren Sie zu Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern.
    
24. Legen Sie auf dem Bildschirm "SIP-Routenmusterkonfiguration" die Musterdefinitionsoptionen wie dargestellt fest, und klicken Sie auf **"Neu hinzufügen".**
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    | Musterverwendung <br/> |Domänenrouting  <br/> |
    |IPv4-Muster  <br/> |contoso.com (bei Verwendung von IPv6 leer lassen)  <br/> |
    |IPv6-Muster  <br/> |contoso.com (bei Verwendung von IPv4 leer lassen)  <br/> |
    |Beschreibung  <br/> |SIPRoute-Muster für mediarv  <br/> |
    |Routenpartition  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP-Trunk-/Routenliste  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Kontrollkästchen "Muster blockieren"  <br/> |Deaktiviert lassen  <br/> |
   
25. Wenn Sie die Audio- oder Videobitraten von den Standardeinstellungen geändert haben, müssen Sie sie auf die Standardwerte zurückverändern. Um die Bitrate für Audio-/Videoanrufe festzulegen, navigieren Sie zur Cisco Unified CM Administration- \> System- \> Region Information- \> Region. Die Standardwerte sind unten als Referenz dargestellt:
    
    |**Parameter**|**Empfohlene Einstellung**|
    |:-----|:-----|
    |Region  <br/> |Standard  <br/> |
    |Audiocodec-Präferenzliste  <br/> |Systemstandard  <br/> |
    |Maximale Audiobitrate  <br/> |64 KBit/s (G.722, G.711)  <br/> |
    |Maximale Sitzungsbitrate für Videoanrufe  <br/> |200000 KBit/s  <br/> |
    |Maximale Sitzungsbitrate  <br/> |2000000000 KBit/s  <br/> |
   
An diesem Punkt ist das CUCM-Videogateway für die Verwendung mit dem VIS konfiguriert. Die entsprechende Konfiguration muss auf jedem VTC erfolgen, den Sie integrieren möchten.
> [!NOTE]
> Um die Resilienz zu verbessern, sollten Sie dieses CUCM-Gateway so konfigurieren, dass es mit einem zweiten Video-Interoperabilitätsserver oder VIS-Pool funktioniert. Weitere Informationen finden Sie unter [Resilienzmechanismen.](../../plan-your-deployment/video-interop-server.md#resiliency)
  
## <a name="see-also"></a>Weitere Informationen

[Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server](configure-a-vtc-for-interoperation.md)
