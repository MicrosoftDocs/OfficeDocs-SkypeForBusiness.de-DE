---
title: Planen der Interop-Videoserver in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Zusammenfassung: Lesen Sie diesen Abschnitt beim Planen von Drittanbietern Telekonferenzen Geräte Skype für Business Server Integration.'
ms.openlocfilehash: 3012ef38a6d1abced7731b405d31b2a0be20be8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907122"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planen der Interop-Videoserver in Skype für Business Server
 
**Zusammenfassung:** Überprüfen Sie beim Planen von Drittanbietern Telekonferenzen Geräte Skype für Business Server Integration in diesem Thema.
  
Skype für Business Server kann jetzt Sie bestimmte VTC (Video Telekonferenzsystem)-Lösungen von Drittanbietern zu integrieren. Die neue Serverrolle, die durch diese Interoperabilität von Videokonferenzen kann ist das Video Interop Server (gegenüber), die derzeit als einen eigenständigen Server Role nur für lokale Installationen implementiert wird. Ein gegenüber dient als Vermittlung zwischen einem Drittanbieter Telefonkonferenzen System und einen Skype für Business Server-Bereitstellung. Bei dieser Version konzentriert sich der VIS auf die Interoperabilität mit Videosystemen von Cisco/Tandberg. Lesen Sie diesen Artikel, um festzustellen, ob dieses Feature in Ihrer Skype für die Installation von Business Server verwendet.
  
## <a name="device-interoperability"></a>Interoperabilität von Geräten

Getestet und unterstützt Sie beim Registrieren des Cisco VTCs Interoperation mit Cisco Unified Communications Manager (CallManager oder CUCM) Version 10.5 und TCP-SIP-Trunks eingerichtet zwischen CUCM und der VIS.
  
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
>  Cisco Software release TC7.0.0 oder oben auf diesen Systemen für die Integration mit Skype für Business Server erwartungsgemäß erforderlich ist.
  
## <a name="sip-trunks"></a>SIP-Trunks

Die Videoserver Interop-Funktionen in SIP-Trunk-Modus, in dem die VTCs weiterhin mit der vorhandenen Cisco Infrastruktur - beispielsweise Cisco Call Manager (CUCM) registrieren. Ein Video-SIP-Trunk ist zwischen CUCM und dem VIS definiert, sodass Anrufe zwischen den beiden Systemen weitergeleitet werden können. Nur Anrufe über den SIP-Trunk vom Videotelekonferenzsystem (VTC) an den VIS werden unterstützt. Folglich kann nicht VTCs können in einer Skype für Business Konferenz einwählen, (durch Wählen der Telefonnummer anrufen automatische Telefonzentrale zugeordnet), aber Drag & Drop in die Konferenz.
  
