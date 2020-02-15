---
title: 'Lync Server 2013: Übersicht über das standortbasierte Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28ca4ea233f783271c91490aa0550bc2344bdaad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Übersicht über das standortbasierte Routing für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-19_

Die standortbasierte Routing Konferenz Anwendung bietet lync-Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung. Die Anwendung überwacht aktive Konferenzen und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Speicherort der teilnehmenden lync-Benutzer.

Die standortbasierte Routing Konferenz Anwendung bestimmt, ob das standortbasierte Routing in einer lync-Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:

  - Der Besprechungsorganisator ist für das standortbasierte Routing aktiviert. Standortbasierte Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für das standortbasierte Routing aktiviert sind.

  - Mindestens ein Besprechungsteilnehmer ist ein PSTN-Endpunkt. Standortbasierte Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte enthalten.

  - Der Netzwerkstandort, an dem das PSTN-Gateway verwendet wurde, um die Konferenz mit dem PSTN zu überbrücken, befindet sich ebenso wie die Netzwerkstandorte, von denen die Organisatoren und Teilnehmer eine Verbindung herstellen.

Die standortbasierte Routing Konferenz Anwendung verhindert die Teilnahme von lync-Benutzern und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an dieselbe Konferenz. Wenn der Organisator einer Besprechung für das standortbasierte Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:

  - Die Endpunkte, die an einer lync-Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung wird als Joined Endpoint Leave und neue Endpunkte an der Konferenz angepasst. Wenn Organisatoren und Teilnehmern eine lync-Besprechung vom gleichen Netzwerkstandort aus beitreten, können ein PSTN-Endpunkt, ein anderer Teilnehmer desselben Netzwerkstandorts, ein anderer Teilnehmer von einem anderen Netzwerkstandort oder ein Teilnehmer an einem unbekannten Netzwerkstandort Join.

  - Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, kann ein PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem für standortbasiertes Routing aktivierten SIP-Trunk abweicht.

  - Wenn Organisatoren und Teilnehmer an der Besprechung vom gleichen Netzwerkstandort aus beitreten und Teilnehmer derselben Besprechung aus dem PSTN beitreten, kann ein lync-Endpunkt von einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.

In der folgenden Tabelle sind die standortbasierten Routing Einschränkungen für Konferenzen zusammengefasst.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Benutzer in einer Konferenz zu einem bestimmten Zeitpunkt</p></td>
<td><p>Benutzer dürfen an der Konferenz teilnehmen</p></td>
<td><p>Benutzer dürfen nicht an der Konferenz teilnehmen</p></td>
</tr>
<tr class="even">
<td><p>Lync VoIP-Clientbenutzer (n) von einem einzelnen Netzwerkstandort</p></td>
<td><p>Lync VoIP-Clientbenutzer am gleichen Netzwerkstandort</p>
<p>Lync VoIP-Clientbenutzer von einem anderen Netzwerkstandort</p>
<p>Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Partner für lync-VoIP-Clientbenutzer</p>
<p>Benutzer Beitritt von einem PSTN-Endpunkt</p></td>
<td><p>Keine</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP-Clientbenutzer (n) von einem unbekannten Netzwerkstandort</p></td>
<td><p>Lync VoIP-Clientbenutzer von einem beliebigen Standort aus</p>
<p>Lync VoIP-Clientbenutzer von einem unbekannten Standort</p>
<p>Partner für lync-VoIP-Clientbenutzer</p></td>
<td><p>Benutzer Beitritt über einen PSTN-Endpunkt</p></td>
</tr>
<tr class="even">
<td><p>Lync VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten aus</p></td>
<td><p>Lync VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort aus</p>
<p>Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Partner für lync-VoIP-Clientbenutzer</p></td>
<td><p>Benutzer Beitritt über einen PSTN-Endpunkt</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort aus und Benutzer, die von einem PSTN-Endpunkt beitreten</p></td>
<td><p>Lync VoIP-Clientbenutzer am gleichen Netzwerkstandort</p></td>
<td><p>Lync VoIP-Clientbenutzer von einem anderen Netzwerkstandort</p>
<p>Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</p>
<p>Partner für lync-VoIP-Clientbenutzer</p></td>
</tr>
</tbody>
</table>


Im folgenden sind zusätzliche Merkmale der standortbasierten Routing Konferenz Anwendung zu finden:

  - Wenn ein Benutzer nicht an einer Konferenz teilnehmen darf, die standortbasierte Routing Einschränkungen verwendet, wird der Benutzer an der Konferenz angerufen, und der lync-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.

  - Ein PSTN-Endpunkt, der einer Konferenz mit standortbasierten Routing Erzwingungen Beitritt, wird nicht auf den Beitritt zur Konferenz beschränkt, unabhängig von seinem Status, wenn der Endpunkt über einen trunk Beitritt, der nicht für standortbasiertes Routing aktiviert ist.

  - Ein Nebenstellen System, das mit einem Vermittlungs Server über einen SIP-Trunk verbunden ist und keine Anrufe an das PSTN ausgeht, hat dieselben erzwungenen wie lync-Benutzer, die sich am selben Netzwerkstandort befinden, an dem der SIP-Trunk definiert ist. Beispielsweise kann ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem lync-Benutzer teilnehmen, wenn er sich am selben Netzwerkstandort befindet; Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der lync-Benutzer befindet.

</div>

<span> </span>

</div>

</div>

</div>

