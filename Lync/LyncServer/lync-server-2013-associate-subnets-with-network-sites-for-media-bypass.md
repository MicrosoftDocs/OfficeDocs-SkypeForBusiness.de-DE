---
title: 'Lync Server 2013: Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie die globalen Einstellungen für die Medienumgehung sowie die Netzwerkregion und Netzwerkstandorte für die Medienumgehung konfiguriert haben.



</div>

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein. Anhand dieser Subnetzinformationen wird der Netzwerkstandort ermittelt, an dem sich ein Endpunkt befindet. Wenn die Standorte beider Teilnehmer einer Sitzung bekannt sind, kann die Medienumgehung das Ziel ermitteln, an das die Mediendaten zur Verarbeitung gesendet werden sollen.

Für die Medienumgehung gelten keine speziellen Anforderungen für die Zuordnung von Subnetzen zu Netzwerkstandorten. Um eine Zuordnung zwischen den Subnetzen und Netzwerkstandorten in Ihrer Topologie zu erstellen, führen Sie die Verfahren unter Zuordnen eines Subnetzes [mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)aus.

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Nächste Schritte: Erstellen von Bandbreitenrichtlinienprofilen

Nachdem Sie die Subnetze und Netzwerkstandorte für die Medienumgehung zugeordnet haben, müssen Sie mindestens ein Bandbreitenrichtlinienprofil erstellen, mit dem Subnetze für die Medienumgehung in Subnetze mit und ohne gute Konnektivität unterteilt werden. Alle Subnetze innerhalb einer Netzwerkregion mit Netzwerkstandorten, für die keine Bandbreiteneinschränkungen gelten, verfügen über eine gute Konnektivität. Für diese Subnetze kann daher die Medienumgehung verwendet werden.

Verfahren zum Konfigurieren von Bandbreitenrichtlinien Profilen finden Sie unter [Create Bandwidth Policy Profiles in lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

