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

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="bdc9b-102">Weiterleiten von E9-1 -1-Anrufen mithilfe eines Elin-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9b-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc9b-103">_**Letztes Änderungsstand des Themas:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="bdc9b-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="bdc9b-104">Einige Partner im Unified Communications Open Interoperability Program bieten qualifizierte ELIN (Emergency Location Identification Number)-fähige Gateways, die eine Alternative zu einer SIP-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter darstellen können.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="bdc9b-105">ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting )-Verbindungen mit E9-1-1-Diensten, die auf dem Telefonfestnetz (Public Switched Telephone Network, PSTN) basieren.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="bdc9b-106">Ausführliche Informationen zu Partnern, die Elin-Gateways und Links zur Dokumentation bereitstellen, [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="bdc9b-107">Wie SIP-Trunk-Verbindungen mit E9-1-1-Dienstanbietern bieten Elin-Gateways auch die Möglichkeit, einen Notruf an den am besten geeigneten öffentlichen Sicherheits-Anrufbeantworter (Rettungsleitstelle) des Anrufers weiterzuleiten, aber diese Gateways verwenden eine Elin als Standort-ID.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="bdc9b-108">Sie definieren Elins für jeden Emergency Response Location (ERL) in Ihrer Organisation (Ausführliche Informationen finden Sie unter [Managing Locations for Elin Gateways in lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="bdc9b-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="bdc9b-109">Wenn Sie ein Elin-Gateway für Notrufe verwenden, verwenden Sie dieselbe lync Server E9-1-1-Infrastruktur, die Sie für eine SIP-trunkverbindung verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="bdc9b-110">Das bedeutet, dass die Standortinformationsdienst Datenbank den Speicherort für den lync Server-Client bereitstellt und die Standortrichtlinie das Feature aktiviert und das Routing definiert.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="bdc9b-111">Mit einem Elin-Gateway müssen Sie jedoch die Elins zur Standortinformationsdienst Datenbank hinzufügen und ihren PSTN-Carrier in die Ali-Datenbank (Automatic Location Identification) hochladen.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="bdc9b-112">Wenn ein lync-Client seinen Standort aus dem Standortinformationsdienst erhält, enthält der Speicherort den Elin.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="bdc9b-113">Bei einem Notruf ist die ELIN in dem Standort enthalten, der an das ELIN-Gateway gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="bdc9b-114">Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer der anrufenden Person durch die ELIN aus.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="bdc9b-115">Das ELIN-Gateway leitet den Anruf dann an das PSTN weiter, wobei die ELIN die Rufnummer ist.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="bdc9b-116">Der PSTN-Netzbetreiber für den E9-1-1-Dienst recherchiert die ELIN in der ALI-Datenbank, bei der es sich um eine ergänzende Datenbank der MSAG (Master Street Address Guide)-Datenbank handelt.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="bdc9b-117">Das PSTN sendet basierend auf der Recherche in der ALI-Datenbank den Anruf dann an eine geeignete Rettungsleitstelle, und die Rettungsleitstelle sendet basierend auf der Recherche in der ALI-Datenbank Einsatzgruppen zum Standort des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="bdc9b-118">Die Nummer, von der der Anruf stammt, wird für einen vordefinierten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="bdc9b-119">Bei einem Rückruf kontaktiert die Rettungsleitstelle das ELIN-Gateway, von dem die ELIN mit der DID (Direct Inward Dialing)-Nummer des Anrufers ausgetauscht wird.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="bdc9b-120">ELIN-Gateways unterstützen nur Notrufe innerhalb des Netzwerks Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="bdc9b-121">Es werden keine Notrufe von außerhalb Ihres Netzwerks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdc9b-122">Ausführliche Informationen zur Verwendung einer SIP-trunkverbindung für Notrufe finden Sie unter <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 Calls by using a SIP Trunk in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="bdc9b-123">Das folgende Diagramm zeigt, wie ein Notruf von lync Server an die Rettungsleitstelle weitergeleitet wird, wenn Sie ein Elin-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="bdc9b-124">**Weiterleiten von E9-1-1-Anrufen mit einem ELIN-Gateway**</span><span class="sxs-lookup"><span data-stu-id="bdc9b-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="bdc9b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="bdc9b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="bdc9b-126">Eine SIP-Einladung mit dem Standort, der Rückrufnummer des Anrufers und der (optionalen) Benachrichtigungs-URL und der Konferenz Rückrufnummer wird an lync Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="bdc9b-127">Lync Server stimmt mit der Notrufnummer überein und leitet den Anruf (basierend auf dem in der anwendbaren ortungsrichtlinie definierten **PSTN-Verwendungs** Wert) an einen Vermittlungsserver und von dort an ein Elin-Gateway weiter.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="bdc9b-128">Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="bdc9b-p106">Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="bdc9b-132">Wenn Sie die ortungsrichtlinie für Benachrichtigungen konfiguriert haben, werden einem oder mehreren Sicherheitsverantwortlichen Ihrer Organisation eine spezielle Sofortnachricht für lync Emergency Notification gesendet.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="bdc9b-133">Diese Meldung wird immer auf dem Bildschirm der Sicherheitsverantwortlichen angezeigt und enthält den Namen des Anrufers, die Telefonnummer, die Uhrzeit und den Standort, sodass Sicherheitspersonal schnell auf den Notruf Anrufer reagieren kann, indem er eine Sofortnachricht oder eine Stimme verwendet.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="bdc9b-p108">Wird der Anruf unterbrochen, verwendet die Rettungsleitstelle die ELIN, um den Anrufer direkt zu kontaktieren. Das ELIN-Gateway tauscht die ELIN durch die DID-Nummer des Anrufers aus.</span><span class="sxs-lookup"><span data-stu-id="bdc9b-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

