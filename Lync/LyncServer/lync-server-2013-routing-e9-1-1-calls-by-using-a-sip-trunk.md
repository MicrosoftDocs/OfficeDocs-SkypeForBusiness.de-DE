---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen mithilfe eines SIP-Trunks'
description: 'Lync Server 2013: Routing von E9-1 -1-Anrufen mithilfe eines SIP-Trunks.'
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
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571821"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Weiterleiten von E9-1 -1-Anrufen mithilfe eines SIP-Trunks in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1. Ausführliche Informationen zur Verwendung eines Elin-Gateways zum Herstellen einer Verbindung mit einem PSTN-basierten E9-1-1-Dienstanbieter finden Sie unter [Routing E9-1-1 Calls by using an Elin Gateway in lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Das folgende Diagramm zeigt, wie ein Notruf von lync Server an den Public Safety Answering Points (Rettungsleitstelle) weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Weiterleitung von Notrufen von lync Server an Rettungsleitstelle](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Weiterleitung von Notrufen von lync Server an Rettungsleitstelle")

Wenn ein Notruf von einem kompatiblen lync Server-Client getätigt wird:

1.  Eine SIP-Einladung mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und der Konferenz Rückrufnummer wird an lync Server weitergeleitet.

2.  Lync Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der anwendbaren ortungsrichtlinie definierten **PSTN-Verwendungs** Wert) an einen Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.

3.  Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4.  Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsverantwortlichen Ihrer Organisation eine spezielle Sofortnachricht für lync Emergency Notification gesendet. Diese Meldung wird immer auf dem Bildschirm der Sicherheitsverantwortlichen angezeigt und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.

5.  Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6.  Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

</div>

<span> </span>

</div>

</div>

</div>

