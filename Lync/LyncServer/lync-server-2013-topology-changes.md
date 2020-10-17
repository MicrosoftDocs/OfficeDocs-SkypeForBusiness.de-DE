---
title: Lync Server 2013 von Topologie-Änderungen
description: Lync Server 2013 Topologie ändert sich.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549101"
---
# <a name="topology-changes-in-lync-server-2013"></a>Topologie-Änderungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Topologie-Anforderungen und Überlegungen für lync Server 2013 unterscheiden sich von denen für frühere Versionen, wie in diesem Abschnitt beschrieben.

<div>

## <a name="new-front-end-pools-architecture"></a>Neue Architektur der Front-End-Pools.

In lync Server 2013 wurde die Architektur von Enterprise Edition-Front-End-Pools in eine verteilte Systemarchitektur geändert.

Mit dieser neuen Architektur bildet die Back-End-Datenbank nicht mehr den Echtzeit-Datenspeicher in einem Pool. Die Informationen zu einem bestimmten Benutzer befinden sich auf drei Front-End-Servern im Pool. Für jeden Benutzer agiert ein Front-End-Server als Master für die Informationen des jeweiligen Benutzers und zwei weitere Front-End-Server dienen als Replikate. Wenn ein Front-End-Server ausfällt, wird ein anderer Front-End-Server, der als Replikat gedient hat, automatisch zum Master hochgestuft.

Dies passiert im Hintergrund und es ist nicht erforderlich, dass Administratoren wissen, welche Front-End-Server als Master für welche Benutzer agieren. Diese Verteilung der Datenspeicherung verbessert die Leistung und Skalierbarkeit innerhalb des Pools und eliminiert den einzelnen Ausfallpunkt eines einzelnen Back-End-Servers.

Der Back-End-Server dient als Sicherungsspeicher für Benutzer- und Konferenzdaten und stellt außerdem den primären Speicher für andere Datenbanken, wie die Reaktionsgruppendatenbank.

Diese Verbesserungen ziehen auch Änderungen bei der Planung und Wartung der Pools nach sich. Es wird empfohlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten, um die vollständige Anzahl von Replikaten bereitzustellen, für die die Front-End-Pool Architektur ausgelegt ist. Darüber hinaus müssen Sie beim Hinzufügen von Servern zu einer Front-End-Pool, beim Entfernen von Servern oder beim Aktualisieren von Servern bestimmte Verfahren befolgen. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Änderungen der Topologie der Serverrolle

Einige Serverrollen, die zuvor auf separaten Servern ausgeführt wurden, sind jetzt in der Front-End-Serverrolle zusammengefasst, was die Hardwarekosten senkt

  - In lync Server 2013 ist A/V-Konferenzserver immer mit Front-End-Server verbunden.

  - Die Front-Ends für die Überwachung und für die Archivierung sind jetzt mit dem Front-End-Server verbunden. Für die Überwachung und die Archivierung ist weiterhin eine separate Back-End-Datenbank erforderlich, die auf demselben Server wie die Back-End-Datenbank des Front-End-Pools verbunden oder auf separaten Back-End-Servern gehostet werden kann.

  - Der Server für beständigen Chat ist jetzt eine Serverrolle. In Microsoft lync Server 2010 war der Gruppen Chat Server eine vertrauenswürdige Drittanbieteranwendung für Microsoft lync Server 2010. In lync Server 2013 wird die Server Funktionalität für beständigen Chat mit drei neuen Serverrollen implementiert:
    
      - **PersistentChatService:** Haupt Server Dienste für beständigen Chat, die als Front-End-Rolle implementiert sind
    
      - **PersistentChatStore:** Back-End-Server Rolle
    
      - **PersistentChatComplianceStore:** Back-End-Server Rolle für die Compliance für beständigen Chat

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

