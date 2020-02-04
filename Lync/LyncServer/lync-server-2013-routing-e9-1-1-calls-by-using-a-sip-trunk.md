---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit für die Bereitstellung von E9-1-1. Details zur Verwendung eines Elin-Gateways zum Herstellen einer Verbindung mit einem PSTN-basierten E9-1-1-Dienstanbieter (Public Switched Telephone Network) finden Sie unter [Routing von E9-1-1-Anrufen mithilfe eines Elin-Gateways in lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Das folgende Diagramm zeigt, wie ein Notruf von lync Server an den Public Safety Answering Point (PSAP) weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Service-Anbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Notfall Anruf Routing von lync Server zu PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Notfall Anruf Routing von lync Server zu PSAP")

Wenn ein Notfall Anruf von einem kompatiblen lync Server-Client abgegeben wird:

1.  Eine SIP-Einladung, die den Standort, die Rückrufnummer des Anrufers und die (optionale) Benachrichtigungs-URL und die Konferenz-Rückrufnummer enthält, wird an lync Server weitergeleitet.

2.  Lync Server vergleicht die Notrufnummer und leitet den Anruf (basierend auf dem in der jeweiligen Standortrichtlinie definierten **PSTN-Nutzungs** Wert) an einen Vermittlungsserver und von dort aus über einen SIP-Trunk an den E9-1-1-Service-Anbieter weiter.

3.  Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4.  Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsbeauftragten Ihrer Organisation eine spezielle Sofortnachricht zur lync-Notfallbenachrichtigung gesendet. Diese Meldung wird immer auf dem Bildschirm des Security Officers eingeblendet und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass das Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

5.  Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6.  Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

</div>

<span> </span>

</div>

</div>

</div>

