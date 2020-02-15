---
title: 'Lync Server 2013: Anforderungen für das standortbasierte Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Anforderungen für das standortbasierte Routing für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-19_

Im folgenden werden die Anforderungen für die Installation und Konfiguration der standortbasierten Routing Konferenz Anwendung benötigt:

  - Lync Server 2013 Kumulatives Update 2 muss auf allen Servern oder Pools in der Topologie bereitgestellt werden.

<div>


> [!NOTE]  
> Wenn auf einem lync-Server oder-Pool in Ihrer Topologie lync Server 2013 Kumulatives Update 2 oder höher nicht installiert ist, kann die Erzwingung des standortbasierten Routings von lync-Besprechungen nicht gewährleistet werden.



</div>

  - Lync Server 2013 standortbasiertes Routing ist eine Voraussetzung für die standortbasierte Routing Konferenz Anwendung. Weitere Informationen zum Konfigurieren lync Server 2013 standortbasierten Routings finden Sie unter Konfigurieren des [standortbasierten Routings](lync-server-2013-configuring-location-based-routing.md).

  - Anforderungen der standortbasierten Routing Konferenz Anwendung entsprechen den Anforderungen für lync Server 2013 standortbasiertes Routing. Weitere Informationen finden Sie unter [Planung für standortbasiertes Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Unterstützte Server

Für die standortbasierte Routing Konferenz Anwendung muss lync Server 2013 Kumulatives Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt werden. Wenn lync Server 2013 Kumulatives Update 2 nicht auf einigen lync-Servern in Ihrer Topologie installiert ist, können standortbasierte Routing Einschränkungen nicht vollständig in lync-Besprechungen und beratenden Anruf Übertragungen erzwungen werden.

In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die standortbasiertes Routing unterstützen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version des Front-End-Pools</p></td>
<td><p>Vermittlungsserver Version</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Kumulatives Update 2</p></td>
<td><p>Lync Server 2013 Kumulatives Update 2</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Kumulatives Update 2</p></td>
<td><p>Lync Server 2013 Kumulatives Update 1</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Kumulatives Update 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Kumulatives Update 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Kumulatives Update 1</p></td>
<td><p>Any</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Any</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Any</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Unterstützte Clients

Die lync-Clients, die das standortbasierte Routing von lync-Besprechungen unterstützen, sind dieselben Clients, die lync Server 2013 standortbasiertes Routing unterstützen. Weitere Informationen finden Sie unter Client- [und Server Unterstützung für standortbasiertes Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Vermittlungsserver Anforderungen für beratende Anruf Übertragungen

Für die standortbasierte Routing Konferenz Anwendung ist die Bereitstellung eigenständiger Vermittlungsserver erforderlich, um standortbasierte Routing Einschränkungen für Anrufe in beratenden anrufen durchzusetzen.

Um das standortbasierte Routing von Anruf Transfers durchzusetzen, muss das Vermittlungsserver nur einem Vermittlungsserver Peer (also PBX, SIP-Gateway usw.) in netzwerkregionen zugeordnet werden, in denen ein standortbasiertes Routing erforderlich ist. Wenn weitere Vermittlungsserver Peers in derselben netzwerkregion bereitgestellt werden, muss der Vermittlungsserver Peer einem anderen Vermittlungsserver zugeordnet werden. Diese Anforderung wird wie folgt beschrieben:

  - Einzelne Vermittlungsserver pro mehrere Vermittlungsserver Peers wenn eine Anrufweiterleitung an einen Vermittlungsserver Peer über eine Vermittlungsserver geleitet wird, die mit mehreren SIP-Trunks für mehrere Peers konfiguriert ist (z.b. Nebenstellenanlagen und Gateways), wird der Beratende die Anrufweiterleitung wird blockiert, um eine PSTN-Maut Umgehung zu verhindern, wenn die Anrufweiterleitung über einige SIP-Trunks zulässig ist, aber über andere SIP-Trunks nicht zulässig ist.
    
    Wenn beispielsweise ein einzelnes Vermittlungsserver ein PSTN-Gateway Vermittlungsserver Peer und eine Nebenstellenanlage Vermittlungsserver Peer bedient, wird das folgende Verhalten beobachtet:
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (dh Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um eine PSTN-Maut Umgehung zu verhindern.
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (also Standort 1) versucht, einen Anruf mit einem Nebenstellen Endgerät am selben Standort (Standort 1) an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, auch wenn er nicht im potenziellen PSTN Tol anfällt. l Umgehung.

  - Separate Vermittlungsserver pro Vermittlungsserver Peer
    
    Wenn eine beratende Übertragung an einen Vermittlungsserver Peer gerichtet ist, wird die beratende Übertragung anhand des einzelnen Vermittlungsserver Peers ausgewertet, der von der Vermittlungsserver gewartet wird. Der Anruf wird nicht zugelassen oder darf aufgrund seines Potenzials in Verbindung mit der PSTN-Maut Umgehung ungeachtet aller anderen Vermittlungsserver-Peers am Standort entstehen, die von separaten Vermittlungsservern gewartet werden.
    
    Beispielsweise wird im Fall eines separaten Vermittlungs Servers, der ein PSTN-Gateway Vermittlungsserver Peer und einer Nebenstellenanlage Vermittlungsserver Peers bedient, das folgende Verhalten beobachtet:
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (dh Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um eine PSTN-Maut Umgehung zu verhindern.
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (dh Standort 1) versucht, einen Anruf mit einem Nebenstellen-Endpunkt an demselben Standort (Standort 1) an einen lync-Benutzer von einem anderen Standort (Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf zugelassen, da er bei einer potenziellen PSTN-Maut Umgehung nicht anfallen kann. Ing.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funktionen, die von der standortbasierten Routing Konferenz Anwendung nicht unterstützt werden

Die folgenden Funktionen werden von der standortbasierten Routing Konferenz Anwendung nicht unterstützt:

  - Einwahlkonferenzen. Das standortbasierte Routing kann nicht für Einwahlkonferenzen erzwungen werden. Alle Einwahl Anforderungen für eine bestimmte Konferenz werden nicht durch standortbasiertes Routing eingeschränkt, auch wenn es sich bei dem Konferenzorganisator um einen lync-Benutzer handelt, der für standortbasiertes Routing aktiviert ist.

  - Es wird empfohlen, keine Konferenz Zugriffsnummern in Regionen zur Verfügung zu stellen, in denen standortbasierte Routing Einschränkungen erzwungen werden müssen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

