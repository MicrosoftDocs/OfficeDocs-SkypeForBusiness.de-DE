---
title: 'Lync Server 2013: Hybrid-und Split-Domain-AutoErmittlung'
description: 'Lync Server 2013: Hybrid-und Split-Domain-AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554881"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

Ein freigegebener SIP-Adressraum, auch bekannt als *geteilte Domänen* Bereitstellung oder *Hybrid* Bereitstellung, ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden. Das gewünschte Ergebnis besteht darin, dass ein Benutzer unabhängig davon, wo sich sein Heimatserver befindet (lokal oder Online), sich bei der Bereitstellung einloggt und zu seinem Standort umgeleitet wird. Um dies zu erreichen, wird das Auto Ermittlungs Feature von lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten. Sie können dies tun, indem Sie die URL (Uniform Resource Locator) der AutoErmittlung mithilfe der lync Server-Verwaltungsshell, des Cmdlets **Get-CsHostingProvider** und des Cmdlets **CsHostingProvider festlegen** konfigurieren.

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilität für die Bereitstellung geteilter Domänen

Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:

  - Geben Sie im lync Server-Verwaltungsshell
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen den Onlineanbieter mit dem Attribut **ProxyFQDN**. Beispiel: sipfed.online.lync.com.

  - Notieren Sie den Wert des ProxyFQDN.

  - Aktivieren Sie den Partnerverbund im lokalen lync Server-Systemsteuerung, sodass der Verbund mit dem Onlineanbieter zugelassen wird.

  - Aktivieren Sie den Partnerverbund für den Onlineanbieter. Standardmäßig sind alle Online Benutzer für den Domänen Verbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie blockierte und zugelassene Domänen definieren, bestimmen Sie die Domänen, die Sie explizit zulassen oder explizit blockieren.

  - Für den Online Verbund müssen Sie Firewall-Ausnahmen, Zertifikate und DNS-Hosteinträge (A oder AAAA, bei Verwendung von IPv6) planen. Außerdem müssen Sie Verbundrichtlinien konfigurieren. Ausführliche Informationen finden Sie unter [Planung für lync Server 2013 und Office Communications Server Partnerverbund](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

