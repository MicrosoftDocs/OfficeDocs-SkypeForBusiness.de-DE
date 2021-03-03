---
title: Planen des Videointeopservers in Skype for Business Server
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
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831945"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planen des Videointeopservers in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, während Sie planen, Skype for Business Server in Telekonferenzgeräte von Drittanbietern zu integrieren.
  
Skype for Business Server ermöglicht ihnen jetzt die Integration mit bestimmten VTC(Video Teleconferencing System)-Lösungen von Drittanbietern. Die neue Serverrolle, die diese Videokonferenzinteroperabilität ermöglicht, ist der Video-Interoperabilität-Server (VIS), der derzeit als eigenständige Serverrolle implementiert ist, die nur für lokale Installationen verfügbar ist. Ein VIS fungiert als Vermittler zwischen einem Drittanbietertelekonferenzsystem und einer Skype for Business Server-Bereitstellung. Für diese Version konzentriert sich der VIS auf die Interoperabilität mit Cisco/Tandberg-Videosystemen. Lesen Sie diesen Artikel, um zu bestimmen, ob sie in Ihrer Skype for Business Server-Installation verwendet werden soll.
  
## <a name="device-interoperability"></a>Geräteinteroperabilität

Die Interoperabilität wird mit Cisco VTCs getestet und unterstützt, die sich bei Cisco Unified Communications Manager (CallManager oder CUCM) Version 10.5 registrieren, und TCP-SIP-Trunks, die zwischen CUCM und dem VIS eingerichtet sind.
  
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
>  Die Cisco-Softwareversion TC7.0.0 oder höher ist auf diesen Systemen erforderlich, damit die Integration in Skype for Business Server wie erwartet funktioniert.
  
## <a name="sip-trunks"></a>SIP-Trunks

Der Video Interop Server arbeitet im SIP-Trunk-Modus, in dem sich die VTCs weiterhin bei der vorhandenen Infrastruktur von Cisco registrieren, z. B. Cisco Call Manager (CUCM). Ein Video-SIP-Trunk ist zwischen CUCM und dem VIS definiert, sodass Anrufe zwischen den beiden Systemen geroutet werden können. Nur Anrufe über den SIP-Trunk vom VTC an den VIS werden unterstützt. Auf diese Weise können VTCs sich in eine Skype for Business-Konferenz einwählen (indem sie die telefonnummer wählen, die der automatischen Telefonanrufautomatie zugeordnet ist), können jedoch nicht gezogen und in die Konferenz abgelegt werden.
  
