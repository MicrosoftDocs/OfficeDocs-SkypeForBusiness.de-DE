---
title: Überlegungen zur Koexistenz
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0e06e5620b3b9ce81826bf623a42ec8d89c5d3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Überlegungen zur Koexistenz

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Nach der Migration wird nur ein lync Server 2013, beständiger Chat Serverpool vorhanden sein, und Sie können Ihre Legacy Bereitstellung außer Betrieb halten.

Bevor die Migration abgeschlossen ist und Sie Ihre aktuelle Gruppen-Chat Server-Bereitstellung vollständig außer Betrieb genommen haben, verfügen Sie möglicherweise über eine der folgenden Bereitstellungen:

  - Lync Server 2013, Serverpool für beständigen Chat, der in einem lync Server 2013-Pool verwaltet werden muss.

  - Lync Server 2010, Gruppen-Chat Pool, der in einem lync Server 2010-Pool verwaltet werden muss.

  - Office Communications Server 2007 R2-Gruppen-Chat-Pool, der in einem Office Communications Server 2007 R2-Pool verwaltet werden muss.

Diese Bereitstellungen können nebeneinander vorhanden sein. Die Kategorien, Räume und Add-Ins in einer Bereitstellung interagieren jedoch nicht mit denen in der zugehörigen Bereitstellung.

Mithilfe der manuellen Konfiguration kann ein Legacyclient (Gruppen-Chat-Client) eine Verbindung zu einem Pool für Office Communications Server 2007 R2, lync Server 2010, Gruppen-Chat oder lync Server 2013 herstellen.

Lync 2013 (Client) kann nur mit dem lync Server 2013, beständigen Chat Serverpool und nicht mit Legacy-Gruppen Chat Server-Pools interagieren. Zur Verwendung des beständigen Chats in einem lync 2013 (-Client) muss der Benutzer in lync 2013 gehostet und durch Richtlinie aktiviert sein.

</div>

<span> </span>

</div>

</div>

</div>

