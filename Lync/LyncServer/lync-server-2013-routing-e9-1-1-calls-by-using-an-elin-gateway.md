---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-05_

Einige Partner des Unified Communications Open Interoperability-Programms bieten qualifizierte Notfall Standort-Identifikationsnummern (Elin)-fähige Gateways, die als Alternative zu einer SIP Trunk-Verbindung zu einem qualifizierten E9-1-1-Service-Anbieter dienen können. Elin-Gateways unterstützen die ISDN-oder zentralisierte Cama-Konnektivität (Automatic Message Accounting) zu Public Switched Telephone Network (PSTN)-basierenden E9-1-1-Diensten. Details zu Partnern, die Elin-Gateways und Links zu deren Dokumentation bereitstellen, [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)finden Sie unter.

Wie SIP-Trunk-Verbindungen mit E9-1-1-Service-Anbietern bieten Elin-Gateways auch die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheits Beantwortungs Punkt (PSAP) des Anrufers zu leiten, doch diese Gateways verwenden eine Elin als Standort-ID. Sie definieren Elins für jeden Emergency Response Location (ERL) in Ihrer Organisation (Details finden Sie unter [Verwalten von Speicherorten für Elin-Gateways in lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Wenn Sie ein Elin-Gateway für Notrufe verwenden, verwenden Sie dieselbe lync Server E9-1-1-Infrastruktur, die Sie für eine SIP-Trunk-Verbindung verwenden würden. Das bedeutet, dass die standortinformationsdienst-Datenbank den Standort für den lync Server-Client bereitstellt und die Standortrichtlinie das Feature aktiviert und das Routing definiert. Mit einem Elin-Gateway müssen Sie jedoch die Elins zur standortinformationsdienst-Datenbank hinzufügen und ihren PSTN-Netzbetreiber in die Datenbank "Automatic Location Identification (Ali)" hochladen.

Wenn ein lync-Client seinen Standort über den standortinformationsdienst erhält, enthält der Standort den Elin. Während eines Notrufs ist der Elin-Standort im Lieferumfang des Elin-Gateways enthalten. Das Elin-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer des Anrufers mit dem Elin aus. Das Elin-Gateway leitet dann den Anruf an das PSTN mit dem Elin als Rufnummer weiter. Der PSTN E9-1-1-Anbieter sucht nach dem Elin in der Ali-Datenbank, die eine Begleit Datenbank zur Master Street Address Guide (MSAG)-Datenbank ist. Das PSTN sendet dann den Anruf an die am besten geeignete PSAP basierend auf dem Ali-Lookup, und der PSAP sendet erste Responder an den Standort des Anrufers, basierend auf dem Ali-Lookup. Die Rufnummer wird für einen vordefinierten Zeitraum für Rückrufe auf dem Elin-Gateway zwischengespeichert. Während eines Rückrufs erreicht der PSAP das Elin-Gateway, das die Elin-Nummer für die direkte Durchwahlnummer des Anrufers ersetzt.

ELIN-Gateways unterstützen Notrufe nur innerhalb des Netzwerks Ihrer Organisation. Notrufe von außerhalb dieses Netzwerks werden nicht unterstützt.

<div>


> [!NOTE]  
> Details zur Verwendung einer SIP Trunk-Verbindung für Notrufe finden Sie unter <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing von E9-1-1-Anrufen mithilfe eines SIP-Trunks in lync Server 2013</A>.



</div>

Das folgende Diagramm zeigt, wie ein Notfall Anruf von lync Server an die PSAP weitergeleitet wird, wenn Sie ein Elin-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Eine SIP-Einladung, die den Standort, die Rückrufnummer des Anrufers und die (optionale) Benachrichtigungs-URL und die Konferenz-Rückrufnummer enthält, wird an lync Server weitergeleitet.

2.  Lync Server vergleicht die Notrufnummer und leitet den Anruf (basierend auf dem in der jeweiligen Standortrichtlinie definierten **PSTN-Nutzungs** Wert) an einen Vermittlungsserver und von dort aus an ein Elin-Gateway weiter.

3.  Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4.  Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP. 

5.  Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht zur lync-Notfallbenachrichtigung gesendet. Diese Meldung wird immer auf dem Bildschirm des Security Officers eingeblendet und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass das Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

6.  Wenn der Anruf vorzeitig unterbrochen wird, kontaktiert der PSAP den Anrufer mithilfe der ELIN direkt. Das ELIN-Gateway tauscht die ELIN mit der DID des Anrufers.

</div>

<span> </span>

</div>

</div>

</div>

