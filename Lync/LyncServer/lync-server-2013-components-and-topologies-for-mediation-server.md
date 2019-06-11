---
title: 'Lync Server 2013: Komponenten und Topologien für den Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In diesem Thema werden die Komponenten beschrieben, auf denen der Vermittlungsserver abhängig ist, und die Topologien, in denen der Vermittlungsserver bereitgestellt werden kann.

<div>

## <a name="dependencies"></a>Abhängigkeiten

Der Vermittlungs Server weist die folgenden Abhängigkeiten auf:

  - **Registrierungsstelle.** Erforderlich. Die Registrierungsstelle ist der nächste Hop zur Signalgebung in den Vermittlungsserver Interaktionen mit dem lync Server 2013-Netzwerk. Beachten Sie, dass der Vermittlungsserver zusammen mit der Registrierungsstelle auf einem Front-End-Server zusammengestellt werden kann, und zwar nicht nur in einem eigenständigen Pool, bestehend aus Vermittlungsservern. Die Registrierungsstelle ist mit einem Vermittlungs Server und einem PSTN-Gateway auf einer Survivable Branch-Appliance in Kontakt.

  - **Monitoring Server.** Optional, aber sehr empfehlenswert. Der Überwachungsserver ermöglicht es dem Vermittlungsserver, Qualitäts Metriken aufzuzeichnen, die seinen Mediensitzungen zugeordnet sind.

  - **Edgeserver.** Für die Unterstützung externer Benutzer erforderlich. Der Edgeserver ermöglicht es dem Vermittlungsserver, mit Benutzern zu interagieren, die sich hinter einem NAT oder einer Firewall befinden.

</div>

<div>

## <a name="topologies"></a>Topologien verfügen

Der lync Server 2013, Mediation Server ist standardmäßig mit einer Instanz der Registrierungsstelle auf einem Standard Edition-Server, einem Front-End-Pool oder einer Survivable Branch-Appliance ausgestattet. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.

Wenn die Leistung ein Problem ist, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen. Wenn Sie SIP-Trunking bereitstellen, empfehlen wir, einen eigenständigen Vermittlungs Server Pool bereitzustellen.

Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway bereitstellen, das medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich. Ein eigenständiger Vermittlungs Server Pool ist nicht erforderlich, da qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.

Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:

  - Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.

  - Die IP-PBX unterstützt keine medienumgehung, aber der Front-End-Pool, der den Vermittlungs Server hostet, kann die Sprachübertragung für Anrufe in die medienumgehung anwenden.

Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.

Details zur bereitzustellenden Topologie finden Sie unter [Bereitstellungsrichtlinien für Mediation Server in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Die folgende Abbildung zeigt eine einfache Topologie, bestehend aus zwei Websites, die über eine WAN-Verbindung verbunden sind. Der Vermittlungs Server ist mit der Registrierungsstelle an einem Front-End-Pool an Standort 1 zusammengefasst. Die Vermittlungsserver an Standort 1 Steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks für jedes PSTN-Gateway (GW1 und GW2) ist die Umgehungsfunktion aktiviert.

**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![Sprach Topologie mit dem Vermittlungs Server-WAN-Gateway] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Sprach Topologie mit dem Vermittlungs Server-WAN-Gateway")

Die nächste Abbildung zeigt eine einfache Topologie, in der der Vermittlungs Server mit der Registrierungsstelle im Front-End-Pool von Standort 1 zusammengeführt wird und über eine direkte SIP-Verbindung mit der IP-PBX-Anlage an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungs Server auch ein PSTN-Gateway an Standort 2. Angenommen, lync-Benutzer sind an beiden Standorten 1 und 2 vorhanden. Gehen Sie auch davon aus, dass die IP-PBX über einen zugeordneten medienprozessor verfügt, der von allen Medien, die von lync-Endpunkten stammen, durchlaufen werden muss, bevor Sie an Medien Endpunkte gesendet werden, die von der IP-Telefonanlage gesteuert In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks an die Telefonanlage und das PSTN-Gateway ist die medienumgehung aktiviert.

**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![Vermittlungs Server für sprach Topologie-WAN-PBX] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Vermittlungs Server für sprach Topologie-WAN-PBX")

Ausführliche Informationen zur Planung von PBX-Topologien finden Sie unter [Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) und [direkte SIP-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungs Server mit dem SBC eines Internet Telefonie-Dienstanbieters verbunden ist. Details zu den SIP-Trunk Topologien finden Sie unter [SIP-Trunking in lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

