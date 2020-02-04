---
title: 'Lync Server 2013: Überprüfen des Topologieentwurfs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Überprüfen des Topologieentwurfs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-01-02_

Der Topologie-Generator überprüft die Topologie automatisch. Jeder topologiefehler wird als Überprüfungsfehler identifiziert, der durch das Symbol "Gültigkeitsprüfungsfehler" neben der Serverrolle angegeben wird. Es ist wichtig, auch zu überprüfen, ob die Topologie die Topologie für Ihre Bereitstellung richtig darstellt.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>So überprüfen Sie die Topologie vor der Veröffentlichung

1.  Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.

2.  Stellen Sie sicher, dass der SQL Server-basierte Server online und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert wurde (einschließlich aller erforderlichen Firewallregeln).

3.  Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist und die entsprechenden Berechtigungen definiert sind.

4.  Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.

5.  Stellen Sie sicher, dass die Server in den Active Directory-Domänendiensten vorhanden sind. Dies geschieht automatisch, wenn Sie die Server der Domäne beigetreten sind.

Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen. Wenn Validierungsfehler vorliegen, müssen Sie diese korrigieren, bevor Sie die Topologie veröffentlichen können. Details zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