![Diagramm von VIS in SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Funktionen

Diese Serverrolle bietet Folgendes:
  
- Die Konvertierung zwischen 3. Party video Systeme und die Skype für Business Server-Bereitstellung verwendeten h. 264-Formate.
    
- Konvertierung der einzelnen Videostreams mit einer bestimmten Auflösung von einer VTC in mehreren Live-Streams von unterschiedlichen Lösungen für die Verwendung in der Skype für Business Server-Bereitstellung. Diese Streams können auf die AVMCU und dann auf Skype gesendet werden, für die Business Server-Endpunkten und andere video Systeme, die unterschiedliche Auflösung angefordert haben. Diese Konvertierung wird auch verwendet, wenn das video Drittanbieter-System in einem Skype for A Business beteiligt ist / V-Konferenz aufrufen. Sobald die transcodieren in einem bestimmten gegenüber Server erreicht ist, erhalten alle folgenden Anforderungen für unterschiedliche Auflösung nur einen Stream mit geringster Auflösung. 
    
- Unterstützung für video SIP-Trunk zwischen dem Gateway CUCM und einen Skype für Business Server Video Interop Server; VTCs weiterhin mit dem Gateway Cisco registrieren und tätigen von Anrufen an die Skype für die Business-Bereitstellung über das Gateway. Anrufe werden über den video SIP-Trunk vom Gateway an die Skype für Business Video Interop-Server weitergeleitet.
    
- Unterstützung eines Benutzers in einem Konferenzraum mit einem unterstützten Videosystem, sodass von diesem System aus gewählt werden kann, um an einer offenen oder geschlossenen Konferenz teilzunehmen. Dieser Anruf durchläuft den Video-SIP-Trunk.
    
- Unterstützung für einen Benutzer in einem Konferenzraum mit einem unterstützten video System zum Aufrufen einer Skype für Business-Client. Der Anruf durchläuft den SIP-Trunk.
    
- Unterstützung für Mid Steuerung aus der Skype für die Business Serverseite oder vom System unterstützten VTC für Point-to-Point und multipoint Anrufe einschließlich Stummschalten/deaktivieren-mute Audio, Video anhalten/fortsetzen, Sperre Video- und Anruf halten/Deinstallation-halten.
    
## <a name="known-limitations"></a>Bekannte Einschränkungen

Diese Serverrolle unterliegt den folgenden Einschränkungen:
  
- Neue Anrufe von der Skype für die Business-Bereitstellung an die VTCs über den video SIP-Trunk werden nicht unterstützt. . Dies bedeutet, dass nur neuen Anrufe von der VTCs in der Skype für die Business-Bereitstellung über den SIP-Trunk video unterstützt werden. Anwesenheitsinformationen für unterstützte video System nicht zur Verfügung über den video SIP-Trunk an das VIS. 
    
- Es wird nur ein eigenständiger VIS-Pool für den Video-SIP-Trunkmodus unterstützt.
    
-  TLS + SRTP oder TCP + RTP wird für die Kommunikation zwischen dem VTC und dem VIS über den Video-SIP-Trunk unterstützt.
    
- Die Anwendungsfreigabe wird nicht unterstützt. Eine Skype für Geschäftsbenutzer im Konferenzraum muss die Skype für Business-Konferenz (über einen Laptop beispielsweise) teilnehmen und Anzeigen der Anwendungsfreigabe Startseiten auf einen der kostenlosen Monitore im Konferenzraum nicht mit der VTC verknüpft sind.
    
- Ein VTC kann nicht über einen VIS an einer Besprechung im Partnerverbund teilnehmen.
    
- Ein VTC kann nicht über einen VIS an einer Onlinebesprechung teilnehmen.
    
- Anrufe von einem VTC an die PSTN über den VIS werden nicht unterstützt.
    
- Anrufe von der PSTN an einen VTC über den VIS werden nicht unterstützt.
    
## <a name="resiliency-mechanisms"></a>Flexibilitätsmechanismen
<a name="resiliency"> </a>

Die gegenüber unterstützt eingehende Anrufe von einem CUCM, die über einen SIP-Trunk video übertragen werden. Es ist möglich, verlieren Konnektivität entweder Upstream- oder downstream, also für stabile Resiliency berücksichtigt beide mögliche Werte:
  
1. **Gegenüber Poolfailover** Hauptfenster gegenüber Pool, dem auf das video Gateway verweist ausgefallen ist, Wiederherstellung möglich, wenn das video Gateway Trunks in zwei (oder mehrere) gegenüber Pools definiert wurde. Das video Gateway fest, dass es keine Aufrufe in den primären Pool gegenüber durchführen kann, leitet Anrufe an einen sekundären gegenüber Pool einfach weiter.
    
     ![Diagramm eines VIS-Poolfailover](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Ein bestimmter Pool gegenüber kann Trunks mit mehreren Gateways, aber normalerweise einem bestimmten Gateway kann nicht haben Trunks in mehreren gegenüber Pools, damit eine Flashkarten zur Unterstützung dieser Failover erfolgen muss: definieren 2 FDQNs in DNS, die in die IP-Adresse eines Gateways video aufgelöst. Darstellen Sie jeder FQDN als ein separates video Gateway in das Topologiedokument ein, wobei jedes video Gateway hat einen Trunk an einen anderen Pool gegenüber und Recovery ist nun möglich. (Wenn TLS verwendet wird, die mehrere Namen müssen im SAN des Zertifikats video Gateway sein.)
    
    > [!NOTE]
    > VIS gestattet nur eingehende Anrufe von Gateways, die im Topologiedokument konfiguriert sind. 
  
2. **Front-End-failover** Wenn ein Pool gegenüber einen Anruf von CUCM erhält, aber nicht seiner primären nächsten Hop Registrierung oder Front-End-Pool erreichen, werden Anrufe zu einem Front-End-Sicherungspool weitergeleitet.
    
     ![Diagramm eines Front-End-Failover](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Die gegenüber wird Nachverfolgen der den Status der primären Front-End-Pool und dem Front-End-Sicherungspool (die Einstellung in der backup-Einstellung für den Registrierungsdienst im Topologiedokument gefunden wird). Sendet Optionen Umfragen einmal pro Minute an beiden Pools und befinden sich fünf erfolglosen die gegenüber nimmt an, dass ein bestimmter Front-End-Pool vorhanden ist. Wenn der primäre Front-End-Pool als nach unten und gibt es einen verfügbaren konfiguriert ist markiert ist sendet backup der gegenüber neuen Anrufe vom Gateway mit dem Front-End-Sicherungspool. Nachdem Sie der primäre Front-End-Pool wieder verfügbar ist, wird die gegenüber mit den primären Front-End-Pool für neue Anrufe fortgesetzt.
    
    Der VIS implementiert außerdem einen 10-Sekunden-Timer für Anrufe vom Video-SIP-Trunk. Wenn der primäre nächsten Hop Front-End-Pool für einen Anruf aus dem video SIP-Trunk und das primäre Front-End für den nächsten Hop, dass der Pool nicht mit einigen SIP-Nachricht (einschließlich 100 Verbindungsversuch) an die INVITE-Nachricht gesendet, es innerhalb dieser Wert Timer, die backup nächsten Hop-Proxy für den Anruf s entgegennehmen verwendet wurde Hould versucht werden, wenn konfiguriert. 
    
    > [!NOTE]
    > Wenn es zuerst mit dem Sicherungspool für den nächsten Hop versucht wurde, wird der primäre Pool anschließend nicht mehr ausprobiert. 
  
    Der Administrator kann auch den Windows PowerShell-Failoverbefehl verwenden, um den VIS zu zwingen, den Sicherungs-Front-End-Pool zu verwenden, beispielsweise wenn Wartungsarbeiten am primären Front-End-Pool durchgeführt werden müssen.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Koexistenz von Voice- und Videotrunks für denselben Gatewaypeer
<a name="resiliency"> </a>

Für Sprach- und Videofunktionen SIP-Trunks mit Business Server unterstützt Skype verwenden den gleichen gatewaypeer. Also kann dieselbe CUCM-Bereitstellung Voice-SIP-Trunks an den Vermittlungsserver und Video-SIP-Trunks an den VIS umfassen.
  
- Ein PSTN-Gateway muss mit einem bestimmten FQDN im Topologiedokument für die Voice-SIP-Trunks definiert werden.
    
- Der Peer zum PSTN-Gateway ist der Vermittlungsserver.
    
- Bei Bedarf können mehrere Voice-Trunks definiert werden, die einen Bereich von einem PSTN-Gateway bis zu mehreren Vermittlungsserverpools umfassen.
    
- Ein Videogateway muss im Topologiedokument für den Video-SIP-Trunk mit demselben FQDN wie für das PSTN-Gateway definiert werden.
    
- Der Peer zum Videogateway ist der VIS.
    
- Ein einzelner Videotrunk kann von einem Videogateway zu einem bestimmten VIS-Pool definiert werden.
    
- CUCM Routen der Anrufe über den VoIP-Trunk im Vergleich zu den video Trunk ordnungsgemäß konfiguriert werden müssen. Beispielsweise konnte ein Präfix spezielle Dial verwendet werden, beim Einwählen aus der VTC. CUCM konnte dieses Präfix Dial Aufrufe gegenüber zuordnen und entsprechende Übersetzungsregeln würde dieses Präfix aus der SIP INVITE-Nachricht an VIS. entfernen
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Koexistenz von VIS in der Skype for Business-Version und früheren Versionen von Lync
<a name="resiliency"> </a>

GEGENÜBER kann nur als Teil des Skype für die Bereitstellung von Business bereitgestellt werden. Können die Interaktion mit Lync 2013-Konferenzen und Clients, die Teil einer vorhandenen Bereitstellung sind; in diesen Fällen müssen gegenüber Pool einen Skype für die Bereitstellung von Business angehören, die einen Pool Registrierung/FE enthält, der den nächsten Hop für den Pool gegenüber befindet.
  
Der VIS unterstützt keine Transcodierung zwischen RTV und H.264. Es gibt keine Videointeroperabilität zwischen Clients vor Lync 2013 und VTC-Teilnehmern in einer Konferenz.
  
Wenn in einer Konferenz Clients vor Lync 2013 enthalten sind, senden mobile Clients Daten über RTV. Dies führt dazu, dass VTCs keine Videodaten erhalten, wenn der mobile Client zum dominanten Sprecher wird.
  
Damit Lync 2013 ordnungsgemäß mit dem VIS funktioniert, der Teil einer Skype for Business-Bereitstellung ist, muss für Lync 2013 die entsprechende CU angewendet werden, die den Lync 2013-Client, die CAA und die AVMCU für die Arbeit mit VIS aktualisiert.
  
Die Interoperabilität von VIS mit Lync 2013 und Skype for Business-Desktopclients wurde getestet und wird unterstützt.
  
Interoperabilität von gegenüber mit nicht-Desktop (Android, Ipad, Iphone, Windows Phone, LMX usw.) Skype für Business-Clients aus dem entsprechenden Apps Speicher zum Zeitpunkt der gegenüber Version verfügbaren getestet und unterstützt wird.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Wiederherstellung bei Paketverlust über FEC
<a name="resiliency"> </a>

FEC kann zur Unterstützung der Wiederherstellung bei Paketverlust aktiviert werden. Bei aktivierter Funktion wird 50 % mehr Videobandbreite in der VIS-zu-VTC-Richtung genutzt.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS-Dimensionierung und Transcodierungskosten
<a name="resiliency"> </a>

Durch die Transcodierung einzelner Videostreams von der Cisco-VTC in mehrere Simulcaststreams wird CPU-Kapazität verbraucht. Ungefähr 16 VTCs können ihre video transcodiert (vorausgesetzt, dass 720p Videostreams aus jeder VTC transcodiert in 3 separate Live-Streams 720p, 360p und 180p ist) in einer einzelnen gegenüber auf das Äquivalent von der Lync 2013 empfohlen FE Plattform ausgeführt haben. Wenn die Transcodierung deaktiviert ist, wird CPU-Kapazität auf dem VIS eingespart. Das durch den VIS beim VTC angeforderte Videobild hat jedoch die geringste übliche Auflösung, die alle Empfänger auf der Skype for Business-Seite zufriedenstellt. Beachten Sie, dass auch bei deaktivierter Transcodierung die Transcodierung möglicherweise aktiviert wird, wenn Skype for Business-Clients bestimmte niedrige Auflösungen anfordern, die VTCs nicht senden können.
  
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

[Bereitstellen eines Video Interop-Servers in Skype für Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
