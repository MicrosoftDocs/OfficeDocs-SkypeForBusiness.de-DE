---
title: Hardwareunterstützung für lync Server 2013 Geräte
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c802141adfecf53b70709ad90cc098004eacda1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522462"
---
# <a name="device-hardware-support-in-lync-server-2013"></a>Unterstützung von Gerätehardware in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-14_

Bevor Sie IP-Telefone und analoge Geräte bereitstellen, müssen spezifische Hardwarekonfigurationen vorliegen.

IP-Telefone, auf denen lync Phone Edition Support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) und Power over Ethernet (PoE).Um die Vorteile von LLDP-MED zu nutzen, muss der Switch IEEE802.1AB und ANSI/TIA-1057 unterstützen. Um PoE zu nutzen, muss der Switch PoE802.3AF oder 802.3at unterstützen.

Zur Aktivierung von LLDP-MED muss der Administrator LLDP über das Konsolenfenster für den Switch aktivieren und die LLDP-MED-Netzwerkrichtlinie mit der richtigen VoIP-VLAN-ID konfigurieren.

Wenn Ihre Bereitstellung analoge Geräte enthält, müssen Sie darüber hinaus das analoge Gateway für die Verwendung von lync Server konfigurieren, und das Gateway muss einer der folgenden sein:

  - ATA-Gerät (Analog Telephone Adapter)

  - Analoges PSTN-Gateway

  - Survivable Branch Appliance mit analogem PSTN-Gateway

  - Survivable Branch Appliance mit PSTN-Gateway, das mit einem ATA-Gerät kommuniziert

Informationen zum Konfigurieren eines analogen Gateways finden Sie unter "Planung der Bereitstellung von analogen Geräten" [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in der lync Server 2010 TechNet-Bibliothek. (Analoge Geräte funktionieren in lync Server 2013 genauso wie in lync Server 2010.)

<div>


> [!IMPORTANT]  
> Sie können den Switch für 9-1-1 (erweitert) (E9-1-1) konfigurieren, wenn der Switch diese Funktion unterstützt.



</div>

</div>

<span> </span>

</div>

</div>

</div>

