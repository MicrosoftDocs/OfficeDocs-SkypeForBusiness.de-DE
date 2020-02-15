---
title: 'Lync Server 2013: Konfiguration des standortbasierten Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a959addbcd98e04d336ba380676399dbff2f586b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Konfiguration des standortbasierten Routings für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-09-11_

Die standortbasierte Routing Konferenz Anwendung beruht auf der Konfiguration lync Server 2013 standortbasierten Routings. Die wichtigsten Konfigurationen lauten wie folgt:

  - Die Position der Teilnehmer, die einer Besprechung beitreten, wird basierend auf dem Netzwerkstandort bestimmt. Ein Netzwerkstandort und die zugehörigen Netzwerk Subnetze müssen in lync Server definiert sein, um standortbasiertes Routing erzwingen zu können.

  - Um das standortbasierte Routing von Besprechungen zu erzwingen, müssen lync-Teilnehmer für das standortbasierte Routing aktiviert sein.

  - Zum Erzwingen eines standortbasierten Routings von PSTN-Endpunkten, die Besprechungen beitreten, muss der SIP-Trunk, der zum Verbinden der PSTN-Endpunkte verwendet wird, für das standortbasierte Routing konfiguriert werden.

Weitere Informationen zum Bereitstellen und konfigurieren lync Server 2013 standortbasierten Routings finden Sie unter Konfigurieren des [standortbasierten Routings](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Aktivieren der standortbasierten Routing Konferenz Anwendung

Die standortbasierte Routing Konferenz Anwendung ist standardmäßig deaktiviert. Vor dem Aktivieren dieser Anwendung müssen Sie die richtige Priorität bestimmen, die für die Anwendung zugewiesen werden soll. Um diese Priorität zu ermitteln, führen Sie das folgende Cmdlet in lync Server-Verwaltungsshell aus:

Get-CsServerApplication-Identity Service: Registrierungsstelle\<: Pool-FQDN\>

In diesem Cmdlet ist \<Pool FQDN\> der Pool, in dem die standortbasierte Routing Konferenz Anwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von lync Server gehosteten Anwendungen und den Prioritätswert für jeden von Ihnen zurück. Die standortbasierte Routing Konferenz Anwendung muss einen Prioritätswert größer als die "UdcAgent"-Anwendung und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" zugewiesen werden. Es wird empfohlen, der standortbasierten Routing Konferenz Anwendung einen Prioritätswert zuzuweisen, der einen Punkt höher ist als der Prioritätswert der Anwendung "UdcAgent".

Wenn die "UdcAgent"-Anwendung beispielsweise den Prioritätswert "2" hat, hat die "DefaultRouting"-Anwendung den Prioritätswert "8", die "ExumRouting"-Anwendung hat den Prioritätswert "9" und die "OutboundRouting"-Anwendung hat den Prioritätswert "10", dann Sie sollten der standortbasierten Routing Konferenz Anwendung einen Prioritätswert von "3" zuweisen. Dadurch wird die Priorität der Anwendungen in der folgenden Reihenfolge platziert: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), standortbasierte Routing Konferenz Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), " DefaultRouting "(Priorität: 9)," ExumRouting "(Priorität: 10) und" OutboundRouting "(Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die standortbasierte Routing Konferenz Anwendung gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, für den Benutzer für standortbasiertes Routing aktiviert sind:

New-CsServerApplication-Identity Service: Registrar:\<Pool FQDN\>/LBRouting-Priority \<\> -Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Beispiel:

New-CsServerApplication-Identity Service:Registrar:ls2013cu2lbrpool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Nachdem Sie dieses Cmdlet verwendet haben, starten Sie alle Front-End-Server im Pool oder die Standard Edition-Server neu, auf denen die standortbasierte Routing Konferenz Anwendung aktiviert wurde.

<div>


> [!IMPORTANT]  
> Standortbasierte Routing-Erzwingungen zu Konferenzen oder beratenden Übertragungen werden erst durchgesetzt, wenn alle Front-End-Server in den entsprechenden Pools oder Standard Edition-Servern neu gestartet werden.



</div>

Nachdem die standortbasierte Routing Konferenz Anwendung erfolgreich aktiviert wurde und alle entsprechenden lync-Server neu gestartet wurden, werden alle Konferenzen, die von lync-Benutzern für standortbasiertes Routing organisiert wurden, überwacht, um zu verhindern, dass die PSTN-Maut Umgehung aktiviert wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

