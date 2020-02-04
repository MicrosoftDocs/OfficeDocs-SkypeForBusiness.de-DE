---
title: 'Lync Server 2013: Hybrid-und Split-Domain-AutoErmittlung'
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
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Ein freigegebener SIP-Adressraum, auch bekannt als " *Split-Domain-* Bereitstellung" oder eine *Hybrid* Bereitstellung, ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden. Das gewünschte Ergebnis besteht darin, dass Sie einen Benutzer haben, unabhängig davon, wo sich der Stammserver befindet (lokal oder Online), sich bei der Bereitstellung anmelden und an den Standort Ihres Home-Servers weitergeleitet werden. Um dies zu erreichen, wird das Auto Ermittlungs Feature von lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten. Dazu können Sie den Uniform Resource Locator (URL) für die AutoErmittlung mithilfe der lync Server-Verwaltungsshell, dem Cmdlet " **Get-CsHostingProvider** " und dem Cmdlet " **Satz-CsHostingProvider** " konfigurieren.

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilität für die Bereitstellung von geteilten Domänen

Sie müssen die folgenden bereitgestellten Attribute sammeln und aufzeichnen:

  - Geben Sie in der lync Server-Verwaltungsshell
    
        Get-CsHostingProvider

  - Suchen Sie in den Ergebnissen den Onlineanbieter mit dem Attribut **ProxyFQDN**. Beispiel: sipfed.online.lync.com.

  - Notieren Sie sich den Wert des ProxyFQDN.

  - Aktivieren Sie die Föderation in der lokalen lync Server-Systemsteuerung, wodurch die Föderation mit dem Onlineanbieter zugelassen wird.

  - Aktivieren Sie den Verbund für den Onlineanbieter. Standardmäßig sind alle Online Benutzer für den Domänen Verbund aktiviert und können mit allen Domänen kommunizieren.

  - Wenn Sie blockierte und zulässige Domänen definieren, ermitteln Sie die Domänen, die explizit zugelassen oder explizit blockiert werden.

  - Für die Online-Föderation müssen Sie Firewall-Ausnahmen, Zertifikate und DNS-Host (A oder AAAA, wenn Sie IPv6 verwenden) planen. Darüber hinaus müssen Sie Verbund Richtlinien konfigurieren. Ausführliche Informationen finden Sie unter [Planen von lync Server 2013 und Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

