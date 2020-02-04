---
title: 'Lync Server 2013: Beziehungen von Sicherungsregistrierungsstellen'
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
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-28_

Neben der Notfallwiederherstellung dienen die verbundenen Pools als Sicherungsregistrierungsstellen füreinander. In lync Server 2013 sind Sicherungs Registrierungsstellen Beziehungen zwischen Front-End-Pools immer 1:1 und wechselseitig. Dies bedeutet Folgendes: Wenn P1 die Sicherung für P2 ist, muss P2 die Sicherung für P1 sein, und es kann auch keine Sicherung für einen anderen Front-End-Pool sein. Hierbei handelt es sich um eine Änderung von lync Server 2010, bei der Backup-Beziehungen im Front-End-Pool viel zu eins sein können.

Auch wenn die Sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool weiterhin als Sicherungs Registrierungsstelle für eine beliebige Anzahl von Überlebenden Branch-Appliances, wie in lync Server 2010, eingesetzt werden.

Beachten Sie, dass lync Server 2013 die Disaster Recovery-Unterstützung nicht für Benutzer ausdehnt, die auf einer Survivable Branch-Appliance verwaltet werden. Wenn ein Front-End-Pool, der als Sicherung für eine Survivable Branch-Appliance dient, herunterfällt, fallen Benutzer, die bei der Survivable Branch-Appliance angemeldet sind, in den Stabilitäts Modus, auch wenn Benutzer im Front-End-Pool über einen Failover zum Backup-Front-End-Pool verstoßen haben.

</div>

<span> </span>

</div>

</div>

</div>

