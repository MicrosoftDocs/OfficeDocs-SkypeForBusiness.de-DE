---
title: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d23b501738010a8e5e5ed1c5c2e9a8608b0709e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Jede Survivable Branch Appliance (SBA) ist einer Front-End-Pool zugeordnet, die als Sicherungs Registrierungsstelle für die SBVg dient. Wenn das Front-End-Pool auf lync Server 2013 aktualisiert wird, muss das SBA von der Front-End-Pool entfernt werden, während das Front-End-Pool aktualisiert wird. Nachdem die Front-End-Pool aktualisiert wurde, kann die SBVg der Front-End-Pool zugeordnet werden. Dazu muss die SBA aus der Topologie im Topologie-Generator gelöscht und anschließend erneut zum Topologie-Generator hinzugefügt werden. Benutzer, die im SBA verwaltet werden, müssen in ein anderes Front-End-Pool verschoben werden, bevor Sie die SBVg aus der Topologie entfernen. Nach dem erneuten Hinzufügen der SBA zur Topologie können diese Benutzer auf die SBA zurückverschoben werden.

Die dazu erforderlichen Schritte sind im Folgenden zusammengefasst:

1.  Verlagerung von Zweigstellenbenutzern, die in SBA verwaltet werden, in eine andere Front-End-Pool.

2.  Entfernen Sie SBA aus Ihrer Topologie, um die vorhandene Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.

3.  Aktualisieren Sie Front-End-Pool auf Microsoft lync Server 2013.

4.  Fügen Sie die SBA wieder Ihrer Topologie hinzu.

5.  Ordnen Sie den neuen Front-End-Pool der SBVg als Sicherungs Registrierungsstelle zu.

6.  Verschieben Sie die Zweigstellenbenutzer zurück auf die SBA.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Hinzufügen von lync Server 2010 Survivable Branch Appliance Zweigstellen Standorts zur Topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

