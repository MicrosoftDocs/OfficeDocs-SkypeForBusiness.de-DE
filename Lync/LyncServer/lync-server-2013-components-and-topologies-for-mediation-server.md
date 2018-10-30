---
title: 'Lync Server 2013: Komponenten und Topologien für den Vermittlungsserver'
TOCTitle: Komponenten und Topologien für den Vermittlungsserver
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398537(v=OCS.15)
ms:contentKeyID: 49294365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In diesem Thema werden die Komponenten beschrieben, von denen der Vermittlungsserver abhängt, sowie die Topologien, in denen der Vermittlungsserver bereitgestellt werden kann.

## Abhängigkeiten

Für den Vermittlungsserver gelten die folgenden Abhängigkeiten:

  - **Registrierung.** Erforderlich. Die Registrierung ist der nächste Hop für Signaldatenverkehr bei der Interaktion des Vermittlungsservers mit dem Lync Server 2013-Netzwerk. Beachten Sie, dass der Vermittlungsserver nicht nur in einem eigenständigen Pool ausgeführt werden kann, der ausschließlich aus Vermittlungsserver besteht, sondern zusätzlich auch mit der Registrierung auf einem Front-End-Server verbunden werden kann. Die Registrierung ist mit einem Vermittlungsserver und einem PSTN-Gateway auf einer Survivable Branch-Anwendung verbunden.

  - **Monitoring Server.** Optional, wird jedoch dringend empfohlen. Der Monitoring-Server ermöglicht dem Vermittlungsserver das Aufzeichnen von Qualitätsmetriken im Zusammenhang mit seinen Mediensitzungen.

  - **Edgeserver.** Für die Unterstützung externer Benutzer erforderlich. Der Edgeserver ermöglicht dem Vermittlungsserver die Interaktion mit Benutzern hinter einem NAT-Router oder einer Firewall.

## Topologien

Der Lync Server 2013- Vermittlungsserver wird standardmäßig mit einer Instanz der Registrierung auf einem Standard Edition-Server, in einem Front-End-Pool oder auf einer Survivable Branch-Anwendung ausgeführt. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert werden.

Wenn die Leistung ein Problem darstellt, kann es sinnvoll sein, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen. Wenn Sie SIP-Trunking bereitstellen, wird die Bereitstellung eines eigenständigen Vermittlungsserverpool empfohlen.

Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserverpool erforderlich. Der Grund hierfür ist, dass qualifizierte Gateways einen DNS-Lastenausgleich für einen Pool von Vermittlungsserver durchführen und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.

Es wird außerdem empfohlen, den Vermittlungsserver mit einem Front-End-Pool zu verbinden, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder eine Verbindung zum Session Border Controller (SBC) eines Anbieters von Internettelefoniediensten herstellen, sofern die folgenden Bedingungen erfüllt sind:

  - Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-Nebenstellenanlage unterstützt keine Medienumgehung, aber der Front-End-Pool, der den Vermittlungsserver hostet, kann Sprachtranscodierung für Anrufe abwickeln, für die die Medienumgehung nicht anwendbar ist.

Sie können mithilfe des Microsoft Lync Server 2013, Planungstools herausfinden, ob der Front-End-Pool, mit dem Sie den Vermittlungsserver verbinden möchten, die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Ausführliche Informationen dazu, welche Topologie Sie bereitstellen sollten, finden Sie unter [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Die folgende Abbildung zeigt eine einfache Topologie mit zwei Standorten, die über eine WAN-Leitung verbunden sind. Der Vermittlungsserver wird mit der Registrierung in einem Front-End-Pool an Standort 1 verbunden. Die Vermittlungsserver an Standort 1 steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die Medienumgehung global aktiviert, um Informationen zu Standorten und Regionen verwenden. Zudem ist die Umgehung für die Trunkverbindungen mit jedem PSTN-Gateway (GW1 und GW2) aktiviert.

**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![VoIP-Topologie mit Vermittlungsserver und WAN-Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "VoIP-Topologie mit Vermittlungsserver und WAN-Gateway")

Die nächste Abbildung zeigt eine einfache Topologie, in der der Vermittlungsserver mit der Registrierung im Front-End-Pool an Standort 1 verbunden wird und über eine direkte SIP-Verbindung mit der IP-Nebenstellenanlage an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungsserver zudem ein PSTN-Gateway an Standort 2. Es wird davon ausgegangen, dass sowohl an Standort 1 als auch an Standort 2 Lync-Benutzer vorhanden sind. Ferner wird davon ausgegangen, dass die IP-Nebenstellenanlage über einen zugeordneten Medienprozessor verfügt, über den der gesamte Mediendatenverkehr von Lync-Endpunkten verarbeitet werden muss, bevor er an Medienendpunkte gesendet wird, die von der IP-Nebenstellenanlage gesteuert werden. In dieser Topologie ist die Medienumgehung global aktiviert, um Informationen zu Standorten und Regionen zu verwenden. Zudem ist die Medienumgehung für die Trunkverbindungen mit der Nebenstellenanlage und dem PSTN-Gateway aktiviert.

**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![VoIP-Topologie mit Vermittlungsserver und WAN-Festnetztelefonanlage](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "VoIP-Topologie mit Vermittlungsserver und WAN-Festnetztelefonanlage")

Ausführliche Informationen zum Planen von Topologien für Nebenstellenanlagen finden Sie unter [Richtlinien für die Vermittlungsserverbereitstellung in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) und [Optionen für Bereitstellungen mit direkten SIP-Verbindungen in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

In der letzten Abbildung in diesem Thema wird eine Topologie gezeigt, in der der Vermittlungsserver mit dem SBC eines Anbieters von Internettelefoniediensten verbunden ist. Ausführliche Informationen zu Topologien für das SIP-Trunking finden Sie unter [SIP-Trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).

