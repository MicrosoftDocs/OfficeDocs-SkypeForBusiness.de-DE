---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen mithilfe eines SIP-Trunks'
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
ms.openlocfilehash: d58507d72a096cb3fbf6deb0d09cddc542fdc2d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="0a570-102">Weiterleiten von E9-1 -1-Anrufen mithilfe eines SIP-Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a570-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a570-103">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0a570-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0a570-104">Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0a570-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="0a570-105">Ausführliche Informationen zur Verwendung eines Elin-Gateways zum Herstellen einer Verbindung mit einem PSTN-basierten E9-1-1-Dienstanbieter finden Sie unter [Routing E9-1-1 Calls by using an Elin Gateway in lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="0a570-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="0a570-106">Das folgende Diagramm zeigt, wie ein Notruf von lync Server an den Public Safety Answering Points (Rettungsleitstelle) weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a570-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="0a570-107">**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**</span><span class="sxs-lookup"><span data-stu-id="0a570-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="0a570-108">![Weiterleitung von Notrufen von lync Server an Rettungsleitstelle](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Weiterleitung von Notrufen von lync Server an Rettungsleitstelle")</span><span class="sxs-lookup"><span data-stu-id="0a570-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="0a570-109">Wenn ein Notruf von einem kompatiblen lync Server-Client getätigt wird:</span><span class="sxs-lookup"><span data-stu-id="0a570-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="0a570-110">Eine SIP-Einladung mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und der Konferenz Rückrufnummer wird an lync Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0a570-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="0a570-111">Lync Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der anwendbaren ortungsrichtlinie definierten **PSTN-Verwendungs** Wert) an einen Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.</span><span class="sxs-lookup"><span data-stu-id="0a570-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="0a570-p102">Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="0a570-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="0a570-115">Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsverantwortlichen Ihrer Organisation eine spezielle Sofortnachricht für lync Emergency Notification gesendet.</span><span class="sxs-lookup"><span data-stu-id="0a570-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="0a570-116">Diese Meldung wird immer auf dem Bildschirm der Sicherheitsverantwortlichen angezeigt und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a570-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="0a570-117">Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0a570-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="0a570-118">Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="0a570-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

