---
title: Plan for Video Interop Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie planen, Skype for Business Server in Telekonferenzgeräte von Drittanbietern zu integrieren.'
ms.openlocfilehash: 3f42ea3545b7185f0d79999adc0af821d73e4bb8077f60cef2b0690a693aaea3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349817"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Plan for Video Interop Server in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, während Sie planen, Skype for Business Server in Telekonferenzgeräte von Drittanbietern zu integrieren.
  
Skype for Business Server ermöglicht ihnen jetzt die Integration in bestimmte VTC-Lösungen von Drittanbietern (Video Teleconferencing System). Die neue Serverrolle, die diese Interoperabilität von Videokonferenzen ermöglicht, ist der Video-Interoperabilitätsserver (VIDEO Interop Server, VIS), der derzeit als eigenständige Serverrolle implementiert ist, die nur für lokale Installationen verfügbar ist. Ein VIS fungiert als Vermittler zwischen einem Drittanbieter-Telekonferenzsystem und einer Skype for Business Server Bereitstellung. Für diese Version konzentriert sich VIS auf die Interoperabilität mit Cisco/Tandberg-Videosystemen. Lesen Sie diesen Artikel, um festzustellen, ob dieses Feature in Ihrer Skype for Business Server-Installation verwendet werden soll.
  
## <a name="device-interoperability"></a>Geräteinteroperabilität

Die Interoperabilität wird mit Cisco-VTCs getestet und unterstützt, die sich bei Cisco Unified Communications Manager (CallManager oder CUCM) Version 10.5 und TCP-SIP-Trunks registrieren, die zwischen CUCM und dem VIS eingerichtet sind.
  
Die derzeit unterstützten VTCs sind:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  Die Cisco-Softwareversion TC7.0.0 oder höher ist auf diesen Systemen erforderlich, damit die Integration mit Skype for Business Server wie erwartet funktioniert.
  
## <a name="sip-trunks"></a>SIP-Trunks

Der Video-Interoperabilität-Server funktioniert im SIP-Trunkmodus, in dem sich die VTCs weiterhin bei der vorhandenen Cisco-Infrastruktur registrieren , z. B. Cisco Call Manager (CUCM). Zwischen CUCM und dem VIS wird ein Video-SIP-Trunk definiert, sodass Anrufe zwischen den beiden Systemen weitergeleitet werden können. Es werden nur Anrufe über den SIP-Trunk vom VTC an den VIS unterstützt. Daher können sich VTCs in eine Skype for Business Konferenz einwählen (durch Wählen der Telefonnummer, die der automatischen Telefonzentrale für Anrufe zugeordnet ist), aber nicht gezogen und in die Konferenz abgelegt werden.
  
