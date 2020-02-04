---
title: Planen des Video-Interop-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie planen, Skype for Business Server mit Teleconferencing-Geräten von Drittanbietern zu integrieren.'
ms.openlocfilehash: 5531fd60cc2aa28202903fcc4392fe7830bcdfa0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684188"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planen des Video-Interop-Servers in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, während Sie planen, Skype for Business Server mit Teleconferencing-Geräten von Drittanbietern zu integrieren.
  
Skype for Business Server ermöglicht Ihnen nun die Integration in bestimmte Drittanbieter-Lösungen für VTC (Video Teleconferencing System). Die neue Serverrolle, die diese Videokonferenz Interoperabilität ermöglicht, ist der Video-Interop-Server (VIS), der derzeit als eigenständige Serverrolle implementiert ist, die nur für lokale Installationen verfügbar ist. Ein VIS fungiert als Vermittler zwischen einem Drittanbieter-Konferenzsystem und einer Skype for Business Server-Bereitstellung. Bei dieser Version konzentriert sich der VIS auf die Interoperabilität mit Videosystemen von Cisco/Tandberg. Lesen Sie diesen Artikel, um festzustellen, ob Sie diese Funktion in Ihrer Skype for Business Server-Installation verwenden möchten.
  
## <a name="device-interoperability"></a>Interoperabilität von Geräten

Interoperation wird getestet und unterstützt mit Cisco VTCs, die sich bei Cisco Unified Communications Manager (CallManager oder CUCM), Version 10,5 und TCP-SIP-Stämmen, die zwischen CUCM und dem VIS eingerichtet sind, registrieren.
  
Folgende Videotelekonferenzsysteme werden zurzeit unterstützt:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  Cisco Software Release TC 7.0.0 oder höher ist auf diesen Systemen erforderlich, damit die Integration in Skype for Business Server wie erwartet funktioniert.
  
## <a name="sip-trunks"></a>SIP-Trunks

Der Video-Interop-Server funktioniert im SIP-Trunk-Modus, in dem sich die VTCs weiterhin bei der vorhandenen Cisco-Infrastruktur registrieren, beispielsweise Cisco Call Manager (CUCM). Ein Video-SIP-Trunk ist zwischen CUCM und dem VIS definiert, sodass Anrufe zwischen den beiden Systemen weitergeleitet werden können. Nur Anrufe über den SIP-Trunk vom Videotelekonferenzsystem (VTC) an den VIS werden unterstützt. Auf diese Weise kann sich VTCs in eine Skype for Business-Konferenz einwählen (durch Wählen der Telefonnummer, die mit der automatischen Anruf Automatik verbunden ist), kann aber nicht in die Konferenz gezogen und abgelegt werden.
  
