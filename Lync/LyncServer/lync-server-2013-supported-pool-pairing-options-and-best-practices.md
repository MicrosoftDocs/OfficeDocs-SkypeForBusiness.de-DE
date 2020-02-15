---
title: Lync Server 2013 unterstützte Optionen für das Pool koppeln und bewährte Methoden
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
ms.openlocfilehash: 963f1532ca7a1aa5402a54936909a22727ab9716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Unterstützte Optionen für das Pool koppeln und bewährte Methoden für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-09_

Die Entfernung zwischen zwei Rechenzentren, die als Paar bereitgestellte Front-End-Pools enthalten sollen, ist nicht begrenzt. Wir empfehlen die Verwendung zweier Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindung. Die Rechenzentren sollen weit genug voneinander entfernt sein, damit sie nicht gleichzeitig von einem Notfall betroffen sein können.

Die Verwendung zweier Rechenzentren in verschiedenen Weltregionen ist zwar möglich, führt jedoch u. U. zu größeren Datenverlusten aufgrund von Wartezeiten bei der Datenreplikation.

Wenn Sie planen, welche Pools gekoppelt werden sollen, müssen Sie beachten, dass nur die folgenden Paarungen unterstützt werden:

  - Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.

  - Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.

  - Für Pools, die zusammen gekoppelt sind, muss das gleiche Betriebssystem installiert sein.

Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Typen von Kopplungen werden jedoch nicht unterstützt.

Jeder Pool in einem Paar sollte über ausreichend Kapazität verfügen, um bei einem Notfall alle Benutzer zu bedienen.

Wenn Sie Enterprise Edition-Pools paaren, können Sie auch auf den Back-End-Servern hohe Verfügbarkeit bereitstellen; bei Paaren aus Standard Edition-Pools stehen jedoch nur die Notfallwiederherstellungsmaßnahmen zur Verfügung.

</div>

<span> </span>

</div>

</div>

</div>

