---
title: 'Lync Server 2013: Planen des Zugriffs durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3068cae2545c0d3f1df3f04935914d21d032ffc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522182"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planen des Zugriffs durch externe Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-19_

Die Kommunikation beinhaltet in den meisten Organisationen Dienste und Benutzer, die sich nicht innerhalb des internen Netzwerks befinden. Diese Dienste und Benutzer umfassen Mitarbeiter, die zeitweise oder dauerhaft außerhalb des Standorts arbeiten, Mitarbeiter von Kunden- oder Partnerorganisationen, Benutzer von öffentlichen Instant Messaging-Diensten (IM) sowie potenzielle Kunden, Partner und anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen möchten. Diese Benutzer werden in dieser Dokumentation kollektiv als *externe Benutzer* bezeichnet.

Mit Microsoft lync Server 2013 können Benutzer in Ihrer Organisation Chat und Anwesenheitsinformationen verwenden, um mit externen Benutzern zu kommunizieren, und Sie können an Audio/Video-Konferenzen und-Webkonferenzen mit Ihren externen Mitarbeitern und anderen Typen externer Benutzer teilnehmen. Sie können auch den externen Zugriff von mobilen Geräten und über Enterprise-VoIP unterstützen. Externe Benutzer, die nicht Mitglied Ihrer Organisation sind, können an lync Server 2013 Besprechungen teilnehmen und anonyme Teilnehmer zulassen.

Um die Kommunikation über die Firewall Ihrer Organisation hinweg zu unterstützen, stellen Sie lync Server 2013 Edgeserver in Ihrem Umkreisnetzwerk bereit (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet). Die Edgeserver steuert, wie Benutzer außerhalb der Firewall eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herstellen können. Der Edgeserver steuert darüber hinaus die Kommunikation von Benutzern innerhalb der Firewall mit externen Benutzern.

Je nach Ihren Anforderungen können Sie einen oder mehrere Edgeserver an einem oder mehreren Standorten bereitstellen. In diesem Abschnitt werden Szenarien für den Zugriff durch externe Benutzer in lync Server 2013 beschrieben, und es wird erläutert, wie Sie die Edge-und Reverse-Proxy Topologie planen.

<div>


> [!NOTE]  
> Sie benötigen zwar eine Edgeserver zur Unterstützung von Enterprise-VoIP und externer Benutzer Zugriff, dieser Abschnitt konzentriert sich jedoch auf die Unterstützung von Sofortnachrichten, Anwesenheitsinformationen, A/V-Konferenzen, Verbund, Webkonferenzen und lync Mobile. Ausführliche Informationen zur Unterstützung von Enterprise-VoIP finden Sie unter <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Übersicht über den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Grundlegendes zur AutoErmittlung in lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Auswählen einer Topologie in lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Datensammlung in lync Server 2013](lync-server-2013-data-collection.md)

  - [Bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

