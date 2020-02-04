---
title: Lync Server 2013 unterstützte Pool-Kopplungs Optionen und bewährte Methoden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Unterstützte Pool-Kopplungs Optionen und bewährte Methoden für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Es gibt keine Einschränkung für den Abstand zwischen zwei Rechenzentren, in denen Front-End-Pools miteinander kombiniert werden. Wir empfehlen, dass Sie zwei Rechenzentren in der gleichen Weltregion verwenden, mit Hochgeschwindigkeits-Links zwischen Ihnen. Am besten ist es, wenn die beiden Rechenzentren voneinander getrennt sind, um zu verhindern, dass ein einzelner Notfall gleichzeitig anschlägt.

Die Möglichkeit, zwei Rechenzentren in verschiedenen Weltregionen zu nutzen, kann aufgrund der Latenz bei der Datenreplikation zu einem höheren Datenverlust führen.

Beachten Sie bei der Planung, welche Pools als Paar bereitgestellt werden, dass nur die folgenden Paarungen unterstützt werden:

  - Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.

  - Physische Pools können nur mit anderen physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.

  - Für Pools, die zusammen gekoppelt sind, muss dasselbe Betriebssystem ausgeführt werden.

Eine Paarung zweier Pools, die nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Art von Paarung wird jedoch nicht unterstützt.

Jeder Pool in einem Paar sollte in der Lage sein, alle Benutzer aus beiden Pools im Fall eines Notfalls zu bedienen.

Wenn Sie Enterprise Edition-Pools koppeln, können Sie auch eine höhere Verfügbarkeit auf den Back-End-Servern implementieren, bei Paaren von Standard Edition-Pools sind jedoch nur die Wiederherstellungsmaßnahmen zur Verfügung.

</div>

<span> </span>

</div>

</div>

</div>