![Diagramm des VIS in SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Features

Diese Serverrolle bietet:
  
- Konvertierung zwischen den H.264-Formaten, die von Videosystemen von Drittanbietern verwendet werden, und der Skype for Business Server-Bereitstellung.
    
- Konvertierung eines einzelnen Videostreams mit einer bestimmten Auflösung von einem VTC in mehrere Simulcaststreams mit unterschiedlichen Auflösungen zur Verwendung in der Skype for Business Server-Bereitstellung. Diese Datenströme können an die AVMCU und dann an Skype for Business Server-Endpunkte und andere Videosysteme gesendet werden, die unterschiedliche Auflösungen angefordert haben. Diese Konvertierung wird auch verwendet, wenn das Videosystem eines Drittanbieters an einem Skype for Business A/V-Konferenzanruf beteiligt ist. Sobald der Transcodierungsgrenzwert auf einem bestimmten VIS-Server erreicht ist, erhalten alle folgenden Anforderungen für unterschiedliche Auflösungen nur einen Stream mit der niedrigsten Auflösung. 
    
- Unterstützung für einen Video-SIP-Trunk zwischen dem #A0 und einem Skype for Business Server Video Interop Server; VTCs registrieren sich weiterhin beim Cisco-Gateway und initiieren Anrufe an die Skype for Business-Bereitstellung über das Gateway. Anrufe werden vom Gateway an den Skype for Business Video Interop Server über den Video-SIP-Trunk geroutet.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten Videosystem zum Wählen aus diesem System, um an einer offenen oder geschlossenen Konferenz teil zu nehmen. Dieser Anruf durchläuft den Video-SIP-Trunk.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten Videosystem zum Anrufen eines Skype for Business-Clients. Der Anruf durchläuft den SIP-Trunk.
    
- Unterstützung für die Mid-Call-Steuerung von der Skype for Business Server-Seite oder vom unterstützten VTC-System für Point-to-Point- und Multipoint-Anrufe, einschließlich Stummschalten/Stummschalten von Audio, Anhalten/Fortsetzen von Videos, Sperren von Videos und Halten/Un-Halten von Anrufen.
    
## <a name="known-limitations"></a>Bekannte Einschränkungen

Für diese Serverrolle gelten die folgenden Einschränkungen:
  
- Neue Anrufe von der Skype for Business-Bereitstellung an die VTCs über den Video-SIP-Trunk werden nicht unterstützt. . Dies bedeutet, dass nur neue Anrufe von den VTCs in die Skype for Business-Bereitstellung über den Video-SIP-Trunk unterstützt werden. Anwesenheit für das unterstützte Videosystem ist nicht über den Video-SIP-Trunk für den VIS verfügbar. 
    
- Nur ein eigenständiger VIS-Pool wird für den Video-SIP-Trunkmodus unterstützt.
    
-  TLS + SRTP oder TCP + RTP wird für die Kommunikation zwischen VTC und VIS über den Video-SIP-Trunk unterstützt.
    
- Die Anwendungsfreigabe wird nicht unterstützt. Ein Skype for Business-Benutzer im Konferenzraum muss an der Skype for Business-Konferenz teilnehmen (z. B. über einen Laptop) und die Bildschirme für die App-Freigabe auf einem der kostenlosen Monitore im Konferenzraum anzeigen, der nicht dem VTC zugeordnet ist.
    
- Die Möglichkeit, dass ein VTC über den VIS an einer Verbund besprechung teilnehmen kann, wird nicht unterstützt.
    
- Die Möglichkeit, dass ein VTC über den VIS an einer Online besprechung teilnehmen kann, wird nicht unterstützt.
    
- Anrufe von einem VTC an das PSTN über den VIS werden nicht unterstützt.
    
- Anrufe aus dem PSTN an ein VTC über den VIS werden nicht unterstützt.
    
## <a name="resiliency-mechanisms"></a>Ausfallsicherheitsmechanismen
<a name="resiliency"> </a>

Der VIS unterstützt eingehende Anrufe von einem CUCM, die über einen Video-SIP-Trunk durchgeführt werden. Es ist möglich, die Konnektivität entweder vor- oder nachgelagert zu verlieren, daher sollten Sie für eine robuste Resilienz beide Möglichkeiten in Betracht ziehen:
  
1. **Failover des VIS-Pools** Wenn der Haupt-VIS-Pool, auf den das Videogateway verweist, aus ist die Wiederherstellung möglich, wenn das Videogateway Trunks zu zwei (oder mehr) VIS-Pools definiert hat. Wenn das Videogateway feststellt, dass keine Anrufe an den primären VIS-Pool möglich sind, leitet es die Anrufe einfach an einen sekundären VIS-Pool weiter.
    
     ![Diagramm des Failovers des VIS-Pools](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Ein bestimmter VIS-Pool kann Trunks zu mehreren Gateways haben, aber normalerweise kann ein bestimmtes Gateway keine Trunks zu mehreren VIS-Pools haben. Daher muss ein Trick zur Unterstützung dieses Failovers ausgeführt werden: Definieren Sie 2 FDQNs in DNS, die in dieselbe IP-Adresse eines Videogateways aufgelöst werden. Stellen Sie jeden FQDN als separates Videogateway im Topologiedokument dar, wobei jedes Videogateway über einen Trunk zu einem anderen VIS-Pool verfügt, und die Wiederherstellung jetzt möglich ist. (Wenn TLS verwendet wird, müssen die mehreren Namen im SAN des Videogatewayzertifikats enthalten sein.)
    
    > [!NOTE]
    > Der VIS lässt nur eingehende Anrufe von Gateways zu, die im Topologiedokument konfiguriert sind. 
  
2. **Front-End-Failover** Wenn ein VIS-Pool einen Anruf von CUCM empfängt, aber den primären Registrierungspool des nächsten Hops oder Front-End-Pools nicht erreichen kann, werden Anrufe an einen Front-End-Sicherungspool geroutet.
    
     ![Diagramm des Front-End-Failovers](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Der VIS verfolgt den Status des primären Front-End-Pools und des Sicherungs-Front-End-Pools (die Einstellung befindet sich in der Sicherungseinstellung für den Registrierungsdienst im Topologiedokument). Es sendet Optionsabfragen einmal pro Minute an beide Pools, und wenn es fünf aufeinander folgende Fehler gibt, geht der VIS davon aus, dass ein bestimmter Front-End-Pool aus ist. Wenn der primäre Front-End-Pool als nicht verfügbar gekennzeichnet ist und eine konfigurierte Sicherung verfügbar ist, sendet der VIS neue Anrufe vom Gateway an den Front-End-Sicherungspool. Sobald der primäre Front-End-Pool wieder da ist, wird der VIS den primären Front-End-Pool für neue Anrufe wieder verwenden.
    
    Der VIS implementiert außerdem einen 10-Sekunden-Timer für Anrufe vom Video-SIP-Trunk. Wenn der primäre Front-End-Pool für den nächsten Hop für einen Anruf vom Video-SIP-Trunk verwendet wurde und der primäre Front-End-Pool des nächsten Hops nicht mit einer sip-Nachricht (einschließlich 100 Trying) an die einladung, die innerhalb dieses Zeitgeberwerts gesendet wurde, antwortet, sollte der Sicherungsproxy für den nächsten Hop für den Anruf ausprobiert werden, wenn er konfiguriert ist. 
    
    > [!NOTE]
    > Wenn der nächste Sicherungshop zuerst ausprobiert wurde, wird der primäre nicht als Nächstes ausprobiert. 
  
    Der Administrator könnte auch den Windows PowerShell-Failoverbefehl verwenden, um zu erzwingen, dass der VIS den Front-End-Sicherungspool verwendet, z. B. wenn Wartungsarbeiten am primären Front-End-Pool ausgeführt werden müssen.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Koexistenz von Sprach- und Video trunks auf demselben Gateway peer
<a name="resiliency"> </a>

Skype for Business Server unterstützt die Verwendung desselben Gateway-Peers durch Sprach- und Video-SIP-Trunks. Die gleiche BEREITSTELLUNG von CUCM könnte also Voice-SIP-Trunks zum Vermittlungsserver und Video-SIP-Trunks zum VIS haben.
  
- Ein PSTN-Gateway muss mit einem bestimmten FQDN im Topologiedokument für die Voice-SIP-Trunks definiert werden.
    
- Der Peer zum PSTN-Gateway ist der Vermittlungsserver.
    
- Bei Bedarf können mehrere Voice trunks definiert werden, die von einem PSTN-Gateway zu mehreren Vermittlungsserverpools reicht.
    
- Ein Videogateway muss im Topologiedokument für den Video-SIP-Trunk mit demselben FQDN wie für das PSTN-Gateway definiert werden.
    
- Der Peer zum Videogateway ist VIS.
    
- Ein einzelner Video trunk kann von einem Videogateway zu einem bestimmten VIS-Pool definiert werden.
    
- CUCM muss so konfiguriert werden, dass Anrufe ordnungsgemäß über den Sprach- und video trunk geroutet werden. Beispielsweise kann ein spezielles Wählpräfix verwendet werden, wenn Sie aus dem VTC wählen. CUCM könnte dieses Wählpräfix Anrufen an den VIS zuordnen, und entsprechende Übersetzungsregeln würden dieses Präfix aus der SIP-Einladung an den VIS nehmen.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Koexistenz des VIS in der Skype for Business Release mit früheren Versionen von Lync
<a name="resiliency"> </a>

Der VIS kann nur im Rahmen der Skype for Business-Bereitstellung bereitgestellt werden. Sie kann mit Lync 2013-Konferenzen und Clients zusammenarbeiten, die Teil einer vorhandenen Bereitstellung sind. In diesen Fällen muss der VIS-Pool Teil einer Skype for Business-Bereitstellung sein, die einen Registrierungs-/FE-Pool enthält, der der nächste Hop für den VIS-Pool ist.
  
Der VIS unterstützt keine Transcodierung zwischen RTV und H.264. Es gibt keine Videointeroperabilität zwischen Clients vor Lync 2013 und VTC-Teilnehmern an einer Konferenz.
  
Die Verwendung von Clients vor Lync 2013 in einer Konferenz führt dazu, dass mobile Clients rtV verwenden, was dazu führt, dass VTCs kein Video empfangen, wenn der mobile Client zum dominanten Lautsprecher wird.
  
Damit Lync 2013 ordnungsgemäß mit dem VIS funktioniert, der Teil einer Skype for Business-Bereitstellung ist, muss für Lync 2013 das entsprechende KU angewendet werden, mit dem der Lync 2013-Client, die Zertifizierungsstelle und die AVMCU für die Zusammenarbeit mit dem VIS aktualisiert werden.
  
Die Interoperabilität des VIS mit Lync 2013- und Skype for Business-Desktopclients wurde getestet und wird unterstützt.
  
Interoperabilität des VIS mit Nicht-Desktop (Android, Ipad, IPhone, Windows Phone, LMX usw.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Wiederherstellung nach Paketverlust über FEC
<a name="resiliency"> </a>

FEC kann aktiviert werden, um die Wiederherstellung nach Paketverlusten zu unterstützen. Wenn diese Aktivierte aktiviert ist, wird 50 % mehr Videobandbreite in Vis-to-VTC-Richtung verwendet.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Größen- und Transcodierungskosten des VIS
<a name="resiliency"> </a>

Die Transcodierung der einzelnen Videostreams vom Cisco VTC zu mehreren Simulcaststreams nutzt die CPU-Kapazität. Ca. 16 VTCs können ihr Video transcodieren (vorausgesetzt, ein 720p-Videostream von jedem VTC wird in 3 separate Simulcaststreams mit 720p, 360p und 180p transcodiert) in einem einzelnen VIS, der auf dem Äquivalent der empfohlenen Lync 2013-FE-Plattform ausgeführt wird. Wenn die Transcodierung deaktiviert ist, wird dadurch die VIS-CPU gespeichert. Das vom VIS vom VTC angeforderte Videobild ist jedoch die niedrigste allgemeine Auflösung, um alle Empfänger auf der Skype for Business-Seite zu erfüllen. Beachten Sie, dass auch bei der Transcodierung die Transcodierung aktiviert werden kann, wenn Skype for Business-Clients bestimmte niedrige Auflösungen anfordern, die vtCs nicht senden können.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Anrufverteilung vom Videogateway an den VIS
<a name="resiliency"> </a>

Die Verteilung erfolgt über einen der CUCM-Verteilungsmechanismen:
  
- Dynamische Verwendung von DNS.
    
- Auf der CuCM-Seite können Sie einzelne Trunks definieren, wobei jeder Trunk auf einem anderen Server im VIS-Pool endet. CUCM führt Anrufe über die verschiedenen Trunks aus.
    
## <a name="no-hybrid-interoperability"></a>Keine Hybridinteroperabilität
<a name="resiliency"> </a>

Unterstützung für VTCs, die über den lokalen VIS an Onlinebesprechungen teilnehmen, ist nicht Teil von Skype for Business.
  
## <a name="no-federation-support"></a>Keine Verbundunterstützung
<a name="resiliency"> </a>

Die Unterstützung für VTCs, die über den VIS an Verbundbesprechungen teilnehmen, ist nicht Teil von Skype for Business.
  
## <a name="see-also"></a>Siehe auch
<a name="resiliency"> </a>

[Bereitstellen des Videointeopservers in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
