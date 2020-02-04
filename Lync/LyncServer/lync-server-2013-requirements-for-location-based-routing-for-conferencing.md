---
title: 'Lync Server 2013: Anforderungen für standortbasiertes Routing für Konferenzen'
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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Voraussetzungen für standortbasiertes Routing für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-19_

Im folgenden werden die Anforderungen für die Installation und Konfiguration der standortbasierten Routing Konferenz Anwendung benötigt:

  - Das kumulative Update 2 von lync Server 2013 muss auf allen Servern oder Pools in Ihrer Topologie bereitgestellt werden.

<div>


> [!NOTE]  
> Wenn auf einem lync-Server oder-Pool in Ihrer Topologie lync Server 2013 Kumulatives Update 2 oder höher nicht installiert ist, kann die Erzwingung des standortbasierten Routings von lync-Besprechungen nicht garantiert werden.



</div>

  - Das standortbasierte Routing von lync Server 2013 ist eine Voraussetzung für eine standortbasierte Routing Konferenz Anwendung. Weitere Informationen zum Konfigurieren des standortbasierten Routings von lync Server 2013 finden Sie unter [Konfigurieren des standortbasierten Routings](lync-server-2013-configuring-location-based-routing.md).

  - Die Anforderungen einer standortbasierten Routing Konferenz Anwendung entsprechen den Anforderungen für das standortbasierte Routing von lync Server 2013. Weitere Informationen finden Sie unter [Planung für standortbasiertes Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Unterstützte Server

Für die standortbasierte Routing Konferenz Anwendung muss lync Server 2013 Kumulatives Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt werden. Wenn das kumulative Update 2 von lync Server 2013 auf einigen lync-Servern in Ihrer Topologie nicht installiert ist, können standortbasierte Routing Einschränkungen in lync-Besprechungen und beratenden Anruf Übertragungen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die standortbasiertes Routing unterstützen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version des Front-End-Pools</p></td>
<td><p>Mediation Server-Version</p></td>
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
<td><p>Beliebig</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Beliebig</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Beliebig</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Unterstützte Clients

Die lync-Clients, die das standortbasierte Routing von lync-Besprechungen unterstützen, sind dieselben Clients, die das standortbasierte Routing von lync Server 2013 unterstützen. Weitere Informationen finden Sie [unter Client-und Server Unterstützung für standortbasiertes Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Vermittlungs Server Anforderungen für beratende Anruf Übertragungen

Für die standortbasierte Routing Konferenz Anwendung müssen eigenständige Vermittlungsserver bereitgestellt werden, um standortbasierte Routing Einschränkungen bei Beratenden Anruf Übertragungen durchzusetzen.

Um die standortbasierte Weiterleitung von beratenden Anruf Übertragungen zu erzwingen, muss der Vermittlungsserver nur einem Vermittlungsserver-Peer (also einer Telefonanlage, einem SIP-Gateway usw.) in netzwerkregionen zugeordnet sein, in denen ein standortbasiertes Routing erforderlich ist. Wenn weitere Vermittlungsserver-Peers im gleichen Netzwerkbereich bereitgestellt werden, muss der Vermittlungsserver-Peer einem anderen Vermittlungsserver zugeordnet sein. Diese Anforderung wird wie folgt erläutert:

  - Einzelner Vermittlungsserver pro mehrere Vermittlungsserver-Peers wenn eine beratende Anrufübertragung an einen Vermittlungsserver-Peer über einen Vermittlungsserver weitergeleitet wird, der mit mehreren SIP-Stämmen für mehrere Peers (also PBX-Anlagen und Gateways) konfiguriert ist, werden die beratenden die Anrufübertragung wird blockiert, um eine PSTN-Maut Umgehung zu verhindern, wenn die Anrufumleitung über einige SIP-Stämme zugelassen, aber über andere SIP-Stämme nicht zulässig ist.
    
    Wenn beispielsweise ein einzelner Vermittlungsserver einen Vermittlungsserver-Peer des PSTN-Gateways und einen PBX-Vermittlungsserver-Peer bedient, wird das folgende Verhalten beobachtet:
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um die PSTN-Maut Umgehung zu verhindern.
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PBX-Endpunkt am gleichen Standort (Standort 1) an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, auch wenn er nicht in potenziellem PSTN Tol anfällt. l umgeht.

  - Separate Vermittlungsserver pro Vermittlungsserver-Peer
    
    Wenn eine beratende Übertragung auf einen Vermittlungsserver-Peer ausgerichtet ist, wird die beratende Übertragung mit dem einzelnen Mediation Server-Peer bewertet, der vom Vermittlungsserver gewartet wird. Der Anruf wird aufgrund seines Potenzials, in der PSTN-Maut Umgehung zu entstehen, ungeachtet aller anderen Vermittlungsserver-Peers in der Website, die von separaten Vermittlungsservern gewartet werden, nicht zugelassen oder zulässig.
    
    Bei einem separaten Vermittlungsserver, der einen Vermittlungsserver-Peer des PSTN-Gateways und einen PBX-Vermittlungsserver-Peer bedient, wird beispielsweise folgendes Verhalten beobachtet:
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um die PSTN-Maut Umgehung zu verhindern.
    
      - Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PBX-Endpunkt am gleichen Standort (Standort 1) an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf zugelassen, da er nicht in potenzielle PSTN-Maut Umgehung fällt. Ing.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Funktionen, die von der standortbasierten Routing Konferenz Anwendung nicht unterstützt werden

Die folgenden Funktionen werden von der standortbasierten Routing Konferenz Anwendung nicht unterstützt:

  - Einwahlkonferenzen. Standortbasiertes Routing kann für Einwahlkonferenzen nicht erzwungen werden. Jede Einwahl Anforderung an eine bestimmte Konferenz wird nicht durch standortbasiertes Routing eingeschränkt, auch wenn es sich bei dem Konferenzorganisator um einen lync-Benutzer handelt, der für standortbasiertes Routing aktiviert ist.

  - Es wird empfohlen, keine Konferenz Zugriffsnummern in Regionen bereitzustellen, in denen standortbasierte Routing Einschränkungen erzwungen werden müssen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