![Diagramm des VIS in SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Features

Diese Serverrolle bietet Folgendes:
  
- Konvertierung zwischen den H.264-Formaten, die von Drittanbieter-Videosystemen verwendet werden, und der Skype for Business Server Bereitstellung.
    
- Konvertierung eines einzelnen Videostreams mit einer bestimmten Auflösung von einem VTC in mehrere Simulcast-Streams mit unterschiedlichen Auflösungen für die Verwendung in der Skype for Business Server Bereitstellung. Diese Datenströme können an die AVMCU und dann an Skype for Business Server Endpunkte und andere Videosysteme gesendet werden, die unterschiedliche Auflösungen angefordert haben. Diese Konvertierung wird auch verwendet, wenn das Videosystem eines Drittanbieters an einer Skype for Business A/V-Telefonkonferenz beteiligt ist. Sobald der Transcodierungsgrenzwert auf einem bestimmten VIS-Server erreicht ist, erhalten alle folgenden Anforderungen für unterschiedliche Auflösungen nur einen Datenstrom mit der niedrigsten Auflösung. 
    
- Unterstützung für einen Video-SIP-Trunk zwischen dem CUCM-Gateway und einem Skype for Business Server Video-Interoperabilität-Server; VTCs registrieren sich weiterhin beim Cisco-Gateway und initiieren Anrufe an die Skype for Business-Bereitstellung über das Gateway. Anrufe werden vom Gateway an den Skype for Business Video-Interoperabilitätsserver über den Video-SIP-Trunk weitergeleitet.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten Videosystem, um von diesem System aus an einer offenen oder geschlossenen Konferenz teilzunehmen. Dieser Anruf durchläuft den Video-SIP-Trunk.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten Videosystem zum Aufrufen eines Skype for Business Clients. Der Anruf durchläuft den SIP-Trunk.
    
- Unterstützung für mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.
    
## <a name="known-limitations"></a>Bekannte Einschränkungen

Für diese Serverrolle gelten die folgenden Einschränkungen:
  
- Neue Anrufe von der Skype for Business-Bereitstellung an die VTCs über den Video-SIP-Trunk werden nicht unterstützt. . Dies bedeutet, dass nur neue Anrufe von den VTCs in die Skype for Business Bereitstellung über den Video-SIP-Trunk unterstützt werden. Die Anwesenheit für das unterstützte Videosystem steht dem VIS nicht über den Video-SIP-Trunk zur Verfügung. 
    
- Für den Video-SIP-Trunkmodus wird nur ein eigenständiger VIS-Pool unterstützt.
    
-  TLS + SRTP oder TCP + RTP wird für die Kommunikation zwischen VTC und VIS über den Video-SIP-Trunk unterstützt.
    
- Die Anwendungsfreigabe wird nicht unterstützt. Ein Skype for Business Benutzer im Konferenzraum muss an der Skype for Business Konferenz teilnehmen (z. B. über einen Laptop) und die Bildschirme für die App-Freigabe auf einem der kostenlosen Monitore im Konferenzraum anzeigen, der nicht mit dem VTC verknüpft ist.
    
- Die Möglichkeit für einen VTC, über den VIS an einer Verbundbesprechung teilzunehmen, wird nicht unterstützt.
    
- Die Möglichkeit für einen VTC, über vis an einer Onlinebesprechung teilzunehmen, wird nicht unterstützt.
    
- Anrufe von einem VTC an das PSTN über den VIS werden nicht unterstützt.
    
- Anrufe vom PSTN an einen VTC über den VIS werden nicht unterstützt.
    
## <a name="resiliency-mechanisms"></a>Resilienzmechanismen
<a name="resiliency"> </a>

Der VIS unterstützt eingehende Anrufe von einem CUCM, die über einen Video-SIP-Trunk übertragen werden. Da es möglich ist, die Konnektivität entweder upstream oder downstream zu verlieren, sollten Sie für eine stabile Resilienz beide Möglichkeiten in Betracht ziehen:
  
1. **VIS-Poolfailover** Wenn der Vis-Hauptpool, auf den das Videogateway verweist, ausgefallen ist, ist eine Wiederherstellung möglich, wenn das Videogateway Trunks für zwei (oder mehr) VIS-Pools definiert hat. Wenn das Videogateway feststellt, dass es keine Anrufe an den primären VIS-Pool tätigen kann, leitet es die Anrufe einfach an einen sekundären VIS-Pool weiter.
    
     ![Diagramm des VIS-Poolfailovers](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Ein bestimmter VIS-Pool kann Trunks zu mehreren Gateways haben, aber normalerweise kann ein bestimmtes Gateway keine Trunks zu mehreren VIS-Pools haben. Daher muss ein Trick ausgeführt werden, um dieses Failover zu unterstützen: Definieren Sie 2 FDQNs in DNS, die in die gleiche IP-Adresse eines Videogateways aufgelöst werden. Stellen Sie jeden FQDN als separates Videogateway im Topologiedokument dar, wobei jedes Videogateway über einen Trunk zu einem anderen VIS-Pool verfügt und eine Wiederherstellung jetzt möglich ist. (Wenn TLS verwendet wird, müssen die mehreren Namen im SAN des Videogatewayzertifikats enthalten sein.)
    
    > [!NOTE]
    > Der VIS lässt nur eingehende Anrufe von Gateways zu, die im Topologiedokument konfiguriert sind. 
  
2. **Front-End-Failover** Wenn ein VIS-Pool einen Anruf von CUCM empfängt, aber seinen primären Next-Hop-Registrierungsstellen- oder Front-End-Pool nicht erreichen kann, werden Anrufe an einen Front-End-Sicherungspool weitergeleitet.
    
     ![Diagramm des Front-End-Failovers](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Der VIS verfolgt den Status des primären Front-End-Pools und des Sicherungs-Front-End-Pools (die Einstellung befindet sich in der Sicherungseinstellung für den Registrierungsstellendienst im Topologiedokument). Es sendet Optionsumfragen einmal pro Minute an beide Pools, und wenn es fünf aufeinander folgende Fehler gibt, geht der VIS davon aus, dass ein bestimmter Front-End-Pool ausgefallen ist. Wenn der primäre Front-End-Pool als "ausgefallen" gekennzeichnet ist und eine verfügbare konfigurierte Sicherung vorhanden ist, sendet der VIS neue Aufrufe vom Gateway an den Front-End-Sicherungspool. Sobald der primäre Front-End-Pool zurückkommt, setzt der VIS die Verwendung des primären Front-End-Pools für neue Anrufe fort.
    
    Der VIS implementiert auch einen 10-Sekunden-Timer für Anrufe vom Video-SIP-Trunk. Wenn der primäre Next-Hop-Front-End-Pool für einen Anruf vom Video-SIP-Trunk verwendet wurde und der primäre Next-Hop-Front-End-Pool nicht mit einer SIP-Nachricht (einschließlich 100 Trying) an die einladung reagiert hat, die innerhalb dieses Timerwerts gesendet wurde, sollte der Nächste-Hop-Proxy für den Anruf getestet werden, wenn konfiguriert. 
    
    > [!NOTE]
    > Wenn der nächste Hop für die Sicherung zuerst ausprobiert wurde, wird der primäre Hop nicht als Nächstes ausprobiert. 
  
    Der Administrator kann auch den Windows PowerShell Failoverbefehl verwenden, um zu erzwingen, dass der VIS den Sicherungs-Front-End-Pool verwendet, z. B. wenn wartung auf dem primären Front-End-Pool ausgeführt werden muss.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Koexistenz von VoIP- und Videotrunks mit demselben Gatewaypeer
<a name="resiliency"> </a>

Skype for Business Server unterstützt die Verwendung des gleichen Gatewaypeers für VoIP- und Video-SIP-Trunks. Dieselbe CUCM-Bereitstellung kann also VoIP-SIP-Trunks an den Vermittlungsserver und Video-SIP-Trunks für den VIS aufweisen.
  
- Ein PSTN-Gateway muss mit einem bestimmten FQDN im Topologiedokument für die VoIP-SIP-Trunks definiert werden.
    
- Der Peer zum PSTN-Gateway ist der Vermittlungsserver.
    
- Mehrere VoIP-Trunks können definiert werden, die bei Bedarf von einem PSTN-Gateway bis zu mehreren Vermittlungsserverpools umfassen.
    
- Ein Videogateway muss im Topologiedokument für den Video-SIP-Trunk mit dem gleichen FQDN wie für das PSTN-Gateway definiert werden.
    
- Der Peer zum Videogateway ist der VIS.
    
- Ein einzelner Videotrunk kann von einem Videogateway zu einem bestimmten VIS-Pool definiert werden.
    
- CUCM muss so konfiguriert werden, dass Anrufe korrekt über den VoIP-Trunk und nicht über den Videotrunk weitergeleitet werden. Beispielsweise kann ein spezielles Wählpräfix für die Auswahl aus dem VTC verwendet werden. CUCM könnte dieses Wählpräfix Anrufen an den VIS zuordnen, und entsprechende Übersetzungsregeln würden dieses Präfix aus der SIP-Einladung an den VIS entfernen.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Koexistenz des VIS in der Skype for Business-Version mit früheren Versionen von Lync
<a name="resiliency"> </a>

DER VIS kann nur im Rahmen Skype for Business Bereitstellung bereitgestellt werden. Sie kann mit Lync 2013-Konferenzen und -Clients zusammenarbeiten, die Teil einer vorhandenen Bereitstellung sind. In diesen Fällen muss der VIS-Pool Teil einer Skype for Business Bereitstellung sein, die einen Registrierungsstellen-/FE-Pool enthält, der der nächste Hop für den VIS-Pool ist.
  
Der VIS unterstützt keine Transcodierung zwischen RTV und H.264. Es gibt keine Videointeroperabilität zwischen Pre-Lync 2013-Clients und VTC-Teilnehmern in einer Konferenz.
  
Wenn Vor-Lync 2013-Clients in einer Konferenz vorhanden sind, werden mobile Clients mit RTV gesendet, was dazu führt, dass VTCs kein Video empfangen, wenn der mobile Client zum dominanten Lautsprecher wird.
  
Damit Lync 2013 ordnungsgemäß mit dem VIS funktioniert, der Teil einer Skype for Business Bereitstellung ist, benötigt Lync 2013 das entsprechende CU, um das Upgrade des Lync 2013-Clients, der CAA und der AVMCU für die Arbeit mit dem VIS durchzuführen.
  
Die Interoperabilität des VIS mit Lync 2013 und Skype for Business Desktopclients wurde getestet und wird unterstützt.
  
Interoperabilität des VIS mit Nicht-Desktop (Android, Ipad, Iphone, Windows Phone, LMX usw.) Skype for Business Clients, die von den entsprechenden Apps Store zum Zeitpunkt der VIS-Veröffentlichung verfügbar sind, wurden getestet und werden unterstützt.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Wiederherstellung nach Paketverlust über FEC
<a name="resiliency"> </a>

FEC kann aktiviert werden, um die Wiederherstellung nach Paketverlust zu unterstützen. Wenn diese Einstellung aktiviert ist, wird 50 % mehr Videobandbreite in VIS-zu-VTC-Richtung verwendet.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS-Größenanpassung und Transcodierungskosten
<a name="resiliency"> </a>

Das Transcodieren der einzelnen Videostreams von Cisco VTC in mehrere Simulcast-Streams verwendet CPU-Kapazität. Ungefähr 16 VTCs können ihre Videos transcodieren (vorausgesetzt, dass ein 720p-Videostream von jedem VTC in 3 separate Simulcast-Streams mit 720p, 360p und 180p transcodiert wird) in einem einzelnen VIS, der auf dem Äquivalent der empfohlenen LYNC 2013-FE-Plattform ausgeführt wird. Wenn die Transcodierung deaktiviert ist, wird dadurch die VIS-CPU gespart. Das vom VIS vom VTC angeforderte Videobild ist jedoch die niedrigste allgemeine Auflösung, um alle Empfänger auf der Skype for Business Seite zu erfüllen. Beachten Sie, dass die Transcodierung auch bei deaktivierter Transcodierung aktiviert werden kann, wenn Skype for Business Clients bestimmte niedrige Auflösungen anfordern, die VTCs nicht senden können.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Anrufverteilung vom Videogateway zum VIS
<a name="resiliency"> </a>

Die Verteilung erfolgt über einen der CUCM-Verteilungsmechanismen:
  
- Dynamische Verwendung von DNS.
    
- Auf der CUCM-Seite können Sie einzelne Trunks definieren, wobei jeder Trunk auf einem anderen Server im VIS-Pool beendet wird. CUCM leitet Anrufe über die verschiedenen Trunks weiter.
    
## <a name="no-hybrid-interoperability"></a>Keine Hybridinteroperabilität
<a name="resiliency"> </a>

Die Unterstützung für VTCs, die über den lokalen VIS an Onlinebesprechungen teilnehmen, ist nicht Teil Skype for Business.
  
## <a name="no-federation-support"></a>Keine Verbundunterstützung
<a name="resiliency"> </a>

Die Unterstützung für VTCs, die über den VIS an Verbundbesprechungen teilnehmen, ist nicht Teil Skype for Business.
  
## <a name="see-also"></a>Siehe auch
<a name="resiliency"> </a>

[Bereitstellen des Video-Interoperabilität-Servers in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
