---
title: 'Lync Server 2013: Planen der AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8115cb68638e2db1db93c1afb96d12d96d2ed78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planen der AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-16_

Die AutoErmittlung wurde für lync Server im kumulativen Update für lync Server 2010: November 2011 eingeführt. Der primäre Zweck für diese anfängliche Implementierung der AutoErmittlung bestand darin, einen Mittel für lync Mobile zum Auffinden des mobilitätsdiensts (MCX) bereitzustellen. Der AutoErmittlungsdienst in lync Server 2013 ist jetzt ein Dienst, der von allen Clients zum Auffinden von Server-und Benutzerdiensten verwendet wird. Der Microsoft lync Server 2013 AutoErmittlungsdienst wird auf Directors und Front-End-Servern ausgeführt.

<div>


> [!TIP]  
> Ein besseres technisches Verständnis der AutoErmittlung und der Kommunikation mit den Clients finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Understanding AutoErmittlung in lync Server 2013</A>.<BR>Mobilität ist nach wie vor ein klares Szenario, und für die Mobilitätsdienste ist noch eine spezielle Planung erforderlich. Weitere Informationen finden Sie unter <A href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</A>.



</div>

Wenn die AutoErmittlung in lync Server 2010 eingeführt wurde, mussten Kompromisse eingegangen werden, um einen Dienst zu implementieren, der potenzielle Zertifikat Änderungen an vorhandenen Server Bereitstellungen erforderlich machte. Die AutoErmittlung kann über Port TCP 443 für HTTPS oder über Port TCP 80 für HTTP verwendet werden. Wenn die Entscheidung für die Verwendung von HTTPS getroffen wurde, mussten Zertifikate für Reverse-Proxies, Directors und Front-End-Server erneut ausgestellt werden, um die `lyncdiscover.<domain>` erforderlichen `lyncdiscoverinternal.<domain>` und DNS-Einträge zu erfüllen. Wenn die Entscheidung für die Verwendung von http getroffen wurde, könnte die erneute Ausstellung von Zertifikaten vermieden werden, indem DNS-CNAME-Einträge (oder Alias) verwendet werden, um vorhandene Namen für die Zertifikate zu verwenden. Die Verwendung von http hat bedeutet, dass die anfängliche Kommunikation unverschlüsselt war.

Da lync Server 2013 AutoErmittlung für alle Clients verwendet, besteht das Hauptszenario darin, ausschließlich HTTPS zu verwenden und Zertifikate mit lyncdiscover zu erstellen. \<Domäne\> als Teil der Konfiguration von Reverse-Proxies, Directors und Front-End-Servern. Wenn Sie die AutoErmittlung in einer aktualisierten Bereitstellung von lync Server 2010 implementieren, können Sie http verwenden, um die Neuausstellung von Zertifikaten zu vermeiden. Anleitungen für beide Szenarien finden Sie in den folgenden Abschnitten.

<div>


> [!IMPORTANT]  
> Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein <EM>lyncdiscover enthalten.&lt; sipdomain "&gt; </EM> -Eintrag für jede SIP-Domäne in Ihrer Organisation. Ausführliche Informationen zu den Einträgen für alternative Antragstellernamen, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-AutoErmittlung in lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Port Zusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [DNS-Zusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

