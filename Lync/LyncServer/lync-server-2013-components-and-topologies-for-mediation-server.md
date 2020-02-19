---
title: 'Lync Server 2013: Komponenten und Topologien für Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1337e7ecdc1ee1467bcb78f0b89ea1410445f59c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Komponenten und Topologien für Vermittlungsserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

In diesem Thema werden die Komponenten beschrieben, von denen die Vermittlungsserver abhängig ist, und die Topologien, in denen der Vermittlungsserver bereitgestellt werden kann.

<div>

## <a name="dependencies"></a>Abhängigkeiten

Die Vermittlungsserver hat die folgenden Abhängigkeiten:

  - **Registrierungsstelle.** Erforderlich. Die Registrierungsstelle ist der nächste Hop für die Signalisierung im Vermittlungsserver Interaktionen mit dem lync Server 2013 Netzwerk. Beachten Sie, dass Vermittlungsserver auf einem Front-End-Server zusammen mit der Registrierungsstelle zusammengestellt werden können und nicht nur in einem eigenständigen Pool installiert sind, der nur aus Vermittlungsservern besteht. Die Registrierungsstelle wird mit einem Vermittlungsserver und einem PSTN-Gateway auf einem Survivable Branch Appliance zusammengefasst.

  - **Monitoring Server.** Optional, wird jedoch dringend empfohlen. Mit dem Monitoring Server kann der Vermittlungsserver Qualitäts Metriken aufzeichnen, die seinen Mediensitzungen zugeordnet sind.

  - **Edgeserver.** Für die Unterstützung externer Benutzer erforderlich. Die Edgeserver ermöglicht es dem Vermittlungsserver, mit Benutzern zu interagieren, die sich hinter einer NAT oder Firewall befinden.

</div>

<div>

## <a name="topologies"></a>Topologien

Die lync Server 2013, Vermittlungsserver ist standardmäßig mit einer Instanz der Registrierungsstelle auf einem Standard Edition-Server, einem Front-End-Pool oder Survivable Branch Appliance verbunden. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.

Wenn es sich bei der Leistung um ein Problem handelt, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen. Wenn Sie SIP-Trunking bereitstellen, wird empfohlen, einen eigenständigen Vermittlungsserver Pool bereitzustellen.

Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können.

Die Verbindung des Vermittlungsservers mit einem Front-End-Pool wird auch empfohlen, wenn Sie IP-Nebenstellenanlagen oder einen von einem Internettelefoniedienstanbieter bereitgestellten SBC (Session Border Controller) verwenden, sofern eine der folgenden Bedingungen erfüllt ist:

  - Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-Nebenstellenanlage unterstützt keine medienumgehung, aber die Front-End-Pool, die die Vermittlungsserver hostet, kann die Sprachübertragung für Anrufe verarbeiten, für die die medienumgehung nicht gilt.

Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Ausführliche Informationen zur bereitzustellenden Topologie finden Sie unter [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Die folgende Abbildung zeigt eine einfache Topologie aus zwei Standorten, die über eine WAN-Verbindung verbunden sind. Vermittlungsserver wird mit der Registrierungsstelle auf einem Front-End-Pool an Standort 1 zusammengefasst. Die Vermittlungsserver an Standort 1 Steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die medienumgehung Global für die Verwendung von Standort-und Regionsinformationen aktiviert, und für die Trunks zu jedem PSTN-Gateway (GW1 und GW2) ist die Umgehung aktiviert.

**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![VoIP-Topologie mit Vermittlungsserver WAN-Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "VoIP-Topologie mit Vermittlungsserver WAN-Gateway")

Die folgende Abbildung zeigt eine einfache Topologie, in der der Vermittlungsserver mit der Registrierungsstelle auf Front-End-Pool an Standort 1 zusammenhängt und über eine direkte SIP-Verbindung mit der IP-Nebenstellenanlage an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungsserver auch ein PSTN-Gateway an Standort 2. Es wird davon ausgegangen, dass lync-Benutzer an beiden Standorten 1 und 2 vorhanden sind. Nehmen Sie außerdem an, dass die IP-Nebenstellenanlage über einen zugeordneten medienprozessor verfügt, der von allen Medien aus lync-Endpunkten durchlaufen werden muss, bevor Sie an Medien Endpunkte gesendet werden, die von der IP-Nebenstellenanlage gesteuert werden. In dieser Topologie ist die medienumgehung Global für die Verwendung von Standort-und Regionsinformationen aktiviert, und für die Trunks für die Nebenstellenanlage und das PSTN-Gateway ist die medienumgehung aktiviert.

**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![VoIP-Topologie Vermittlungsserver WAN-Nebenstellenanlage](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "VoIP-Topologie Vermittlungsserver WAN-Nebenstellenanlage")

Ausführliche Informationen zur Planung von PBX-Topologien finden Sie unter [Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) und [direkte SIP-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der die Vermittlungsserver mit dem SBC eines Internet Telefonie-Dienstanbieters verbunden ist. Ausführliche Informationen zu SIP-Trunk Topologien finden Sie unter [SIP-Trunking in lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

