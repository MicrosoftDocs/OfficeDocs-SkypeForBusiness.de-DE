---
title: 'Lync Server 2013: Topologieänderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Topologieänderungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Topologie-Anforderungen und-Überlegungen für lync Server 2013 unterscheiden sich von denen für frühere Versionen, wie in diesem Abschnitt beschrieben.

<div>

## <a name="new-front-end-pools-architecture"></a>Neue Front-End-Pools-Architektur

In lync Server 2013 wurde die Architektur von Enterprise Edition-Front-End-Pools in eine verteilte Systemarchitektur geändert.

Mit dieser neuen Architektur ist die Back-End-Datenbank nicht mehr der Echtzeitdaten Speicher in einem Pool. Informationen zu einem bestimmten Benutzer werden auf drei Front-End-Servern im Pool aufbewahrt. Für jeden Benutzer fungiert ein Front-End-Server als Master für die Informationen dieses Benutzers, und zwei weitere Front-End-Server dienen als Replikate. Wenn ein Front-End-Server ausfällt, wird ein anderer Front-End-Server, der als Replikat fungiert, automatisch zum Master heraufgestuft.

Dies geschieht hinter den Kulissen, und Administratoren müssen nicht wissen, welche Front-End-Server die Master für welche Benutzer sind. Diese Verteilung der Datenspeicherung verbessert die Leistung und Skalierbarkeit innerhalb des Pools und beseitigt den einzelnen Fehlerpunkt eines einzelnen Back-End-Servers.

Der Back-End-Server dient als Sicherungsspeicher für Benutzer-und Konferenzdaten und ist auch der primäre Speicher für andere Datenbanken wie die Datenbank der Reaktionsgruppe.

Diese Verbesserungen besagen auch, dass es Änderungen bei der Planung und Verwaltung Ihrer Pools gibt. Wir empfehlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server umfassen, um die vollständige Anzahl von Replikaten bereitzustellen, für die die Front-End-Pool-Architektur konzipiert ist. Darüber hinaus müssen Sie bestimmte Verfahren ausführen, wenn Sie einem Front-End-Pool Server hinzufügen, Server davon entfernen oder Server aktualisieren. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Änderungen der Server Rollen Topologie

Einige Serverrollen, die zuvor auf separaten Servern ausgeführt wurden, werden jetzt in der Front-End-Serverrolle konsolidiert, sodass Sie die Hardwarekosten sparen können.

  - In lync Server 2013 ist der A/V-Konferenzserver immer mit dem Front-End-Server verbunden.

  - Die Front-Ends für Überwachung und Archivierung sind jetzt immer mit dem Front-End-Server verbunden. Für die Überwachung und Archivierung ist immer noch eine separate Back-End-Datenbank erforderlich, die sich auf demselben Server wie die Back-End-Datenbank des Front-End-Pools befindet oder auf separaten Back-End-Servern gehostet werden kann.

  - Der beständige Chat Server ist nun eine Serverrolle. In Microsoft lync Server 2010 war der Gruppen-Chat Server eine vertrauenswürdige Anwendung eines Drittanbieters für Microsoft lync Server 2010. In lync Server 2013 wird die Funktion des beständigen Chat Servers mit drei neuen Serverrollen implementiert:
    
      - **PersistentChatService:** Die wichtigsten Server Dienste für beständigen Chat, die als Front-End-Rolle implementiert sind
    
      - **PersistentChatStore:** Back-End-Server Rolle
    
      - **PersistentChatComplianceStore:** Back-End-Server Rolle für beständigen Chat

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

