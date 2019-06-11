---
title: 'Lync Server 2013: Konfiguration von standortbasiertem Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Konfiguration von standortbasiertem Routing für Konferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-11_

Die standortbasierte Routing Konferenz Anwendung basiert auf der Konfiguration des standortbasierten Routings von lync Server 2013. Die wichtigsten Konfigurationen sind die folgenden:

  - Die Position der Teilnehmer, die an einer Besprechung teilnehmen, wird basierend auf Ihrer Netzwerk Website festgelegt. Eine Netzwerk Website und die zugehörigen Netzwerk-Subnetze müssen in lync Server definiert werden, um standortbasiertes Routing durchzusetzen.

  - Um die standortbasierte Weiterleitung von Besprechungen zu erzwingen, müssen lync-Teilnehmer für standortbasiertes Routing aktiviert sein.

  - Zum Erzwingen der standortbasierten Weiterleitung von PSTN-Endpunkten, die an Besprechungen teilnehmen, muss der SIP-Trunk, der zum Verbinden der PSTN-Endpunkte verwendet wird, für standortbasiertes Routing konfiguriert

Weitere Informationen zum Bereitstellen und Konfigurieren des standortbasierten Routings von lync Server 2013 finden Sie unter Konfigurieren des [Standort](lync-server-2013-configuring-location-based-routing.md)basierten Routings.

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Aktivieren der standortbasierten Routing Konferenz Anwendung

Die standortbasierte Routing Konferenz Anwendung ist standardmäßig deaktiviert. Bevor Sie diese Anwendung aktivieren, müssen Sie die richtige Priorität ermitteln, die für die Anwendung zugewiesen werden soll. Führen Sie das folgende Cmdlet in der lync Server-Verwaltungsshell aus, um diese Priorität zu ermitteln:

Get-CsServerApplication-Identity Service: Registrierungsstelle\<: Pool-FQDN\>

In diesem Cmdlet ist \<Pool-\> FQDN der Pool, in dem die standortbasierte Routing Konferenz Anwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von lync Server gehosteten Anwendungen zurück, und der Prioritätswert für jeden von Ihnen. Der standortbasierten Routing Konferenz Anwendung muss ein Prioritätswert zugewiesen werden, der größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" ist. Wir empfehlen, dass Sie der standortbasierten Routing Konferenz Anwendung einen Prioritätswert zuweisen, der einen Punkt höher als der Prioritätswert der Anwendung "UdcAgent" ist.

Wenn beispielsweise die Anwendung "UdcAgent" einen Prioritätswert von "2" aufweist, weist die Anwendung "DefaultRouting" einen Prioritätswert von "8" auf, die "ExumRouting"-Anwendung hat einen Prioritätswert von "9", und die Anwendung "OutboundRouting" hat einen Prioritätswert von "10" und dann Sie sollten der standortbasierten Routing Konferenz Anwendung einen Prioritätswert von "3" zuweisen. Auf diese Weise würde die Priorität der Anwendungen in der folgenden Reihenfolge platziert: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), standortbasierte Routing Konferenz Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8); " DefaultRouting "(Priorität: 9)," ExumRouting "(Priorität: 10) und" OutboundRouting "(Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die standortbasierte Routing Konferenz Anwendung gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, auf dem Benutzer für standortbasiertes Routing aktiviert sind:

New-CsServerApplication-Identity Service: Registrierungsstelle\<: Pool\>-FQDN- \</LBRouting-\> Prioritätsstufe der Anwendungspriorität $true-kritische $true-URIhttp://www.microsoft.com/LCS/LBRouting

Beispiel:

New-CsServerApplication-Identity Service:Registrar:ls2013cu2lbrpool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Nachdem Sie dieses Cmdlet verwendet haben, starten Sie alle Front-End-Server im Pool oder die Standard Edition-Server neu, auf denen die standortbasierte Routing Konferenz Anwendung aktiviert wurde.

<div>


> [!IMPORTANT]  
> Standortbasierte Routing-Erzwingungen zu Konferenzen oder beratenden Übertragungen werden erst erzwungen, wenn alle Front-End-Server in den entsprechenden Pools oder den Standard Edition-Servern neu gestartet werden.



</div>

Nachdem die standortbasierte Routing Konferenz Anwendung erfolgreich aktiviert wurde und alle anwendbaren lync-Server neu gestartet wurden, werden alle Konferenzen, die von lync-Benutzern für standortbasierte Routings organisiert werden, überwacht, um zu verhindern, dass die PSTN-Maut Umgehung durchgeführt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

