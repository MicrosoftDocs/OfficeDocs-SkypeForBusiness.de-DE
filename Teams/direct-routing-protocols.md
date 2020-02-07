---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Direkte Routing Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835025"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="b1728-103">Direct Routing-Definitionen und RFC-Standards</span><span class="sxs-lookup"><span data-stu-id="b1728-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="b1728-104">In diesem Artikel wird beschrieben, wie das direkt Routing von Microsoft Phone System RFC-Standardprotokolle implementiert.</span><span class="sxs-lookup"><span data-stu-id="b1728-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="b1728-105">Dieser Artikel richtet sich an sprach Administratoren, die für die Konfiguration der Verbindung zwischen dem lokalen Session Border Controller (SBC) und dem SIP-Proxydienst (Session Initiation Protocol) verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="b1728-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="b1728-106">Der Kunde SBC Schnittstellen mit den folgenden Komponenten im Microsoft Teams-Back-End ab:</span><span class="sxs-lookup"><span data-stu-id="b1728-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="b1728-107">**Der SIP-Proxy** zum signalisieren.</span><span class="sxs-lookup"><span data-stu-id="b1728-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="b1728-108">Hierbei handelt es sich um die mit dem Internet verbundene Komponente des direkten Routings, die SIP (TLS)-Verbindungen zwischen dem SBCS und dem direkten Routing verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b1728-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="b1728-109">**Die Medien Prozessoren** für Medien.</span><span class="sxs-lookup"><span data-stu-id="b1728-109">**The media processors** for media.</span></span> <span data-ttu-id="b1728-110">Hierbei handelt es sich um die mit dem Internet verbundene Komponente des direkten Routings, die den Mediendatenverkehr verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b1728-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="b1728-111">Diese Komponente verwendet SRTP-und SRTCP-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="b1728-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="b1728-112">Weitere Informationen zum direkten Routing finden Sie unter [Direktes Routing für das Telefon System](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b1728-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="b1728-113">Weitere Informationen dazu, wie das SIP-Protokoll von Direct Routing implementiert wird, finden Sie unter [Direct Routing – SIP-Protokoll](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="b1728-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="b1728-114">RFC-Standards</span><span class="sxs-lookup"><span data-stu-id="b1728-114">RFC standards</span></span>

