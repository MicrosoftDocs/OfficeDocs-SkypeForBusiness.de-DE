---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen mithilfe eines Elin-Gateways'
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
ms.openlocfilehash: befa9ad077780eb57d4690790673fc0a5452af60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Weiterleiten von E9-1 -1-Anrufen mithilfe eines Elin-Gateways in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-05_

Einige Partner im Unified Communications Open Interoperability Program bieten qualifizierte ELIN (Emergency Location Identification Number)-fähige Gateways, die eine Alternative zu einer SIP-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter darstellen können. ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting )-Verbindungen mit E9-1-1-Diensten, die auf dem Telefonfestnetz (Public Switched Telephone Network, PSTN) basieren. Ausführliche Informationen zu Partnern, die Elin-Gateways und Links zur Dokumentation bereitstellen, [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)finden Sie unter.

Wie SIP-Trunk-Verbindungen mit E9-1-1-Dienstanbietern bieten Elin-Gateways auch die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheits-Anrufbeantworter (Rettungsleitstelle) des Anrufers weiterzuleiten, aber diese Gateways verwenden eine Elin als Standort-ID. Sie definieren Elins für jeden Emergency Response Location (ERL) in Ihrer Organisation (Ausführliche Informationen finden Sie unter [Managing Locations for Elin Gateways in lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Wenn Sie ein Elin-Gateway für Notrufe verwenden, verwenden Sie dieselbe lync Server E9-1-1-Infrastruktur, die Sie für eine SIP-trunkverbindung verwenden würden. Das bedeutet, dass die Standortinformationsdienst Datenbank den Speicherort für den lync Server-Client bereitstellt und die Standortrichtlinie das Feature aktiviert und das Routing definiert. Mit einem Elin-Gateway müssen Sie jedoch die Elins zur Standortinformationsdienst Datenbank hinzufügen und ihren PSTN-Carrier in die Ali-Datenbank (Automatic Location Identification) hochladen.

Wenn ein lync-Client seinen Standort aus dem Standortinformationsdienst erhält, enthält der Speicherort den Elin. Bei einem Notruf ist die ELIN in dem Standort enthalten, der an das ELIN-Gateway gesendet wird. Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer der anrufenden Person durch die ELIN aus. Das ELIN-Gateway leitet den Anruf dann an das PSTN weiter, wobei die ELIN die Rufnummer ist. Der PSTN-Netzbetreiber für den E9-1-1-Dienst recherchiert die ELIN in der ALI-Datenbank, bei der es sich um eine ergänzende Datenbank der MSAG (Master Street Address Guide)-Datenbank handelt. Das PSTN sendet basierend auf der Recherche in der ALI-Datenbank den Anruf dann an eine geeignete Rettungsleitstelle, und die Rettungsleitstelle sendet basierend auf der Recherche in der ALI-Datenbank Einsatzgruppen zum Standort des Anrufers. Die Nummer, von der der Anruf stammt, wird für einen vordefinierten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen. Bei einem Rückruf kontaktiert die Rettungsleitstelle das ELIN-Gateway, von dem die ELIN mit der DID (Direct Inward Dialing)-Nummer des Anrufers ausgetauscht wird.

ELIN-Gateways unterstützen nur Notrufe innerhalb des Netzwerks Ihrer Organisation. Es werden keine Notrufe von außerhalb Ihres Netzwerks unterstützt.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung einer SIP-trunkverbindung für Notrufe finden Sie unter <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 Calls by using a SIP Trunk in lync Server 2013</A>.



</div>

Das folgende Diagramm zeigt, wie ein Notruf von lync Server an die Rettungsleitstelle weitergeleitet wird, wenn Sie ein Elin-Gateway verwenden.

**Weiterleiten von E9-1-1-Anrufen mit einem ELIN-Gateway**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Eine SIP-Einladung mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und der Konferenz Rückrufnummer wird an lync Server weitergeleitet.

2.  Lync Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der anwendbaren ortungsrichtlinie definierten **PSTN-Verwendungs** Wert) an einen Vermittlungsserver und von dort an ein Elin-Gateway weiter.

3.  Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4.  Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.

5.  Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsverantwortlichen Ihrer Organisation eine spezielle Sofortnachricht für lync Emergency Notification gesendet. Diese Meldung wird immer auf dem Bildschirm der Sicherheitsverantwortlichen angezeigt und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

6.  Wird der Anruf unterbrochen, verwendet die Rettungsleitstelle die ELIN, um den Anrufer direkt zu kontaktieren. Das ELIN-Gateway tauscht die ELIN durch die DID-Nummer des Anrufers aus.

</div>

<span> </span>

</div>

</div>

</div>

