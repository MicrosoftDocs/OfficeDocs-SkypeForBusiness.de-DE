---
title: 'Lync Server 2013: bewährte Methoden für Ihre Kerninfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce25a61ef74c38b5455b7b8d437b43d24e12397e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Bewährte Methoden für Ihre Kerninfrastruktur in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-27_

Wahrscheinlich haben Sie bereits Schritte zum Entwerfen der Fehlertoleranz in Ihrem System unternommen, indem Sie Verfahren wie die Sicherstellung der Hardwareredundanz, das Schützen von Stromverlust, die regelmäßige Installation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server Aktivitäten verwenden. Diese Vorgehensweisen bieten nicht nur Ihrer Microsoft lync Server 2013 Infrastruktur, sondern auch Ihrem gesamten Netzwerkvorteile. Wenn Sie diese Vorgehensweisen nicht implementiert haben, sollten Sie dies vor der Bereitstellung von lync Server 2013 tun.

Um die Server in ihrer lync Server 2013-Bereitstellung vor versehentlicher oder zielgerichteter Beschädigung zu schützen, die zu Ausfallzeiten führen können, sollten Sie die folgenden Vorkehrungen treffen:

  - Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Durch das Abonnieren des Microsoft-Sicherheitsbenachrichtigungsdiensts können Sie sicherstellen, dass Sie Sofortbenachrichtigungen über Sicherheitsbulletins für ein beliebiges Microsoft-Produkt erhalten. Um sich anzumelden, wechseln Sie zur Microsoft Technical Security Notifications-Website unter [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).

  - Stellen Sie sicher, dass die Zugriffsrechte ordnungsgemäß eingerichtet sind.

  - Halten Sie Ihre Server in einer physischen Umgebung, die unbefugten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software stets mit den neuesten Virensignaturdateien auf dem aktuellen Stand. Verwenden Sie das Feature für automatische Aktualisierungen der Antivirenanwendung, um die Virensignaturen auf dem neuesten Stand zu halten.

  - Es wird empfohlen, dass Sie die Windows Server-Betriebssystemdienste deaktivieren, die auf den Computern, auf denen Sie lync Server 2013 installieren, nicht erforderlich sind.

  - Verschlüsseln von Betriebssystemen und Laufwerken, auf denen Daten mit einem Verschlüsselungssystem mit voller Lautstärke gespeichert werden, es sei denn, Sie können eine ständige und vollständige Kontrolle über die Server, die gesamte physische Isolierung und die ordnungsgemäße und sichere Außerbetriebnahme von ersetzten oder ausgefallenen Datenträgern garantieren Laufwerke.

  - Deaktivieren Sie alle externen DMA-Ports (Direct Memory Access) des Servers, es sei denn, Sie können eine sehr strenge Kontrolle über den physischen Zugriff auf die Server garantieren. DMA-basierte Angriffe, die relativ einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel verfügbar machen.

</div>

<span> </span>

</div>

</div>

</div>

