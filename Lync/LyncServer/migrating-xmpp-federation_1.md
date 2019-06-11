---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

In früheren Versionen von Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. In lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem lync Server 2013-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem lync Server 2013-Front-End-Server ausgeführt wird.

Aus Sicht der Migration kann ein Office Communications Server 2007 R2-Benutzerkonto in einen lync Server 2013-Pool verschoben und weiterhin das Office Communications Server 2007 R2 XMPP-Gateway verwendet werden. Dies ist nur möglich, wenn der XMPP-Verbundpartner nicht in lync Server 2013 konfiguriert ist.

Zusammenfassung: Wenn Office Communications Server mit dem Office Communications Server 2007 R2 XMPP-Gateway bereitgestellt wurde und die XMPP-Föderation für Legacy Office Communications Server 2007 R2-Benutzer aktiviert wurde, können Sie die XMPP-Föderation zu lync Server 2013 migrieren:

1.  Bereitstellen eines lync Server 2013-Pools

2.  Bereitstellen eines lync Server 2013-Edgeserver

3.  Verschieben Sie alle Benutzer in den lync Server 2013-Pool.

4.  Erstellen Sie XMPP-Zugriffsrichtlinien und-Zertifikate für den Edgeserver.

5.  Aktivieren Sie die XMPP-Föderation in lync Server 2013. 

6.  Aktualisieren Sie die DNS-Einträge so, dass Sie auf das lync Server 2013 XMPP-Gateway verweisen.

</div>

<span> </span>

</div>

</div>

</div>

