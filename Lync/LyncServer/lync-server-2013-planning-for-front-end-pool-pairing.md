---
title: 'Lync Server 2013: Planen der Bildung von Front-End-Poolpaaren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planen der Bildung von Front-End-Poolpaaren in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Stellen Sie für die besten Möglichkeiten zur Disaster Recovery in lync Server 2013 Paare von Front-End-Pools auf zwei geografisch verteilten Websites bereit. Jede Website enthält einen Front-End-Pool, der mit einem entsprechenden Front-End-Pool in der anderen Website gekoppelt ist. Beide Websites sind aktiv, und der lync Server-Sicherungsdienst bietet Echtzeitdaten Replikation, damit die Pools synchronisiert bleiben. Der Sicherungsdienst ist ein neues Feature in lync Server 2013, das zur Unterstützung der Disaster Recovery-Lösung entwickelt wurde. Sie wird in einem Front-End-Pool installiert, wenn Sie den Pool mit einem anderen Front-End-Pool koppeln.

Wenn der Pool auf einer Website fehlschlägt, können Sie die Benutzer aus diesem Pool in den Pool auf der anderen Website übertragen, wodurch Dienste für alle Benutzer in beiden Pools bereitgestellt werden. Bei der Kapazitätsplanung sollte jeder Pool so konzipiert sein, dass er die Arbeitslasten aller Benutzer in beiden Pools im Fall eines Notfalls behandelt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Unterstützte Pool-Kopplungs Optionen und bewährte Methoden für lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover des zentralen Verwaltungsspeichers in Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