![Diagramm von VIS in SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Funktionen

Diese Serverrolle bietet Folgendes:
  
- Konvertierung zwischen den H. 264-Formaten, die von Videosystemen von Drittanbietern und der Skype for Business Server-Bereitstellung verwendet werden.
    
- Konvertierung eines einzelnen Videostreams bei einer gegebenen Auflösung von einem VTC in mehrere Livestreams verschiedener Auflösungen zur Verwendung in der Skype for Business Server-Bereitstellung. Diese Streams können an die AVMCU und dann an Skype for Business Server-Endpunkte und andere Videosysteme gesendet werden, die unterschiedliche Auflösungen angefordert haben. Diese Konvertierung wird auch verwendet, wenn das Videosystem eines Drittanbieters an einem Skype for Business a/V-Konferenzanruf teilnimmt. Sobald die Transcodierungs Grenze in einem bestimmten VIS-Server erreicht ist, erhalten alle folgenden Anforderungen für verschiedene Auflösungen nur einen Datenstrom mit der niedrigsten Auflösung. 
    
- Unterstützung für einen Video-SIP-Trunk zwischen dem CUCM-Gateway und einem Skype for Business Server-Video-Interop-Server; VTCs registrieren Sie sich weiterhin beim Cisco-Gateway, und initiieren Sie Anrufe an die Skype for Business-Bereitstellung über das Gateway. Anrufe werden vom Gateway zum Skype for Business-Video-Interop-Server über den Video-SIP-Trunk weitergeleitet.
    
- Unterstützung eines Benutzers in einem Konferenzraum mit einem unterstützten Videosystem, sodass von diesem System aus gewählt werden kann, um an einer offenen oder geschlossenen Konferenz teilzunehmen. Dieser Anruf durchläuft den Video-SIP-Trunk.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten Videosystem zum Anrufen eines Skype for Business-Clients. Der Anruf durchläuft den SIP-Trunk.
    
- Unterstützung für die Mid-Call-Steuerung von der Skype for Business-Server Seite oder vom unterstützten VTC-System für Punkt-zu-Punkt-und Multipoint-Anrufe, einschließlich Stummschaltung/Stummschaltung von Audio, Pausieren/Fortsetzen des Videos, Sperren von Video und halten/UN-halten-Anruf.
    
## <a name="known-limitations"></a>Bekannte Einschränkungen

Diese Serverrolle unterliegt den folgenden Einschränkungen:
  
- Neue Anrufe aus der Skype for Business-Bereitstellung in die VTCs über den Video-SIP-Trunk werden nicht unterstützt. . Das bedeutet, dass nur neue Anrufe vom VTCs in die Skype for Business-Bereitstellung über den Video-SIP-Trunk unterstützt werden. Der Anwesenheitsstatus für das unterstützte Videosystem steht nicht über den Video-SIP-Trunk des VIS zur Verfügung. 
    
- Es wird nur ein eigenständiger VIS-Pool für den Video-SIP-Trunkmodus unterstützt.
    
-  TLS + SRTP oder TCP + RTP wird für die Kommunikation zwischen dem VTC und dem VIS über den Video-SIP-Trunk unterstützt.
    
- Die Anwendungsfreigabe wird nicht unterstützt. Ein Skype for Business-Benutzer im Konferenzraum muss an der Skype for Business-Konferenz teilnehmen (beispielsweise über einen Laptop) und die APP-Freigabe Bildschirme auf einem der kostenlosen Monitore im Konferenzraum anzeigen, der nicht dem VTC zugeordnet ist.
    
- Ein VTC kann nicht über einen VIS an einer Besprechung im Partnerverbund teilnehmen.
    
- Ein VTC kann nicht über einen VIS an einer Onlinebesprechung teilnehmen.
    
- Anrufe von einem VTC an die PSTN über den VIS werden nicht unterstützt.
    
- Anrufe von der PSTN an einen VTC über den VIS werden nicht unterstützt.
    
## <a name="resiliency-mechanisms"></a>Flexibilitätsmechanismen
<a name="resiliency"> </a>

Das VIS unterstützt eingehende Anrufe von einem CUCM, die über einen Video-SIP-Trunk übertragen werden. Es ist möglich, die Konnektivität entweder Upstream oder Downstream zu verlieren, daher sollten Sie für robuste Stabilität beide Möglichkeiten in Frage stellen:
  
1. **VIS-Pool-Failover** Wenn der Haupt-VIS-Pool, auf den das Video Gateway verweist, nach unten zeigt, ist eine Wiederherstellung möglich, wenn das Video Gateway Trunks zu zwei (oder mehr) VIS-Pools definiert hat. Wenn das Video-Gateway feststellt, dass es keine Anrufe an den primären VIS-Pool durchführen kann, werden die Anrufe einfach an einen sekundären VIS-Pool weitergeleitet.
    
     ![Diagramm eines VIS-Poolfailover](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    In einem bestimmten VIS-Pool können Trunks zu mehreren Gateways vorhanden sein, aber normalerweise kann ein bestimmtes Gateway keine Trunks zu mehreren VIS-Pools aufweisen, daher muss ein Trick zur Unterstützung dieses Failovers ausgeführt werden: definieren Sie 2 FDQNs in DNS, die in die gleiche IP-Adresse eines Video Gateways aufgelöst werden. Stellen Sie jeden FQDN als separates Video Gateway im Topologie-Dokument dar, in dem die einzelnen Video Gateways einen trunk zu einem anderen VIS-Pool aufweisen, und die Wiederherstellung ist nun möglich. (Wenn TLS verwendet wird, müssen sich die verschiedenen Namen im San des Video Gateway-Zertifikats befinden.)
    
    > [!NOTE]
    > VIS gestattet nur eingehende Anrufe von Gateways, die im Topologiedokument konfiguriert sind. 
  
2. **Front-End-Failover** Wenn ein VIS-Pool einen Anruf von CUCM erhält, aber seine primäre Registrierungsstelle für den nächsten Hop oder den Front-End-Pool nicht erreichen kann, werden Anrufe an einen Backup-Front-End-Pool weitergeleitet.
    
     ![Diagramm eines Front-End-Failover](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Das VIS verfolgt den Status des primären Front-End-Pools und des zugehörigen Backup-Front-End-Pools (die Einstellung finden Sie in der Backup-Einstellung für den Registrierungsdienst im Topologie-Dokument). Sie sendet einmal pro Minute Wahlmöglichkeiten an beide Pools, und wenn fünf aufeinanderfolgende Fehler auftreten, geht das VIS davon aus, dass ein bestimmter Front-End-Pool ausgefallen ist. Wenn der primäre Front-End-Pool als "unten" gekennzeichnet ist und eine verfügbare konfigurierte Sicherung vorhanden ist, sendet das VIS neue Anrufe vom Gateway zum Backup-Front-End-Pool. Sobald der primäre Front-End-Pool zurückkommt, wird das VIS für neue Anrufe wieder mit dem primären Front-End-Pool fortgesetzt.
    
    Der VIS implementiert außerdem einen 10-Sekunden-Timer für Anrufe vom Video-SIP-Trunk. Wenn der primäre Next-Hop-Front-End-Pool für einen Anruf vom Video-SIP-Trunk verwendet wurde und der primäre Front-End-Pool des nächsten Hop nicht mit einigen SIP-Nachrichten (einschließlich 100) an die an ihn gesendete Einladung innerhalb dieses Timer-Werts antwortete, wird der Backup-Proxy für den nächsten Hop für den Anruf s oft wird bei der Konfiguration versucht. 
    
    > [!NOTE]
    > Wenn es zuerst mit dem Sicherungspool für den nächsten Hop versucht wurde, wird der primäre Pool anschließend nicht mehr ausprobiert. 
  
    Der Administrator kann auch den Windows PowerShell-Failoverbefehl verwenden, um den VIS zu zwingen, den Sicherungs-Front-End-Pool zu verwenden, beispielsweise wenn Wartungsarbeiten am primären Front-End-Pool durchgeführt werden müssen.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Koexistenz von Voice- und Videotrunks für denselben Gatewaypeer
<a name="resiliency"> </a>

Skype for Business Server unterstützt die Verwendung von Sprach-und Video-SIP-Stämmen mit dem gleichen Gateway-Peer. Also kann dieselbe CUCM-Bereitstellung Voice-SIP-Trunks an den Vermittlungsserver und Video-SIP-Trunks an den VIS umfassen.
  
- Ein PSTN-Gateway muss mit einem bestimmten FQDN im Topologiedokument für die Voice-SIP-Trunks definiert werden.
    
- Der Peer zum PSTN-Gateway ist der Vermittlungsserver.
    
- Bei Bedarf können mehrere Voice-Trunks definiert werden, die einen Bereich von einem PSTN-Gateway bis zu mehreren Vermittlungsserverpools umfassen.
    
- Ein Videogateway muss im Topologiedokument für den Video-SIP-Trunk mit demselben FQDN wie für das PSTN-Gateway definiert werden.
    
- Der Peer zum Videogateway ist der VIS.
    
- Ein einzelner Videotrunk kann von einem Videogateway zu einem bestimmten VIS-Pool definiert werden.
    
- CUCM muss so konfiguriert werden, dass Anrufe über den Voice trunk und den Video trunk ordnungsgemäß weitergeleitet werden. Beispielsweise kann eine spezielle Wähl Vorwahl verwendet werden, wenn Sie aus dem VTC wählen; CUCM könnte diese Wähl Vorwahl mit Anrufen an VIS verknüpfen, und entsprechende Übersetzungsregeln würden dieses Präfix von der SIP-Einladung zu VIS abstreifen.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Koexistenz von VIS in der Skype for Business-Version und früheren Versionen von Lync
<a name="resiliency"> </a>

VIS kann nur als Teil der Bereitstellung von Skype for Business bereitgestellt werden. Sie kann mit lync 2013-Konferenzen und-Clients interagieren, die Teil einer vorhandenen Bereitstellung sind. in diesem Fall muss der VIS-Pool Teil einer Skype for Business-Bereitstellung sein, die einen Registrar/FE-Pool enthält, der als nächster Hop für den VIS-Pool dient.
  
Der VIS unterstützt keine Transcodierung zwischen RTV und H.264. Es gibt keine Videointeroperabilität zwischen Clients vor Lync 2013 und VTC-Teilnehmern in einer Konferenz.
  
Wenn in einer Konferenz Clients vor Lync 2013 enthalten sind, senden mobile Clients Daten über RTV. Dies führt dazu, dass VTCs keine Videodaten erhalten, wenn der mobile Client zum dominanten Sprecher wird.
  
Damit Lync 2013 ordnungsgemäß mit dem VIS funktioniert, der Teil einer Skype for Business-Bereitstellung ist, muss für Lync 2013 die entsprechende CU angewendet werden, die den Lync 2013-Client, die CAA und die AVMCU für die Arbeit mit VIS aktualisiert.
  
Die Interoperabilität von VIS mit Lync 2013 und Skype for Business-Desktopclients wurde getestet und wird unterstützt.
  
Interoperabilität von VIS mit nicht-Desktop (Android, iPad, iPhone, Windows Phone, LMX usw.) Skype for Business-Clients, die im jeweiligen Apps Store zum Zeitpunkt der Veröffentlichung von VIS zur Verfügung stehen, wurden getestet und werden unterstützt.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Wiederherstellung bei Paketverlust über FEC
<a name="resiliency"> </a>

FEC kann zur Unterstützung der Wiederherstellung bei Paketverlust aktiviert werden. Bei aktivierter Funktion wird 50 % mehr Videobandbreite in der VIS-zu-VTC-Richtung genutzt.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS-Dimensionierung und Transcodierungskosten
<a name="resiliency"> </a>

Durch die Transcodierung einzelner Videostreams von der Cisco-VTC in mehrere Simulcaststreams wird CPU-Kapazität verbraucht. Etwa 16 VTCs können Ihr Video transcodieren lassen (vorausgesetzt, dass ein 720p-Videostream von jedem VTC in 3 getrennte Livestream-Streams bei 720p, 360p und 180P) in einem einzigen VIS ausgeführt wird, das auf dem Äquivalent der von lync 2013 empfohlenen FE-Plattform läuft. Wenn die Transcodierung deaktiviert ist, wird CPU-Kapazität auf dem VIS eingespart. Das durch den VIS beim VTC angeforderte Videobild hat jedoch die geringste übliche Auflösung, die alle Empfänger auf der Skype for Business-Seite zufriedenstellt. Beachten Sie, dass auch bei deaktivierter Transcodierung die Transcodierung möglicherweise aktiviert wird, wenn Skype for Business-Clients bestimmte niedrige Auflösungen anfordern, die VTCs nicht senden können.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Anrufverteilung vom Videogateway an den VIS
<a name="resiliency"> </a>

Die Verteilung erfolgt über einen der CUCM-Verteilungsmechanismen:
  
- Dynamisch über DNS
    
- Auf der CUCM-Seite können Sie einzelne Trunks definieren, wobei jeder Trunk auf einem anderen Server im VIS-Pool beendet wird. CUCM leitet Anrufe über die verschiedenen Trunks.
    
## <a name="no-hybrid-interoperability"></a>Keine hybride Interoperabilität
<a name="resiliency"> </a>

Die Unterstützung von VTCs, die über einen lokalen VIS an Onlinebesprechungen teilnehmen, ist kein Bestandteil von Skype for Business.
  
## <a name="no-federation-support"></a>Keine Unterstützung von Partnerverbünden
<a name="resiliency"> </a>

Die Unterstützung von VTCs, die über einen lokalen VIS an Besprechungen in einem Partnerverbund teilnehmen, ist kein Bestandteil von Skype for Business.
  
## <a name="see-also"></a>Siehe auch
<a name="resiliency"> </a>

[Bereitstellen des Video-Interop-Servers in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
