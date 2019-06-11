---
title: 'Lync Server 2013: Übersicht über E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="5bee2-102">Übersicht über E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bee2-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bee2-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5bee2-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5bee2-104">Microsoft lync Server 2013 unterstützt erweiterte 9-1-1 (E9-1-1)-Aufrufe von lync-Clients und lync Phone Edition-Geräten.</span><span class="sxs-lookup"><span data-stu-id="5bee2-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="5bee2-105">Wenn Sie lync Server für E9-1-1 konfigurieren, beinhalten Notrufe, die von lync 2013 oder lync Phone Edition abgesetzt werden, die Informationen zum Emergency Response Location (ERL) aus der Datenbank des Standort Informationsdiensts.</span><span class="sxs-lookup"><span data-stu-id="5bee2-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="5bee2-106">ERLs bestehen aus bürgerlichen (also Straßen-) Adressen und anderen Informationen, die dazu beitragen, eine genauere Position in Bürogebäuden und anderen Multitenant-Anlagen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="5bee2-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="5bee2-107">Wenn ein Benutzer einen Notfall Anruf tätigt, leitet lync Server den Audioanruf zusammen mit dem Standort und den Rückrufinformationen über einen Vermittlungsserver an einen E9-1-1-Service-Anbieter weiter.</span><span class="sxs-lookup"><span data-stu-id="5bee2-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="5bee2-108">Der E9-1-1-Service-Anbieter verwendet die bürgerliche Adresse des Anrufers, um den Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterzuleiten, der dem Aufenthaltsort des Anrufers dient, und sendet einen Notfall-Service-Abfrage Schlüssel (ESQK), den der PSAP verwendet, um den Erl des Anrufers nachschlagen zu können.</span><span class="sxs-lookup"><span data-stu-id="5bee2-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="5bee2-109">Lync Server unterstützt zwei Methoden zum Weiterleiten von Notrufen an einen E9-1-1-Dienstanbieter:</span><span class="sxs-lookup"><span data-stu-id="5bee2-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="5bee2-110">Eine SIP (Session Initiation Protocol)-Trunkverbindung mit einem qualifizierten E9-1-1-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="5bee2-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="5bee2-111">Ein ELIN (Emergency Location Identification Number)-Gateway zu einem Festnetz (Public Switched Telephone, PSTN)-basierten E9-1-1-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="5bee2-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="5bee2-112">Wenn Sie einen SIP Trunk E9-1-1 Dienstanbieter verwenden, fügen Sie ERLs der Datenbank des Standort Informationsdiensts hinzu, und überprüfen Sie dann die Speicherorte mit einem Master Street Address Guide (MSAG), der vom E9-1-1-Dienstanbieter verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="5bee2-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="5bee2-113">Wenn ein Dienstanbieter E9-1-1 einen Anruf empfängt, der keine Standortinformationen hat oder einen Speicherort aufweist, der nicht mit dem MSAG überprüft wurde, leitet der E9-1-1-Dienstanbieter den Anruf an ein nationales/regionales Notruf Center (ECRC) weiter, das Personal mit speziell geschulten Mitarbeitern, die den Standort des Anrufers, wenn möglich, mündlich abrufen und den Anruf manuell an die entsprechende PSAP weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="5bee2-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="5bee2-114">(Einige SIP Trunk E9-1-1-Service-Anbieter bieten Kunden auch eine direkte PSTN-Wählnummer (DID) an den ECRC, die ein alternatives Mittel zur Weiterleitung von 9-1-1-anrufen bietet, wenn der SIP-Trunk aus irgendeinem Grund fehlschlägt.)</span><span class="sxs-lookup"><span data-stu-id="5bee2-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="5bee2-115">Im Gegensatz zu Time Division Multiplexing (TDM) und IP-basierter PBX-Telefone (Private Branch Exchange), die über feste Speicherorte verfügen, kann ein lync-Endpunkt sehr mobil sein.</span><span class="sxs-lookup"><span data-stu-id="5bee2-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="5bee2-116">Wenn Sie das E9-1-1-Feature bereitstellen, hilft lync Server dabei, sicherzustellen, dass der Notruf, unabhängig davon, wo sich ein Anrufer befindet, an die PSAP weitergeleitet werden kann, die dem Aufenthaltsort des Anrufers dient.</span><span class="sxs-lookup"><span data-stu-id="5bee2-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="5bee2-117">Beispiel: Wenn sich das Hauptbüro eines Benutzers in Redmond, Washington, befindet und der Benutzer einen Notruf von einem Computer in einer Zweigstelle in Wichita, Kansas, absetzt, leitet der SIP-Trunk- oder PSTN-basierte E9-1-1-Dienstanbieter den Anruf an die Rettungsleitstelle in Wichita und nicht an die Rettungsleitstelle in Redmond weiter.</span><span class="sxs-lookup"><span data-stu-id="5bee2-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="5bee2-118">Wenn Sie ein Elin-Gateway verwenden, fügen Sie auch ERLs der Datenbank des Standort Informationsdiensts hinzu, Sie schließen aber auch eine Elin-Nummer für jede Position ein.</span><span class="sxs-lookup"><span data-stu-id="5bee2-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="5bee2-119">Die ELIN-Nummer wird während eines Notrufs zur Notrufnummer.</span><span class="sxs-lookup"><span data-stu-id="5bee2-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="5bee2-120">Sie müssen dann sicherstellen, dass der PSTN-Netzbetreiber die ELINs in die ALI-Datenbank (Automatic Location Identification, automatische Standortidentifizierung) hochlädt.</span><span class="sxs-lookup"><span data-stu-id="5bee2-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bee2-121">Mit lync verbundene analoge Geräte können keine Standortinformationen vom standortinformationsdienst empfangen oder den Standort an den E9-1-1-Service-Anbieter übertragen.</span><span class="sxs-lookup"><span data-stu-id="5bee2-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="5bee2-122">Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden und E9-1-1 über analoge Telefone unterstützen müssen, stehen Ihnen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="5bee2-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5bee2-123"><STRONG>Traditionelle PS-Ali-Option</STRONG>&nbsp;&nbsp;&nbsp;Wenn Sie über lokale PSTN-Gateways an jeder Website verfügen, auf der analoge Telefone bereitgestellt werden und auf jedem analogen Telefon ein did vorhanden ist, können Sie die Position des analogen Geräts direkt mit einem privaten Schalter/automatisch bereitstellen. Location Identification (PS-Ali)-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="5bee2-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="5bee2-124">In diesem Fall konfigurieren Sie speziell gestaltete lync-VoIP-Richtlinien und weisen Sie den Kontaktobjekten des analogen Geräts zu, sodass E9-1-1-Anrufe von diesen Telefonen direkt über das lokale Gateway an den PSTN-Anbieter weiterleiten, der die Website abruft (anstatt das Routing des Anruf an einen E9-1-1-Service-Anbieter SIP-Trunk).</span><span class="sxs-lookup"><span data-stu-id="5bee2-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="5bee2-125">Wenn ein Notruf erfolgt, ordnet eine Datenbank bei einem PS-Ali-Anbieter, der dem PSTN-trunk zugeordnet ist, die did-Daten jedes analogen Telefons einem physikalischen Standort zu und stellt diesen Standort dem PSAP zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5bee2-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="5bee2-126">Diese Einträge müssen mit dem PS-Ali-Dienstanbieter jedes Mal aktualisiert werden, wenn Telefone in andere ERLs verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="5bee2-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="5bee2-127"><STRONG>E9-1-1 Service Provider-Option</STRONG>&nbsp;&nbsp;&nbsp;Sie können die analoge Telefon DIDs und deren zugehörige ERLs mit dem E9-1-1-Dienstanbieter registrieren, wenn dieser vom Dienstanbieter E9-1-1 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5bee2-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="5bee2-128">Wenn der Anbieter einen Anruf von lync Server erhält, der keine PIDF-Lo-Daten enthält, kann der Anbieter sehen, ob eine Daten Bank Übereinstimmung für die DID-Nummer des anrufenden Teilnehmers vorliegt.</span><span class="sxs-lookup"><span data-stu-id="5bee2-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="5bee2-129">Durch Verwendung des Erl, das aus seiner Datenbank abgerufen wurde, kann der Anbieter den Notruf automatisch an die richtige PSAP weiterleiten, und der PSAP empfängt die did des analogen Geräts und einen ESQK-Eintrag, der es dem Dispatcher ermöglicht, den Standort des Anrufers nachzuschlagen.</span><span class="sxs-lookup"><span data-stu-id="5bee2-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="5bee2-p108">Wenn Sie ein ELIN-Gateway verwenden und die Unterstützung für E9-1-1 über analoge Telefone erforderlich ist, können Sie dem PS-ALI-Dienstanbieter wie oben in der ersten Option beschrieben den Standort des analogen Geräts direkt zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="5bee2-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="5bee2-131">Aus Sicht des lync-Servers kann der E9-1-1-Prozess in zwei Phasen aufgeteilt werden:</span><span class="sxs-lookup"><span data-stu-id="5bee2-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="5bee2-132">Schritt 1: Abrufen eines Standorts</span><span class="sxs-lookup"><span data-stu-id="5bee2-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="5bee2-133">Schritt 2: Weiterleiten des Notrufs an einen E9-1-1-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="5bee2-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="5bee2-134">In diesem Abschnitt wird die Funktionsweise dieser Schritte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5bee2-134">This section describes how these stages work.</span></span>

<span data-ttu-id="5bee2-135">Wenn Sie Ihre Infrastruktur so konfigurieren möchten, dass der Standort von Clients automatisch erkannt wird, müssen Sie zunächst festlegen, welche Netzwerkelemente verwendet werden sollen, um Anrufer Standorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="5bee2-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="5bee2-136">Details zu den möglichen Optionen finden Sie unter [Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in lync Server 2013 verwendet](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)werden.</span><span class="sxs-lookup"><span data-stu-id="5bee2-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5bee2-137">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5bee2-137">In This Section</span></span>

  - [<span data-ttu-id="5bee2-138">Abrufen eines Standorts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bee2-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="5bee2-139">Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bee2-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="5bee2-140">Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bee2-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

