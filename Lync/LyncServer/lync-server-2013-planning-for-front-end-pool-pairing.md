---
title: 'Lync Server 2013: Planen der Front-End-Pool Kopplung'
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
ms.openlocfilehash: 10d45434bf34cc5e7e158039851e8a7fb2cbd6e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planen der Front-End-Pool Kopplung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Für die besten Möglichkeiten zur Notfallwiederherstellung in lync Server 2013 stellen Sie Paare von Front-End-Pools auf zwei geografisch verteilten Standorten bereit. Jede Website enthält eine Front-End-Pool, die mit einem entsprechenden Front-End-Pool am anderen Standort gekoppelt ist. Beide Standorte sind aktiv, und der lync Server Sicherungsdienst bietet eine Echtzeitdaten Replikation, damit die Pools synchronisiert bleiben. Der Sicherungsdienst ist ein neues Feature in lync Server 2013, das zur Unterstützung der Notfallwiederherstellungslösung entwickelt wurde. Sie wird auf einem Front-End-Pool installiert, wenn Sie den Pool mit einem anderen Front-End-Pool koppeln.

Wenn für den Pool an einem Standort ein Fehler auftritt, können Sie die Benutzer aus diesem Pool mit dem Pool im anderen Standort verfallen, der dann für alle Benutzer in beiden Pools Dienste bereitstellt. Für Kapazitäts Planungszwecke sollte jeder Pool so konzipiert sein, dass er die Arbeitslasten aller Benutzer in beiden Pools im Falle eines Notfalls behandelt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Unterstützte Optionen für das Pool koppeln und bewährte Methoden für lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Sicherungs Registrierungs Beziehungen in lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Wiederherstellungszeit für Pool-Failover und Pool-Failback in lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover des zentralen Verwaltungsspeichers in lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Front-End-Pool koppeln von Datensicherheit in lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

