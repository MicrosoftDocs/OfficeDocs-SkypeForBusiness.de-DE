---
title: Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Verbinden einer Survivable Branch Appliance mit einem Lync Server 2013-Front-End-Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verknüpft, der als Sicherungs Registrierungsstelle für die SBA fungiert. Wenn der Front-End-Pool auf lync Server 2013 aktualisiert wird, muss der SBA vom Front-End-Pool entfernt werden, während der Front-End-Pool aktualisiert wird. Nach dem Upgrade des Front-End-Pools kann die SBA dem Front-End-Pool erneut zugeordnet werden. Dies umfasst das Löschen des SBA aus der Topologie im Topologie-Generator und das anschließende erneute Hinzufügen des SBA zu Topology Builder. Benutzer, die in der SBA verwaltet werden, müssen in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen. Nachdem die SBA wieder zur Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden.

Nachfolgend werden die folgenden Schritte zusammengefasst:

1.  Verschieben Sie Branch-Benutzer, die in SBA beheimatet sind, in einen anderen Front-End-Pool.

2.  Entfernen Sie SBA aus Ihrer Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.

3.  Aktualisieren des Front-End-Pools auf Microsoft lync Server 2013

4.  Fügen Sie SBA wieder in Ihre Topologie ein.

5.  Ordnen Sie den neuen Front-End-Pool der SBA als Sicherungs Registrierungsstelle zu.

6.  Verschieben Sie Branch-Benutzer zurück in die SBA.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2010 Survivable Branch Appliance zu einer Topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

