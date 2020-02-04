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
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Bewährte Methoden für Ihre Kerninfrastruktur in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-27_

Sie haben wahrscheinlich bereits Schritte unternommen, um Fehlertoleranz in Ihrem System zu entwerfen, und Verfahren wie das Sicherstellen von Hardwareredundanz, Schutzmaßnahmen gegen Stromausfälle, Routineinstallation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server-Aktivitäten verwendet. Diese Vorgehensweisen nutzen nicht nur Ihre Microsoft lync Server 2013-Infrastruktur, sondern auch Ihr gesamtes Netzwerk. Wenn Sie diese Methoden nicht implementiert haben, empfiehlt es sich, dies vor der Bereitstellung von lync Server 2013 zu tun.

Gehen Sie wie folgt vor, um die Server in ihrer lync Server 2013-Bereitstellung vor versehentlichen oder zielgerichteten Verletzungen zu schützen, die zu Ausfallzeiten führen können:

  - Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand. Mit einem Abonnement für den Microsoft Security Notification Service können Sie sicherstellen, dass Sie bei Veröffentlichungen von Sicherheitsbulletins für alle Microsoft-Produkte sofort benachrichtigt werden. Wenn Sie sich anmelden möchten, wechseln Sie zur Microsoft Technical Security [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Notifications-Website unter.

  - Achten Sie darauf, dass Zugriffsrechte ordnungsgemäß eingerichtet sind.

  - Stellen Sie Ihre Server in einer physischen Umgebung auf, die einen nicht autorisierten Zugriff verhindert. Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist. Halten Sie die Software mit den neuesten Virussignaturdateien auf dem neuesten Stand. Verwenden Sie die Funktion für automatische Updates Ihrer Antivirenanwendung, um die Virussignaturen aktuell zu halten.

  - Wir empfehlen, dass Sie die Windows Server-Betriebssystemdienste deaktivieren, die auf den Computern, auf denen Sie lync Server 2013 installieren, nicht erforderlich sind.

  - Verschlüsseln Sie Betriebssysteme und Festplattenlaufwerke, auf denen Daten gespeichert sind, mit einem Verschlüsselungssystem für das gesamte Volume, es sei denn, Sie können eine beständige und vollständige Kontrolle der Server, vollkommene physische Isolation und das ordnungsgemäße und sichere Außerbetriebsetzen von ausgetauschten oder ausgefallenen Festplattenlaufwerken sicherstellen.

  - Deaktivieren Sie alle externen Ports für den direkten Speicherzugriff des Servers, es sei denn, Sie können eine sehr enge Kontrolle des physischen Zugriffs auf die Server sicherstellen. Angriffe auf der Basis von direktem Speicher, die realtiv einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel offenlegen.

</div>

<span> </span>

</div>

</div>

</div>

