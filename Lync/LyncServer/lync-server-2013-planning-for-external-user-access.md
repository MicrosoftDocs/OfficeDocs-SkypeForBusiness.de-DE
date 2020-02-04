---
title: 'Lync Server 2013: Planen des Zugriffs externer Benutzer'
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
ms.openlocfilehash: 17d38abe775a915fc3357610ad2b741eb0e77628
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planen des Zugriffs externer Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-19_

Die Kommunikation in den meisten Organisationen umfasst Dienste und Benutzer, die sich nicht in Ihrem internen Netzwerk befinden. Zu diesen Diensten und Benutzern gehören Mitarbeiter, die vorübergehend oder dauerhaft extern sind, Mitarbeiter von Kunden-oder Partnerorganisationen, Personen, die öffentliche Instant Messaging-Dienste (im) verwenden, und potenzielle Kunden, Partner und anonyme Benutzer, die Sie einladen zu Besprechungen und Präsentationen. In dieser Dokumentation werden diese Personen gemeinsam als *externe Benutzer*bezeichnet.

Mit Microsoft lync Server 2013 können Benutzer in Ihrer Organisation Chats und Anwesenheitsinformationen für die Kommunikation mit externen Benutzern verwenden, und Sie können an Audio/Video-Konferenzen und Webkonferenzen mit Ihren externen Mitarbeitern und anderen Typen externer Benutzer teilnehmen. Sie können auch externen Zugriff von mobilen Geräten und über Enterprise-VoIP unterstützen. Externe Benutzer, die keine Mitglieder Ihrer Organisation sind, können an lync Server 2013-Besprechungen teilnehmen und anonyme Teilnehmer zulassen.

Um die Kommunikation in der Firewall Ihrer Organisation zu unterstützen, stellen Sie den lync Server 2013-Edgeserver in Ihrem Umkreisnetzwerk bereit (auch bekannt als DMZ, demilitarisierte Zone und abgeschirmtes Subnetz). Der Edgeserver steuert, wie Benutzer außerhalb der Firewall eine Verbindung mit ihrer internen lync Server 2013-Bereitstellung herstellen können. Außerdem steuert Sie die Kommunikation mit externen Benutzern, die innerhalb der Firewall entstehen.

Je nach Ihren Anforderungen können Sie einen oder mehrere Edgeserver an einem oder mehreren Speicherorten bereitstellen. In diesem Abschnitt werden Szenarien für den Zugriff durch externe Benutzer in lync Server 2013 beschrieben, und es wird erläutert, wie Sie Ihre Edge-und Reverse-Proxy Topologie planen.

<div>


> [!NOTE]  
> Obwohl Sie einen Edgeserver zur Unterstützung von Enterprise-VoIP und externem Benutzer Zugriff benötigen, konzentriert sich dieser Abschnitt auf die Unterstützung für Chat, Anwesenheit, A/V-Konferenzen, Föderation, Webkonferenzen und lync Mobile. Details zur Unterstützung von Enterprise-VoIP finden Sie unter <A href="lync-server-2013-planning-for-enterprise-voice.md">Planen von Enterprise-VoIP in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Systemanforderungen für Komponenten für den Zugriff durch externe Benutzer für Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Übersicht über den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Grundlegendes zu AutoErmittlung in lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Auswählen einer Topologie in Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Datenerfassung in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

