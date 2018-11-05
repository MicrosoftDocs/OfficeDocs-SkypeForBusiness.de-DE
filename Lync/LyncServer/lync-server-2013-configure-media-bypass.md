---
title: 'Lync Server 2013: Konfigurieren der Medienumgehung'
TOCTitle: Konfigurieren der Medienumgehung
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413028(v=OCS.15)
ms:contentKeyID: 49295912
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt wird vorausgesetzt, dass Sie bereits mindestens einen Vermittlungsserver veröffentlicht und konfiguriert haben (wie unter [Definieren eines Vermittlungsservers im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) und [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) bzw. [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) und [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation beschrieben).

Außerdem wird vorausgesetzt, dass Sie zumindest einen Gatewaypeer zur Bereitstellung von PSTN-Verbindungen wie in [Definieren eines Gateways im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) beschrieben festgelegt haben. Wenn es sich bei dem Peer, mit dem Sie sich verbinden, um den SBC eines SIP-Trunkinganbieter handelt, sollten Sie sich vergewissern, dass dieser ein qualifizierter Anbieter ist und die Medienumgehung unterstützt. Viele SIP-Trunkinganbieter lassen für den SBC nur den Empfang von Datenverkehr vom Vermittlungsserver zu. In diesem Fall darf die Medienumgehung für den betreffenden Trunk nicht aktiviert werden. Darüber hinaus können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation dem SIP-Trunkinganbieter ihre internen Netzwerk-IP-Adressen offenlegt.


> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur für die Produkte und Versionen unterstützt, die auf der Webseite für das Unified Communications Open Interoperability Program \endash Lync Server unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268730">http://go.microsoft.com/fwlink/?linkid=268730</A> aufgelistet werden.



In diesem Abschnitt wird beschrieben, wie Sie die Medienumgehung aktivieren, um die erforderliche Verarbeitungsleistung durch den Vermittlungserver zu verringern. Bevor Sie die Medienumgehung aktivieren, dass Ihre Umgebung die dafür erforderlichen Anforderungen erfüllt (siehe [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in der Planungsdokumentation. Denken Sie daran die Informationen in [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) für die Frage zu berücksichtigen, ob Sie die globalen Einstellungen für die Medienumgehung aktivieren, damit der Vermittlungsserver standardmäßig umgangen wird, oder ob Sie auf Grundlage von standort- und regionsspezifischen Informationen entscheiden, ob der Vermittlungsserver umgangen werden soll.

Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) - eine andere erweiterte Enterprise-VoIP-Funktion - bereits optional konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung der Anrufsteuerung nicht für Anrufe gilt, für welche die Medienumgehung aktiviert ist. Bei einem Anruf wird zuerst überprüft, ob die Medienumgehung angewendet werden soll. Wenn dies der Fall ist, wird die Anrufsteuerung nicht angewendet. Nur wenn die Medienumgehung nicht aktiviert ist, wird geprüft, ob die Anrufsteuerung angewendet werden soll. Diese beiden Funktionen schließen sich für alle Anrufe, die an das PSTN weitergeleitet werden, gegenseitig aus. Dies ist ein logisches Verhalten, denn die Medienumgehung setzt voraus, dass bei einem Anruf keine Bandbreitenbeschränkungen zwischen den Medienendpunkten vorhanden sind. In Verbindungen mit eingeschränkter Bandbreite kann keine Medienumgehung stattfinden. Demzufolge trifft auf einen PSTN-Anruf nur eine der beiden folgenden Verhaltensweisen zu: a) die Medien umgehen den Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf oder b) die Anrufsteuerung reserviert Bandbreite für den Anruf, und die Medien werden vom betroffenen Vermittlungsserver verarbeitet.

## Nächste Schritte: Aktivieren der Medienumgehung für die Trunkverbindung

Nach der Konfiguration der anfänglichen Einstellungen für die PSTN-Anbindung (Wähleinstellungen, VoIP-Richtlinien, PSTN-Verwendungsdatensätze, ausgehende Anrufrouten und Übersetzungsregeln) führen Sie die Schritte unter [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) aus, um mit der Aktivierung der Medienumgehung zu beginnen.

## Siehe auch

#### Aufgaben

[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren der Medienumgehung zur dauerhaften Umgehung des Vermittlungsservers](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  

#### Konzepte

[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Weitere Ressourcen

[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

