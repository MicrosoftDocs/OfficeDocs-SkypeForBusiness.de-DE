---
title: Migrieren des XMPP-Verbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761b0835eb8c1db84b8b969479ad329e7f75e033
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrieren des XMPP-Verbunds

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

In früheren Versionen von Office Communications Server wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Server Rolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen. In lync Server 2013 kann die XMPP-Funktionalität als Feature bereitgestellt werden. Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem lync Server 2013 Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem lync Server 2013 Front-End-Server ausgeführt wird.

Aus Migrations Sicht kann ein Office Communications Server 2007 R2 Benutzerkonto in einen lync Server 2013 Pool verschoben werden und weiterhin das Office Communications Server 2007 R2 XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in lync Server 2013 konfiguriert ist.

Zusammenfassend lässt sich feststellen, ob Office Communications Server mit dem Office Communications Server 2007 R2 XMPP-Gateway und dem XMPP-Verbund bereitgestellt wurde, für ältere Office Communications Server 2007 R2-Benutzer aktiviert wurde, um den XMPP-Verbund zu lync Server 2013 zu migrieren:

1.  Bereitstellen eines lync Server 2013 Pools.

2.  Bereitstellen eines lync Server 2013-Edge-Servers

3.  Verschiebt alle Benutzer in den lync Server 2013 Pool.

4.  Erstellen Sie XMPP-Zugriffsrichtlinien und -Zertifikate für den Edgeserver.

5.  Aktivieren Sie XMPP-Verbund in lync Server 2013. 

6.  Aktualisieren Sie die DNS-Einträge so, dass Sie auf das lync Server 2013 XMPP-Gateway verweist.

</div>

<span> </span>

</div>

</div>

</div>

