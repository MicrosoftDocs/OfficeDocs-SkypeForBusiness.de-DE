---
title: 'Lync Server 2013: Vermittlungsserverkomponente'
TOCTitle: Vermittlungsserverkomponente
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398399(v=OCS.15)
ms:contentKeyID: 49294113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vermittlungsserverkomponente in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Der Vermittlungsserver in Lync Server 2013 muss für die Enterprise-VoIP-Arbeitsauslastung bereitgestellt werden. In diesem Abschnitt werden die grundlegende Funktionalität, Abhängigkeiten, grundlegende Topologien sowie Richtlinien für die Planung beschrieben.

Der Vermittlungsserver übersetzt Signale und - in einigen Konfigurationen - Medien zwischen Ihrer internen Lync Server 2013Enterprise-VoIP-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder SIP-Trunk (Session Initiation Protocol). Aufseiten von Lync Server 2013 überwacht der Vermittlungsserver eine einzelne Mutual TLS-Transportadresse (MTLS). Aufseiten des Gateways überwacht der Vermittlungsserver alle zugehörigen Überwachungsports für die Trunks, die im Topologiedokument definiert wurden. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.

Wenn Sie in Ihrer Umgebung zudem über eine vorhandene Nebenstellenanlage verfügen, verarbeitet der Vermittlungsserver Anrufe zwischen Enterprise-VoIP-Benutzern und der Nebenstellenanlage. Wenn es sich bei Ihrer Nebenstellenanlage um eine IP-Nebenstellenanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und dem Vermittlungsserver erstellen. Bei Verwendung einer TDM-Nebenstellenanlage (Time Division Multiplex) müssen Sie zudem ein PSTN-Gateway zwischen dem Vermittlungsserver und der Nebenstellenanlage bereitstellen.

Der Vermittlungsserver ist standardmäßig mit dem Front-End-Server verbunden. Der Vermittlungsserver kann ebenfalls in einem eigenständigen Pool bereitgestellt werden, um eine bessere Leistung zu erzielen, oder wenn Sie SIP-Trunking bereitstellen (in diesem Fall wird die Bereitstellung in einem eigenständigen Pool dringend empfohlen).

Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserverpool erforderlich. Der Grund hierfür ist, dass qualifizierte Gateways einen DNS-Lastenausgleich für einen Pool von Vermittlungsservern durchführen und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.

Es wird außerdem empfohlen, den Vermittlungsserver mit einem Front-End-Pool zu verbinden, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder eine Verbindung zum Session Border Controller (SBC) eines Anbieters von Internettelefoniediensten herstellen, sofern die folgenden Bedingungen erfüllt sind:

  - Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-Nebenstellenanlage unterstützt keine Medienumgehung, aber der Front-End-Pool, der den Vermittlungsserver hostet, kann Sprachtranscodierung für Anrufe abwickeln, für die die Medienumgehung nicht anwendbar ist.

Sie können mithilfe des Microsoft Lync Server 2013, Planungstools herausfinden, ob der Front-End-Pool, mit dem Sie den Vermittlungsserver verbinden möchten, die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Der Vermittlungsserver hat die folgenden Hauptfunktionen:

  - Verschlüsseln und Entschlüsseln von SRTP auf Lync Server-Seite

  - Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über Mutual TLS

  - Übersetzen von Mediendatenströmen zwischen Lync Server und dem Gatewaypeer des Vermittlungsserver

  - Herstellen von Verbindungen zwischen Clients außerhalb des Netzwerks und internen ICE-Komponenten, damit Medien NAT und Firewalls passieren können

  - Vermitteln von Anrufflüssen, die nicht von einem Gateway unterstützt werden, wie z. B. Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Client

  - Verwenden des SIP-Trunking-Dienstanbieters für das Telefonfestnetz, sodass kein PSTN-Gateway erforderlich ist (gilt für Bereitstellungen mit SIP-Trunking)

Die folgende Abbildung zeigt die Signal- und Medienprotokolle, die der Vermittlungsserver bei der Kommunikation mit einem Basis-PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet.

**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Vermittlungsserverprotokolle (Diagramm)](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Vermittlungsserverprotokolle (Diagramm)")


> [!NOTE]
> Bei Verwendung von TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) zwischen dem PSTN-Gateway und dem Vermittlungsserver im Netzwerk sollten Sie geeignete Maßnahmen ergreifen, um die Sicherheit und den Datenschutz innerhalb des Netzwerks sicherzustellen.



## In diesem Abschnitt

  - [M:N-Trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Anrufsteuerung und Vermittlungsserver in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver in Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Medienumgehung und Vermittlungsserver in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

