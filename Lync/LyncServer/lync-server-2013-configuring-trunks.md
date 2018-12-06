---
title: 'Lync Server 2013: Konfigurieren von Trunks'
TOCTitle: Konfigurieren von Trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398170(v=OCS.15)
ms:contentKeyID: 49293149
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Im Rahmen einer Enterprise-VoIP-Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und mindestens einem der folgenden Peers konfigurieren, um PSTN-Verbindungen für Enterprise-VoIP-Clients und -Geräte in Ihrer Organisation bereitzustellen:

  - SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten

  - PSTN-Gateway

  - Nebenstellenanlage (Private Branch Exchange, PBX)

Ausführliche Informationen finden Sie unter [Planen der PSTN-Konnektivität in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in der Planungsdokumentation.


> [!IMPORTANT]
> Bevor Sie mit der Trunkkonfiguration beginnen, überprüfen Sie, ob die Topologie erstellt und der Vermittlungsserver und der Peer konfiguriert und einander zugeordnet wurden. Nähere Informationen finden Sie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in Lync Server 2013</A> in der Bereitstellungsdokumentation.




> [!NOTE]
> Im Rahmen der Trunkkonfiguration können Sie die Lync Server 2013-Medienumgehung aktivieren, die eine Umgehung des Vermittlungsservers für Medien ermöglicht. Trunks können mit oder ohne Medienumgehung konfiguriert werden, die Aktivierung dieser Funktion wird jedoch dringend empfohlen. Nähere Informationen finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-planning-for-media-bypass.md">Planung der Medienumgehung in Lync Server 2013</A>.



## In diesem Abschnitt

  - [Unterstützung für mehrere Trunks in Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Routing zwischen Trunks in Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Anzeigen von Informationen zur Trunkkonfiguration in Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Konfigurieren eines Trunks ohne Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Ändern von SIP-Trunk-Konfigurationseinstellungen in Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Testen von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Anzeigen von Informationen zu einzelnen SIP-Trunks in Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

## Siehe auch

#### Aufgaben

[Definieren eines Gateways im Topologie-Generator in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### Weitere Ressourcen

[Planen der PSTN-Konnektivität in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