<span data-ttu-id="b1728-115">Das direkte Routing entspricht den RFC-Standards.</span><span class="sxs-lookup"><span data-stu-id="b1728-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="b1728-116">Der SBC, der mit Direct Routing verbunden ist, muss auch den folgenden RFCs (oder deren Nachfolgern) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b1728-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="b1728-117">Standards für Geräte, die den nicht-Medien-Bypass-Modus unterstützen</span><span class="sxs-lookup"><span data-stu-id="b1728-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="b1728-118">Die folgenden Standards gelten für Geräte, die nur den nicht-Medien-Bypass-Modus unterstützen:</span><span class="sxs-lookup"><span data-stu-id="b1728-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="b1728-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span><span class="sxs-lookup"><span data-stu-id="b1728-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="b1728-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="b1728-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="b1728-121">Private Erweiterung des Sitzungs Initiierungs Protokolls für die Assertions Identität in vertrauenswürdigen Netzwerken – Abschnitte zur Behandlung von P-Asserted-Identity-Header.</span><span class="sxs-lookup"><span data-stu-id="b1728-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="b1728-122">Direct Routing sendet P-Asserted-Identity mit Datenschutz-ID-Headern.</span><span class="sxs-lookup"><span data-stu-id="b1728-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="b1728-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Eine Erweiterung des Session Initiation Protocol (SIP) für erforderliche Verlaufsinformationen.</span><span class="sxs-lookup"><span data-stu-id="b1728-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="b1728-124">Weitere Informationen finden Sie auch unter Routing SIP-Protokoll Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="b1728-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="b1728-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mechanismus für das Sitzungs Initiierungs Protokoll</span><span class="sxs-lookup"><span data-stu-id="b1728-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="b1728-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Der Header des Session Initiation Protocol (SIP) "ersetzt"</span><span class="sxs-lookup"><span data-stu-id="b1728-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="b1728-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) SIP-Nutzung (Session Initiation Protocol) des Angebots/Antwort-Modells</span><span class="sxs-lookup"><span data-stu-id="b1728-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="b1728-128">Lesen Sie den Abschnitt "Abweichungen von RFC".</span><span class="sxs-lookup"><span data-stu-id="b1728-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="b1728-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) und [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="b1728-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="b1728-130">Schützen Sie den RTP-Datenverkehr mithilfe von SRTP.</span><span class="sxs-lookup"><span data-stu-id="b1728-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="b1728-131">Der SBC muss in der Lage sein, Schlüssel mithilfe von SDES festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b1728-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="b1728-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP)-Angebot/Antwort Klärungen für RTP/RTCP-Multiplexing</span><span class="sxs-lookup"><span data-stu-id="b1728-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="b1728-133">Für Geräte, die den Medien Umgehungsmodus unterstützen, gelten Standards</span><span class="sxs-lookup"><span data-stu-id="b1728-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="b1728-134">Zusätzlich zu den Standards, die in Bezug auf den nicht-Bypass-Modus aufgeführt sind, werden die folgenden Standards für den Medien Umgehungsmodus verwendet:</span><span class="sxs-lookup"><span data-stu-id="b1728-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="b1728-135">[RFC 5245 Interactive Connectivity Establishment (ICE) für die medienumgehung](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="b1728-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="b1728-136">Der SBC muss Folgendes unterstützen:</span><span class="sxs-lookup"><span data-stu-id="b1728-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="b1728-137">Ice lite – die Kunden von Teams sind Full Ice-Kunden</span><span class="sxs-lookup"><span data-stu-id="b1728-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="b1728-138">[Ice startet neu](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="b1728-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="b1728-139">Weitere Informationen finden Sie unter Ice-Neustarts Anwendungsfall und Beispiele im ICE-Neustart: Medien Umgehungs Anruf an einen Endpunkt übertragen, der keine medienumgehung unterstützt</span><span class="sxs-lookup"><span data-stu-id="b1728-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="b1728-140">[RFC RFC 5589 Session Initiation Protocol (SIP)-Anrufsteuerung – Übertragung](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="b1728-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="b1728-141">[RFC 3960 Early Media und Klingelton Generierung im Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), siehe Abschnitte 3,1, Forking und 3,2, Klingelton Generierung</span><span class="sxs-lookup"><span data-stu-id="b1728-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="b1728-142">RFC 5389-Sitzungs Traversal-Dienstprogramme für NAT (Stun)</span><span class="sxs-lookup"><span data-stu-id="b1728-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="b1728-143">RFC 5766 Traversal mit Relays um NAT (wiederum): Relay-Erweiterungen zu Session Traversal Utilities für NAT (Stun)</span><span class="sxs-lookup"><span data-stu-id="b1728-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="b1728-144">Standards, die für die Unterstützung der Übermittlung von Standortinformationen an E911-Anbieter gelten</span><span class="sxs-lookup"><span data-stu-id="b1728-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="b1728-145">RFC 6442, Standortübertragung für das Sitzungs Initiierungs Protokoll</span><span class="sxs-lookup"><span data-stu-id="b1728-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="b1728-146">Abweichungen von der RFC</span><span class="sxs-lookup"><span data-stu-id="b1728-146">Deviations from the RFC's</span></span>

<span data-ttu-id="b1728-147">In der folgenden Tabelle sind die Abschnitte der RFC (s) aufgeführt, in denen die Implementierung des SIP-oder Medien Stapels von Microsoft vom Standard abweicht:</span><span class="sxs-lookup"><span data-stu-id="b1728-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="b1728-148">RFC und Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b1728-148">RFC and sections</span></span> | <span data-ttu-id="b1728-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1728-149">Description</span></span> | <span data-ttu-id="b1728-150">Abweichung</span><span class="sxs-lookup"><span data-stu-id="b1728-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="b1728-151">RFC 6337, Abschnitt 5,3 halten und Fortsetzen von Medien</span><span class="sxs-lookup"><span data-stu-id="b1728-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="b1728-152">RFC ermöglicht die Verwendung von "a = inaktiv", "a = sendonly", a = recvonly ", um einen Anruf in Wartestellung zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="b1728-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="b1728-153">Der SIP-Proxy unterstützt nur "a = inaktiv" und versteht nicht, ob der SBC "a = sendonly" oder "a = recvonly" sendet.</span><span class="sxs-lookup"><span data-stu-id="b1728-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="b1728-154">RFC 6337, Abschnitt 5,4 "Verhalten beim Empfangen von SDP mit c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="b1728-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="b1728-155">[RFC3264](https://tools.ietf.org/html/rfc3264) erfordert, dass ein Agent SDP mit einer Verbindungsadresse von 0.0.0.0 empfangen kann, in diesem Fall bedeutet dies, dass weder RTP noch RTCP an den Peer gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b1728-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="b1728-156">Diese Option wird vom SIP-Proxy nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1728-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="b1728-157">Betriebsmodi</span><span class="sxs-lookup"><span data-stu-id="b1728-157">Operational modes</span></span>

<span data-ttu-id="b1728-158">Es gibt zwei Betriebsmodi für das direkte Routing:</span><span class="sxs-lookup"><span data-stu-id="b1728-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="b1728-159">**Ohne medienumgehung** , bei der der gesamte RTP-Datenverkehr zwischen dem Teams-Client, den Medien Prozessoren und dem SBC fließt.</span><span class="sxs-lookup"><span data-stu-id="b1728-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="b1728-160">**Mit medienumgehung** , bei der alle RTP-Medien zwischen den Endpunkten der Teams und dem SBC fließen.</span><span class="sxs-lookup"><span data-stu-id="b1728-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="b1728-161">Beachten Sie, dass der SIP-Datenverkehr immer über den SIP-Proxy fließt.</span><span class="sxs-lookup"><span data-stu-id="b1728-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
