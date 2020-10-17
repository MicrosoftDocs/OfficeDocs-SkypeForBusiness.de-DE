---
title: 'Lync Server 2013: Betriebssystemunterstützung für Server und Tools'
description: 'Lync Server 2013: Betriebssystemunterstützung für Server und Tools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67cf2e39e0c8f9e66f755b16be03af37dd9a946e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555151"
---
# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a>Betriebssystemunterstützung für Server und Tools in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-01_

Lync Server 2013 ist nur in 64-Bit verfügbar, was 64-Bit-Hardware und 64-Bit-Editionen von Windows Server erfordert. Dies bedeutet, dass alle Serverrollen und Computer, auf denen lync Server 2013 Verwaltungstools ausgeführt werden, ein 64-Bit-Edition-Betriebssystem ausführen.

<div>

## <a name="operating-systems-for-server-roles"></a>Betriebssysteme für Serverrollen

Lync Server 2013 unterstützt die 64-Bit-Editionen der folgenden Betriebssysteme für alle Server Rollen in lync Server 2013:

  - Die Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Das Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Das Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)

  - Das Windows Server 2012 Standard-Betriebssystem

  - Das Betriebssystem des Windows Server 2012-Rechenzentrums

  - Die Windows Server 2012 R2-Betriebssysteme werden mit den kumulativen Updates für lync Server 2013: Oktober 2013 unterstützt.

Lync Server 2013 wird für Folgendes nicht unterstützt:

  - Die Server Core-Installationsoption von Windows Server 2008 R2 oder Windows Server 2012

  - Dem Betriebssystem Windows Web Server 2008 R2 oder Windows Web Server 2012

  - Windows Server 2008 R2 HPC-Edition oder Windows Server 2012 HPC-Edition

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a>Weitere Betriebssysteme für Verwaltungstools

Lync Server 2013 Verwaltungstools werden standardmäßig auf Servern mit lync Server 2013 installiert, aber Sie können Verwaltungstools separat auf anderen Computern installieren, auf denen Windows-Betriebssysteme verwendet werden. Dazu gehören die folgenden 64-Bit-Versionen der folgenden Betriebssysteme, zusätzlich zu den 64-Bit-Editionen der Betriebssysteme, die für die Bereitstellung von Serverrollen unterstützt werden (wie im vorherigen Abschnitt beschrieben).

  - Das Betriebssystem Windows 7 Betriebssystem mit SP1 (erforderlich) oder neuestes Service Pack (empfohlen)

  - Das Windows 8 Betriebssystem oder das neueste Service Pack (empfohlen)

  - Das Windows 8.1 Betriebssystem oder das neueste Service Pack (empfohlen)

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a>Betriebssysteme für andere Server in Ihrer Bereitstellung

  - Ausführliche Informationen zu den Anforderungen für Back-End-Server und andere Datenbankserver finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md).

  - Ausführliche Informationen zu den Anforderungen für Reverse-Proxy Server (für die Edge-Bereitstellung) finden Sie unter [IIS-Unterstützung in lync Server 2013](lync-server-2013-iis-support.md).

  - Ausführliche Informationen zu anderen Softwareanforderungen, einschließlich Infrastruktur und Unterstützung der Virtualisierung, finden Sie in den anderen Themen unter [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

