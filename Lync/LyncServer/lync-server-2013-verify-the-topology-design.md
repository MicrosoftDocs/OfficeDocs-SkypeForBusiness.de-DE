---
title: 'Lync Server 2013: Überprüfen des Topologie-Designs'
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
ms.openlocfilehash: 452bd18d19fa61a0479ee8040361290b0b99d702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Überprüfen des Topologie-Designs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-01-02_

Der Topologie-Generator überprüft die Topologie automatisch. Jeder Topologiefehler wird als Überprüfungsfehler identifiziert, angegeben durch das entsprechende Fehlersymbol neben der Serverrolle. Es ist wichtig, ebenfalls sicherzustellen, dass die Topologie die gewünschte Konfiguration für Ihre Bereitstellung richtig darstellt.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>So überprüfen Sie die Topologie vor deren Veröffentlichung

1.  Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.

2.  Stellen Sie sicher, dass der SQL Server basierte Server Online ist und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert ist, einschließlich aller erforderlichen Firewallregeln.

3.  Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist, und dass die richtigen Berechtigungen definiert wurden.

4.  Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.

5.  Stellen Sie sicher, dass die Server in Active Directory-Domänendienste vorhanden sind. Dies geschieht automatisch, wenn Sie die Server der Domäne hinzugefügt haben.

Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen. Im Falle von Überprüfungsfehlern müssen Sie diese zunächst korrigieren, bevor Sie die Topologie veröffentlichen können. Ausführliche Informationen zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

