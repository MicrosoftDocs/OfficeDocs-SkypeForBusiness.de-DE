---
title: Überlegungen zur Koexistenz
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7502e74eb1bb4c2a5e7889fc46cb4419101bf4a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Überlegungen zur Koexistenz

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Nach der Migration ist nur ein lync Server 2013 Server Pool für beständigen Chat vorhanden, und Sie können Ihre Legacy-Bereitstellung außer Betrieb nehmen.

Bevor die Migration abgeschlossen ist und Sie Ihre aktuelle Gruppen Chat Server-Bereitstellung vollständig außer Betrieb genommen haben, haben Sie möglicherweise eine der folgenden Bereitstellungen:

  - Lync Server 2013 Server Pool für beständigen Chat, der in einem lync Server 2013-Pool verwaltet werden muss.

  - Lync Server 2010 Gruppen Chat Pool, der in einem lync Server 2010-Pool verwaltet werden muss.

  - Office Communications Server 2007 R2 Gruppen Chat-Pool, der in einem Office Communications Server 2007 R2-Pool verwaltet werden muss.

Diese Bereitstellungen können nebeneinander vorhanden sein. Die Kategorien, Chatrooms und Add-ins in einer Bereitstellung interagieren nicht mit denen einer anderen Bereitstellung.

Mithilfe der manuellen Konfiguration kann ein Legacyclient (Gruppenchatclient) gleichzeitig eine Verbindung mit einem Pool für Office Communications Server 2007 R2, lync Server 2010, Gruppenchat oder lync Server 2013 herstellen.

Der lync 2013 (Client) kann nur mit dem Serverpool für lync Server 2013, beständigen Chat und nicht mit Legacy-Gruppen Chat Server-Pools interagieren. Damit der beständige Chat in einem lync 2013 (Client) verwendet werden kann, muss der Benutzer in lync 2013 verwaltet werden und durch eine Richtlinie aktiviert sein.

</div>

<span> </span>

</div>

</div>

</div>

