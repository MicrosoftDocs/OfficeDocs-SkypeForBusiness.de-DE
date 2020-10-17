---
title: Lync Server 2013 von Sicherungs Registrierungsstellen Beziehungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd41595fed0d16327f65f4e6af39fe80c049daa4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499332"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Sicherungs Registrierungs Beziehungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-28_

Zusätzlich zur Bereitstellung von Notfallwiederherstellungsfunktionen dienen zwei gekoppelte Pools als Sicherungs Registrierungsstellen für einander. In lync Server 2013 sind Sicherungs Registrierungs Beziehungen zwischen Front-End-Pools immer 1:1 und reziproke. Das heißt, wenn P1 die Sicherung für P2 ist, muss P2 die Sicherung für P1 sein, und es kann auch keine Sicherung für andere Front-End-Pool sein. Dies ist eine Änderung gegenüber lync Server 2010, in der Front-End-Pool Sicherungsbeziehungen viele zu eins sein könnten.

Auch wenn Sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool auch die Sicherungs Registrierungsstelle für eine beliebige Anzahl von Survivable Branch Appliances sein, genau wie in lync Server 2010.

Beachten Sie, dass lync Server 2013 keine Unterstützung für die Notfallwiederherstellung für Benutzer in einem Survivable Branch Appliance erweitert. Wenn ein Front-End-Pool, das als Sicherung für eine Survivable Branch Appliance dient, ausfällt, werden Benutzer, die sich beim Survivable Branch Appliance angemeldet haben, in den Ausfall Sicherheitsmodus verfallen, auch wenn Benutzer, die sich im Front-End-Pool befinden, auf die Sicherungs Front-End-Pool Failover.

</div>

<span> </span>

</div>

</div>

</div>

