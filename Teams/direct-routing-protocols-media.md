---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888574"
---
# <a name="overview"></a><span data-ttu-id="34d95-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="34d95-103">Overview</span></span>

<span data-ttu-id="34d95-104">In diesem Artikel wird beschrieben, wie das direkte Routing die medienumgehung mit einem für Ice lite aktivierten Session Border Controller (SBC) unterstützt, wie in [RFC 5245](https://tools.ietf.org/html/rfc5245)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34d95-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="34d95-105">Dieser Artikel richtet sich an sprach Administratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="34d95-106">Dieser Artikel enthält eine Übersicht über die Ice lite-Szenarien und die Anforderungen für die Interoperabilität.</span><span class="sxs-lookup"><span data-stu-id="34d95-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="34d95-107">In diesem Artikel werden die Nachrichtenformate und die erforderlichen Zustandsautomaten Übergänge beschrieben, um eine zuverlässige Anruf-und Medien Übermittlung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="34d95-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="34d95-108">Terminologie</span><span class="sxs-lookup"><span data-stu-id="34d95-108">Terminology</span></span>

- <span data-ttu-id="34d95-109">Erster Gruß – die ersten Worte, die vom Anrufer und angerufenen gesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="34d95-110">Es ist wichtig, dass alle Anstrengungen unternommen werden, um sicherzustellen, dass die ersten Pakete von den Endpunkten für die meisten Anwendungsfälle zuverlässig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="34d95-111">Forking – das Angebot des Anrufers wird möglicherweise an mehrere Endpunkte übermittelt, wenn der aufgerufene auf mehreren Geräten zur Verfügung steht (beispielsweise kann ein Team Benutzer in Teams für Windows und Teams für Android oder iPhone angemeldet sein).</span><span class="sxs-lookup"><span data-stu-id="34d95-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="34d95-112">Provisorische Antwort (183) – die Endpunkte für Anrufer für eine schnellere Anrufeinrichtung senden Sie eine Antwort mit den Kandidaten und Schlüsseln, die zum Einrichten des Medienflusses erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="34d95-113">Dies erfolgt in Erwartung des Benutzers, der den Anruf (200OK) möglicherweise von dieser bestimmten aufgerufenen Instanz aus beantwortet.</span><span class="sxs-lookup"><span data-stu-id="34d95-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="34d95-114">Mit Forking sollte der Anrufer bereit sein, mehrere provisorische Antworten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34d95-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="34d95-115">Re-invite – Angebot mit endgültigen Kandidaten, die vom ICE-Controlling-Endpunkt ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="34d95-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="34d95-116">Dies hat das a = Remote-Candidate-Attribut, um alle Racebedingungen von der Behandlung mehrerer Gabeln zu lösen.</span><span class="sxs-lookup"><span data-stu-id="34d95-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="34d95-117">Teams-Endpunkt – Dies kann entweder ein Server (medienprozessor, Transport Relay) oder der Client für Teams sein.</span><span class="sxs-lookup"><span data-stu-id="34d95-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="34d95-118">Nachrichtenformat</span><span class="sxs-lookup"><span data-stu-id="34d95-118">Message format</span></span>

<span data-ttu-id="34d95-119">Die Teams-Infrastruktur folgt RFC 5245 für Ice-lite.</span><span class="sxs-lookup"><span data-stu-id="34d95-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="34d95-120">Dies impliziert, dass alle Stun-Nachrichten mit [RFC 5389](https://tools.ietf.org/html/rfc5389)kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="34d95-121">Das SBCS, wie es in RFC 5389 erforderlich ist, muss alle Betäubungs Attribute ignorieren, die Sie nicht erkennen, und die Nachrichten mit den bekannten Attributen weiterverarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34d95-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="34d95-122">Wenn fehlerhafte Pakete empfangen werden, müssen die Pakete verworfen werden, ohne dass dies Auswirkungen auf die Einrichtung der Mediensitzung hat.</span><span class="sxs-lookup"><span data-stu-id="34d95-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="34d95-123">Ice lite-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34d95-123">ICE Lite requirements</span></span>

<span data-ttu-id="34d95-124">In diesem Abschnitt werden die Anforderungen für Ice lite kurz erfasst.</span><span class="sxs-lookup"><span data-stu-id="34d95-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="34d95-125">Kandidaten Sammlung</span><span class="sxs-lookup"><span data-stu-id="34d95-125">Candidate gathering</span></span>

<span data-ttu-id="34d95-126">Der SBC muss nur einen Kandidaten anbieten, der öffentlich erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="34d95-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="34d95-127">Derzeit werden nur IPv4-Kandidaten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34d95-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="34d95-128">Verbindungs Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="34d95-128">Connectivity checks</span></span>

<span data-ttu-id="34d95-129">Die Ice lite-Implementierung muss auf alle empfangenen Verbindungs Überprüfungen Antworten.</span><span class="sxs-lookup"><span data-stu-id="34d95-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="34d95-130">Der Ice lite-Endpunkt darf keine Verbindungs Prüfanforderungen senden.</span><span class="sxs-lookup"><span data-stu-id="34d95-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="34d95-131">(Wenn Verbindungs Überprüfungen verstoßen werden, wird die vollständige Implementierung beantwortet, was dazu führen kann, dass unerwartete Peer-abgeleitete Kandidaten erkannt werden und möglicherweise zu Anruf Fehlern führen.)</span><span class="sxs-lookup"><span data-stu-id="34d95-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="34d95-132">Nominierungen</span><span class="sxs-lookup"><span data-stu-id="34d95-132">Nominations</span></span>

<span data-ttu-id="34d95-133">Der vollständige Implementierungs Endpunkt für ICE ist immer der steuernde Endpunkt und folgt "normalen" Nominierungen für die Auswahl der endgültigen Kandidaten, die für den Medienfluss verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="34d95-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="34d95-134">Der Ice lite-Endpunkt kann die Nominierungen verwenden, um den für Medien und die komplette Anrufeinrichtung zu verwendenden Pfad abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="34d95-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="34d95-135">Hinweis: bei der Verzweigung mit Peer Endpunkten, die 183 provisorische Antworten senden, muss der SBC bereit sein, auf Prüfungen von mehreren Endpunkten und auch Nominierungen von mehreren Endpunkten zu reagieren, wenn die Nominierungen vor 200OK erfolgen.</span><span class="sxs-lookup"><span data-stu-id="34d95-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="34d95-136">Je nach Konvergenz des ICE State Machine auf dem endgültigen Pfad und dem Zeitpunkt der Antwort des Benutzers können die Nominierungen vor oder nach dem 200OK erfolgen.</span><span class="sxs-lookup"><span data-stu-id="34d95-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="34d95-137">Der SBC muss in der Lage sein, beide Fälle zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34d95-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="34d95-138">Konvergierende für Verzweigung</span><span class="sxs-lookup"><span data-stu-id="34d95-138">Converging for forking</span></span>

<span data-ttu-id="34d95-139">Wenn das Angebot des SBC an mehrere Endpunkte für Teams abzweigt, können die Endpunkte der Teams mit einer provisorischen Antwort Antworten und Verbindungs Prüfungen starten.</span><span class="sxs-lookup"><span data-stu-id="34d95-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="34d95-140">Der SBC muss bereit sein, Verbindungs Überprüfungen zu empfangen und auf Verbindungs Überprüfungen von mehreren Peer Endpunkten zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="34d95-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="34d95-141">So kann beispielsweise der Benutzer von Teams sowohl auf einem Desktop-Computer als auch auf einem Mobiltelefon angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="34d95-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="34d95-142">Beide Geräte werden über den eingehenden Anruf benachrichtigt und versuchen, Verbindungs Prüfungen mit dem SBC durchführen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="34d95-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="34d95-143">Schließlich wird nur einer der Endpunkte den Anruf annehmen (200OK).</span><span class="sxs-lookup"><span data-stu-id="34d95-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="34d95-144">Beim Empfang des 200OK kann der SBC den richtigen Kontext für die Verarbeitung der Medienpakete einrichten.</span><span class="sxs-lookup"><span data-stu-id="34d95-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="34d95-145">Szenarien</span><span class="sxs-lookup"><span data-stu-id="34d95-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="34d95-146">Eingehender Anruf von SBC</span><span class="sxs-lookup"><span data-stu-id="34d95-146">Inbound call from SBC</span></span>

<span data-ttu-id="34d95-147">Für dieses Szenario gibt es mehrere mögliche Peer Endpunkte, die vom SBC behandelt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="34d95-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="34d95-148">Server Endpunkte werden in der Regel direkt mit 200OK beantwortet.</span><span class="sxs-lookup"><span data-stu-id="34d95-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="34d95-149">Hierbei handelt es sich um vollständige Ice-Endpunkte, die normalerweise in Szenarien für Voicemail, Anrufwarteschlange und automatische Telefonzentrale involviert sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="34d95-150">Client Endpunkte können mehrere provisorische Antworten mit unterschiedlichen from/to-Tags (183) senden, gefolgt von einem 200OK vom Endpunkt, der den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="34d95-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="34d95-151">Hierbei handelt es sich um vollständige Ice-Endpunkte, die Endbenutzer Clients darstellen.</span><span class="sxs-lookup"><span data-stu-id="34d95-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="34d95-152">Andere SBC-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="34d95-152">Other SBC endpoints.</span></span> <span data-ttu-id="34d95-153">Hierbei handelt es sich um Ice lite-Endpunkte, die normalerweise in das Szenario der gleichzeitigen Klingeln von Clientendpunkten und anderen Telefonnummern involviert sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="34d95-154">Der SBC muss auf alle gültigen Verbindungs Prüfungsanforderungen Antworten, die von den vollständigen Ice-Endpunkten empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="34d95-155">Pro RFC werden die vollständigen Ice-Endpunkte zu steuernden Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="34d95-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="34d95-156">Die Endpunkte der Teams (Client/Server) führen "reguläre" Nominierungen aus, um Verbindungs Prüfungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="34d95-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="34d95-157">Die endgültige 200Ok kann entweder von einem Endpunkt sein, der ein früheres Medium gesendet hat, oder von einem anderen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="34d95-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="34d95-158">Beim Empfang des 200Ok muss der SBC den richtigen Kontext für den Medienfluss einrichten.</span><span class="sxs-lookup"><span data-stu-id="34d95-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="34d95-159">Frühe Medien</span><span class="sxs-lookup"><span data-stu-id="34d95-159">Early media</span></span>

<span data-ttu-id="34d95-160">Wenn ein früher Medienfluss vorliegt, muss sich der SBC an den ersten Endpunkt verriegeln, der Streaming-Medien startet. der Medienfluss kann beginnen, bevor Kandidaten nominiert werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="34d95-161">Der SBC sollte in dieser Phase Unterstützung für das Senden von DTMF haben, um IVR/Voicemail-Szenarien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="34d95-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="34d95-162">Der SBC sollte den Pfad mit der höchsten Priorität verwenden, auf dem er überprüft hat, ob die Nominierungen nicht abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="34d95-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="34d95-163">Outbound-Anruf an SBC</span><span class="sxs-lookup"><span data-stu-id="34d95-163">Outbound call to SBC</span></span>

<span data-ttu-id="34d95-164">Die Endpunkte der Teams sind der Aufrufer für dieses Szenario und der steuernde Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="34d95-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="34d95-165">Beim Empfang einer provisorischen Antwort (183) oder einer endgültigen Antwort (200OK) startet der Team-Endpunkt Verbindungs Prüfungen und führt zu "normalen" Nominierungen, um die Verbindungs Prüfungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="34d95-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="34d95-166">Hinweis: Wenn der SBC eine provisorische Antwort (183) sendet, muss der SBC bereit sein, Verbindungs Prüfanforderungen zu empfangen und die Nominierungen möglicherweise abzuschließen, bevor der 200OK vom SBC gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="34d95-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="34d95-167">Wenn Schecks und/oder Nominierungen abgeschlossen werden, bevor die 200OK eingehen, werden die Überprüfungen und/oder Nominierungen nach Eingang von 200OK nicht mehr durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="34d95-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="34d95-168">Der SBC darf die Ice-Kandidaten, das Kennwort und den ufrag (username-Fragment) nicht zwischen 183 und 200 ändern.</span><span class="sxs-lookup"><span data-stu-id="34d95-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="34d95-169">Um frühe Medien zu unterstützen, kann der SBC mit dem Streaming der Medien an den Peer Ice-Kandidaten beginnen, wobei die höchste Priorität auf der Grundlage empfangener Verbindungs Überprüfungen liegt, noch bevor die Nominierungen vom Teams-Endpunkt abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="34d95-170">Der SBC sollte erwarten, dass Medien aus Teams an einem beliebigen Kandidaten, bis die Nominierungen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="34d95-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="34d95-171">Sobald ein Kandidat nominiert wurde, muss der SBC auf den richtigen Kontext zurückgesetzt werden, um Medienpakete zu senden und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="34d95-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="34d95-172">Anforderungen für die SRTP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34d95-172">SRTP support requirements</span></span>

<span data-ttu-id="34d95-173">Der SBC muss die SRTP-Verschlüsselungs Verschlüsselungs AES_CM_128_HMAC_SHA1_80 für Angebot und Antwort im folgenden Format unterstützen:</span><span class="sxs-lookup"><span data-stu-id="34d95-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="34d95-174">Der folgende Code ist ein Beispiel für das Crypto-Attribut im SDP-Angebot aus dem SBC:</span><span class="sxs-lookup"><span data-stu-id="34d95-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="34d95-175">Die Parameter MkII und length sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34d95-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="34d95-176">Weitere Informationen finden Sie in [RFC 4568, Abschnitt 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="34d95-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="34d95-177">SDES-Supportanforderungen</span><span class="sxs-lookup"><span data-stu-id="34d95-177">SDES support requirements</span></span>

<span data-ttu-id="34d95-178">Das Gerät muss SDES in dem Format anbieten können, wie nachstehend beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34d95-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="34d95-179">Microsoft Media Processors bevorzugen immer SDES.</span><span class="sxs-lookup"><span data-stu-id="34d95-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="34d95-180">Auch wenn ein Client nur DTLS unterstützt, werden die Medien Prozessoren in SDES konvertiert, wenn keine medienumgehung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="34d95-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="34d95-181">Wenn ein Client nur DTLS (zukünftiger Google Chrome-Status) ist, wird mit der medienumgehung ein MP-Element in den Pfad eingefügt, und der Anruf wird von der medienumgehung in die nicht-medienumgehung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="34d95-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="34d95-182">Zwischen der SBC-und der medienprozessor Komponente des direkten Routings wird immer SDES verwendet.</span><span class="sxs-lookup"><span data-stu-id="34d95-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="34d95-183">Derzeit gibt es keinen Team-Client, der nur DTLS bietet; Google hat jedoch angekündigt, dass Sie zu einem bestimmten Zeitpunkt die Unterstützung von SDES beenden werden.</span><span class="sxs-lookup"><span data-stu-id="34d95-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="34d95-184">Format für das Angebot von SBC im Bypass-Modus</span><span class="sxs-lookup"><span data-stu-id="34d95-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="34d95-185">Das Angebot muss SDES enthalten und kann DTLS optional im folgenden Format enthalten:</span><span class="sxs-lookup"><span data-stu-id="34d95-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="34d95-186">Format für Antwort mit SDES in SBC</span><span class="sxs-lookup"><span data-stu-id="34d95-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="34d95-187">Format für Angebot von Teams in SBC</span><span class="sxs-lookup"><span data-stu-id="34d95-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="34d95-188">Format für SDES-Angebot nur für SBC</span><span class="sxs-lookup"><span data-stu-id="34d95-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

