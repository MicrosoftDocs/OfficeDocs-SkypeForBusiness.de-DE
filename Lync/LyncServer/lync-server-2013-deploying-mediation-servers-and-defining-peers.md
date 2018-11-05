---
title: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers'
TOCTitle: Bereitstellen von Vermittlungsservern und Definieren von Peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412780(v=OCS.15)
ms:contentKeyID: 49294993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterten Enterprise-VoIP-Anwendungen ( Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen, Anrufsteuerung usw.) sind in Front-End-Pools verfügbar. Bei Lync Server 2013 ist die Funktionalität der Vermittlungsserver in den Front-End-Server integriert. Ein separater, eigenständiger Vermittlungsserver wird nicht mehr benötigt. Front-End-Pools können direkt mit unterstützten Gateways (PSTN-Gateway oder IP-Nebenstellenanlage) kommunizieren, wodurch kein Vermittlungsserver als Mittler benötigt wird.

Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar. Zum Herstellen einer Verbindung zischen Ihrer Enterprise-VoIP-Infrastruktur und dem SIP-Trunkinganbieter muss ein separater Vermittlungsserver bereitgestellt werden.

Die Verbindung zwischen Lync Server (der Vermittlungsserver-Komponente in einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway wird als logische Zuordnung definiert, die man als *Trunk* bezeichnet. In den Themen in diesem Abschnitt werden die Definition eines Trunks und die Bereitstellung eines eigenständigen Vermittlungsservers beschrieben, wenn Sie eine Verbindung mit einem SIP-Trunk herstellen.

## In diesem Abschnitt

  - [Definieren eines Vermittlungsservers im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definieren eines Gateways im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definieren von zusätzlichen Trunks im Topologie-Generator in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

## Zugehörige Abschnitte

[Konfigurieren von Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

