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
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Planen der AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-16_

Die AutoErmittlung wurde für lync Server im kumulativen Update für lync Server 2010: November 2011 eingeführt. Der Hauptzweckdieser anfänglichen Implementierung der AutoErmittlung war die Bereitstellungeines Mittel für lync Mobile zum Auffinden des mobilitätsdiensts (Mobility Service, MCX). Der AutoErmittlungsdienst in lync Server 2013 ist jetzt ein Dienst, der von allen Clients zum Auffinden von Server-und Benutzerdiensten verwendet wird. Der Microsoft lync Server 2013-AutoErmittlungsdienst wird auf Directors und Front-End-Servern ausgeführt.

<div>


> [!TIP]  
> Ein besseres technisches Verständnis der AutoErmittlung und der Informationen, die Clients mitgeteilt werden, finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Grundlegendes zu AutoErmittlung in lync Server 2013</A>.<BR>Mobilität ist nach wie vor ein eindeutiges Szenario, und die Mobilitätsdienste erfordern noch einige besondere Planungen. Weitere Informationen finden Sie unter <A href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</A>.



</div>

Wenn AutoErmittlung in lync Server 2010 eingeführt wurde, gab es Kompromisse, die erforderlich sind, um einen Dienst zu implementieren, der potenzielle Zertifikat Änderungen an vorhandenen Server Bereitstellungen erforderlich macht. AutoErmittlung kann über Port TCP 443 für HTTPS oder über Port TCP 80 für HTTP verwendet werden. Wenn die Entscheidung zur Verwendung von HTTPS getroffen wurde, mussten Zertifikate für Reverse-Proxies, Directors und Front-End-Server erneut ausgestellt werden, um die erforderlichen `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` DNS-Einträge aufnehmen zu können. Wenn es sich um die Verwendung von http handelt, kann die erneute Ausstellung von Zertifikaten mithilfe von DNS-CNAME-Einträgen (oder Alias) verhindert werden, um vorhandene Namen auf den Zertifikaten zu verwenden. Die Verwendung von http bedeutete, dass die anfängliche Kommunikation unverschlüsselt war.

Da lync Server 2013 die AutoErmittlung für alle Clients verwendet, besteht das Hauptszenario darin, nur HTTPS zu verwenden und Zertifikate mit lyncdiscover zu erstellen. \<Domäne\> als Teil der Konfiguration von Reverse-Proxies, Directors und Front-End-Servern. Wenn Sie die AutoErmittlung in einer aktualisierten Bereitstellung von lync Server 2010 implementieren, möchten Sie möglicherweise http verwenden, um die erneute Ausstellung von Zertifikaten zu vermeiden. Anleitungen für beide Szenarien finden Sie in den folgenden Abschnitten.

<div>


> [!IMPORTANT]  
> Die Liste Subject Alternative Name für Zertifikate, die von der externen Webdienste-Veröffentlichungsregel verwendet werden, muss eine <EM>lyncdiscover enthalten.&lt; sipdomain&gt; </EM> -Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation. Details zu den Einträgen des alternativen betreffs, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter <A href="lync-server-2013-certificate-summary-autodiscover.md">Zertifikats Zusammenfassung – AutoErmittlung in lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Port Zusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [DNS-Zusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

