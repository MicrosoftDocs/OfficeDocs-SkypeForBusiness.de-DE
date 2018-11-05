---
title: 'Lync Server 2013: Unterstützte Gerätehardware'
TOCTitle: Unterstützte Gerätehardware
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412908(v=OCS.15)
ms:contentKeyID: 49295212
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Gerätehardware in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie IP-Telefone und analoge Geräte bereitstellen, müssen spezifische Hardwarekonfigurationen vorliegen.

IP-Telefone, auf denen Lync Phone Edition ausgeführt wird, unterstützen LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discovery) und PoE (Power over Ethernet). Um die Vorteile von LLDP-MED zu nutzen, muss der Switch IEEE802.1AB und ANSI/TIA-1057 unterstützen. Um PoE zu nutzen, muss der Switch PoE802.3AF oder 802.3at unterstützen.

Zur Aktivierung von LLDP-MED muss der Administrator LLDP über das Konsolenfenster für den Switch aktivieren und die LLDP-MED-Netzwerkrichtlinie mit der richtigen VoIP-VLAN-ID konfigurieren.

Wenn Ihre Bereitstellung analoge Geräte umfasst, müssen Sie darüber hinaus das analoge Gateway zur Verwendung von Lync Server konfigurieren, und bei dem Gateway muss es sich um eines der folgenden Geräte handeln:

  - ATA-Gerät (Analog Telephone Adapter)

  - Analoges PSTN-Gateway

  - Survivable Branch Appliance mit analogem PSTN-Gateway

  - Survivable Branch Appliance mit PSTN-Gateway, das mit einem ATA-Gerät kommuniziert

Informationen zum Konfigurieren eines analogen Gateways finden Sie im Abschnitt "Planen der Bereitstellung von analogen Geräten" unter [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in der Lync Server 2010 TechNet-Bibliothek. (Analoge Geräte funktionieren in Lync Server 2013 genauso wie in Lync Server 2010.)


> [!IMPORTANT]
> Sie können den Switch für 9-1-1 (erweitert) (E9-1-1) konfigurieren, wenn der Switch diese Funktion unterstützt.


