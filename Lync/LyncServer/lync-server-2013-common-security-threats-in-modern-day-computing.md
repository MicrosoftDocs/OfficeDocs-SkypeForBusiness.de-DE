---
title: 'Lync Server 2013: Häufige Sicherheitsbedrohungen in der modernen Datenverarbeitung'
description: 'Lync Server 2013: Häufige Sicherheitsbedrohungen in der modernen Tagesverarbeitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47284d91ea9f14e3bafadb1a285f6e98d9ea7ded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576991"
---
# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="d8fe1-103">Häufige Sicherheitsbedrohungen in der modernen Datenverarbeitung</span><span class="sxs-lookup"><span data-stu-id="d8fe1-103">Common security threats in modern day computing</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8fe1-104">_**Letztes Änderungsstand des Themas:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="d8fe1-104">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="d8fe1-105">Da es sich bei lync Server 2013 um ein Kommunikationssystem der Unternehmensklasse handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-105">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="d8fe1-106">Angriff mit kompromittierten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="d8fe1-106">Compromised-Key Attack</span></span>

<span data-ttu-id="d8fe1-107">Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-107">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="d8fe1-108">Es gibt zwei vertrauliche Schlüssel, die in der Public Key-Infrastruktur (PKI) verwendet werden, die berücksichtigt werden müssen:.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-108">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="d8fe1-109">Der private Schlüssel, den jeder Zertifikatbesitzer hat</span><span class="sxs-lookup"><span data-stu-id="d8fe1-109">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="d8fe1-110">Der Sitzungsschlüssel, der nach einer erfolgreichen Identifizierung und einem Sitzungsschlüssel Austausch durch die kommunizierenden Partner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-110">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="d8fe1-111">Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-111">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="d8fe1-112">Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-112">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="d8fe1-113">Lync Server 2013 verwendet die PKI-Funktionen im Windows Server-Betriebssystem, um die für die Verschlüsselung verwendeten Schlüsseldaten für die TLS-Verbindungen (Transport Layer Security) zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-113">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="d8fe1-114">Die für die Medienverschlüsselung verwendeten Tasten werden über TLS-Verbindungen ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-114">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="d8fe1-115">Denial-of-Service-Angriff auf das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="d8fe1-115">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="d8fe1-116">Der *Denial-of-Service-Angriff* tritt auf, wenn der Angreifer eine normale Netzwerknutzung und Funktion durch gültige Benutzer verhindert.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-116">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="d8fe1-117">Dies geschieht, wenn der Angreifer den Dienst mit legitimen Anforderungen überflutet, die die Verwendung des Diensts durch berechtigte Benutzer überfordern.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-117">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="d8fe1-118">Durch die Verwendung eines Denial-of-Service-Angriffs kann der Angreifer folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="d8fe1-118">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="d8fe1-119">Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-119">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="d8fe1-120">Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-120">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="d8fe1-121">Er kann die Spuren seines Angriffs vertuschen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-121">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="d8fe1-122">Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-122">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="d8fe1-123">Lauschangriffe (schnüffeln, schnüffeln)</span><span class="sxs-lookup"><span data-stu-id="d8fe1-123">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="d8fe1-124">*Lauschangriffe* können auftreten, wenn ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk erhält und über die Möglichkeit verfügt, den Datenverkehr zu überwachen und zu lesen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-124">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="d8fe1-125">Dies wird auch als *Sniffing* oder *Snooping*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-125">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="d8fe1-126">Wenn der Datenverkehr aus reinem Text besteht, kann der Angreifer ihn lesen, sobald er Zugriff auf den Pfad hat.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-126">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="d8fe1-127">Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-127">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="d8fe1-128">Die standardmäßige Empfehlung und Einstellung für den Datenverkehr in Microsoft lync Server 2013 besteht darin, MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS von Client zu Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-128">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="d8fe1-129">Diese Schutzmaßnahme würde einen Angriff innerhalb des Zeitraums, in dem eine bestimmte Unterhaltung stattfindet, sehr schwierig oder unmöglich machen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-129">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="d8fe1-130">TLS authentifiziert alle Parteien und verschlüsselt den gesamten Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-130">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="d8fe1-131">Dies verhindert nicht das Abhören, aber der Angreifer kann den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-131">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="d8fe1-132">Mit dem Relay-NAT-Protokoll (Umkehren) wird der Datenverkehr nicht verschlüsselt, und die gesendeten Informationen werden durch die Nachrichtenintegrität geschützt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-132">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="d8fe1-133">Obwohl es zum Abhören geöffnet ist, können die gesendeten Informationen (also die IP-Adressen und der Port) direkt extrahiert werden, indem Sie einfach die Quell-und Zieladressen der Pakete betrachten.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-133">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="d8fe1-134">Das A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem die Nachrichtenintegrität der Nachricht mithilfe des von einigen wenigen Elementen abgeleiteten Schlüssels überprüft wird, einschließlich eines Umdrehungs Kennworts, das nie in Klartext gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-134">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="d8fe1-135">Wenn SRTP (Secure Real Time Protocol) verwendet wird, wird der Mediendatenverkehr ebenfalls verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-135">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="d8fe1-136">Identitäts Spoofing (IP-Adress Spoofing)</span><span class="sxs-lookup"><span data-stu-id="d8fe1-136">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="d8fe1-137">*Spoofing* tritt auf, wenn der Angreifer die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet, ohne hierzu autorisiert zu sein.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-137">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="d8fe1-138">Ein erfolgreicher Angriff ermöglicht es dem Angreifer, zu funktionieren, als wäre der Angreifer die Entität, die normalerweise durch die IP-Adresse identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-138">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="d8fe1-139">Im Kontext von Microsoft lync Server 2013 kommt diese Situation nur dann ins Spiel, wenn ein Administrator die folgenden beiden Schritte ausgeführt hat:</span><span class="sxs-lookup"><span data-stu-id="d8fe1-139">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="d8fe1-140">Konfigurierte Verbindungen, die nur TCP (Transmission Control Protocol) unterstützen (Dies wird nicht empfohlen, da die TCP-Kommunikation nicht verschlüsselt ist).</span><span class="sxs-lookup"><span data-stu-id="d8fe1-140">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="d8fe1-141">Die IP-Adressen dieser Verbindungen wurden als vertrauenswürdige Hosts gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-141">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="d8fe1-142">Dies ist ein kleineres Problem bei TLS-Verbindungen (Transport Layer Security), da TLS alle Beteiligten authentifiziert und den gesamten Datenverkehr verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-142">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="d8fe1-143">Durch die Verwendung von TLS wird verhindert, dass ein Angreifer IP-Adress Spoofing für eine bestimmte Verbindung ausführt (beispielsweise gegenseitige TLS-Verbindungen).</span><span class="sxs-lookup"><span data-stu-id="d8fe1-143">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="d8fe1-144">Ein Angreifer kann jedoch weiterhin die Adresse des DNS-Servers spoofen, der von lync Server 2013 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-144">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="d8fe1-145">Da die Authentifizierung in lync jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das für die Spoofing einer der Parteien in der Kommunikation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-145">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="d8fe1-146">Man-in-the-Middle-Angriff</span><span class="sxs-lookup"><span data-stu-id="d8fe1-146">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="d8fe1-147">Ein man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern über den Computer des Angreifers ohne das Wissen der beiden kommunizierenden Benutzer umleitet.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-147">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="d8fe1-148">Der Angreifer kann den Datenverkehr überwachen und lesen, bevor er ihn an den beabsichtigten Empfänger sendet.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-148">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="d8fe1-149">Jeder Benutzer in der Kommunikation sendet unwissentlich Datenverkehr an den Angreifer und empfängt ihn, während er denkt, dass er nur mit dem vorgesehenen Benutzer kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-149">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="d8fe1-150">Dies kann passieren, wenn ein Angreifer Active Directory-Domänendienste ändern kann, um seinen Server als vertrauenswürdigen Server hinzuzufügen oder um Domain Name System (DNS) zu ändern, damit Clients auf dem Weg zum Server über den Angreifer eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-150">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="d8fe1-151">Ein man-in-the-Middle-Angriff kann auch mit dem Mediendatenverkehr zwischen zwei Clients auftreten.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-151">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="d8fe1-152">In Microsoft lync Server 2013 die gemeinsame Verwendung von Audio-, Video-und Anwendungsfreigaben mit mehreren Punkten wird jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-152">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="d8fe1-153">Server wie Gruppen Chat verwenden HTTPS, um die Sicherheit des Webdatenverkehrs zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-153">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="d8fe1-154">Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)</span><span class="sxs-lookup"><span data-stu-id="d8fe1-154">RTP Replay Attack</span></span>

<span data-ttu-id="d8fe1-155">Ein *Wiedergabeangriff* tritt auf, wenn eine gültige Medienübertragung zwischen zwei Parteien abgefangen und zu böswilligen Zwecken erneut übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-155">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="d8fe1-156">SRTP, das in Verbindung mit einem Secure Signaling-Protokoll verwendet wird, schützt Übertragungen vor Replay-Angriffen, indem es dem Empfänger ermöglicht, einen Index der bereits empfangenen RTP-Pakete beizubehalten und jedes neue Paket mit denen zu vergleichen, die bereits im Index aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-156">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="d8fe1-157">Spim</span><span class="sxs-lookup"><span data-stu-id="d8fe1-157">Spim</span></span>

<span data-ttu-id="d8fe1-158">*Spim* ist unerbetene kommerzielle Sofortnachrichten oder Anwesenheitsabonnementanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-158">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="d8fe1-159">Zwar selbst keine Kompromisse im Netzwerk, sondern im geringsten stört, kann Ressourcenverfügbarkeit und-Produktion reduzieren und möglicherweise zu einer Gefährdung des Netzwerks führen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-159">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="d8fe1-160">Ein Beispiel hierfür sind Benutzer, die sich gegenseitig durch Senden von Anforderungen Spimming.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-160">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="d8fe1-161">Benutzer können sich gegenseitig blockieren, um dies zu verhindern, aber mit dem Verbund, wenn ein koordinierter spim-Angriff hergestellt wird, kann dies nur schwer zu überwinden sein, wenn Sie den Partnerverbund nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-161">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="d8fe1-162">Viren und Würmer</span><span class="sxs-lookup"><span data-stu-id="d8fe1-162">Viruses and Worms</span></span>

<span data-ttu-id="d8fe1-163">Ein *Virus* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-163">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="d8fe1-164">Um zu funktionieren, benötigt ein Virus einen Host, beispielsweise eine Datei, eine e-Mail oder ein Programm.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-164">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="d8fe1-165">Ein *Wurm* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren, jedoch keinen Host benötigt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-165">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="d8fe1-166">Viren und Würmer werden in erster Linie bei Dateiübertragungen zwischen Clients oder beim Senden von URLs von anderen Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-166">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="d8fe1-167">Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und in Ihrem Namen Sofortnachrichten senden.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-167">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="d8fe1-168">Informationen zur Identifikation von Personen</span><span class="sxs-lookup"><span data-stu-id="d8fe1-168">Personally Identifiable Information</span></span>

<span data-ttu-id="d8fe1-169">Microsoft lync Server 2013 hat das Potenzial, Informationen über ein öffentliches Netzwerk offen zu geben, die möglicherweise mit einer Person verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-169">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="d8fe1-170">Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:</span><span class="sxs-lookup"><span data-stu-id="d8fe1-170">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="d8fe1-171">**Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer für die Freigabe oder nicht Freigabe über einen Link zu einem Verbundpartner oder mit Kontakten in einer Organisation auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-171">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="d8fe1-172">Diese Daten werden nicht für Benutzer in einem öffentlichen Chat Netzwerk freigegeben.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-172">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="d8fe1-173">Clientrichtlinien und andere Clientkonfigurationen können dem System Administrator eine gewisse Kontrolle versetzen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-173">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="d8fe1-174">In lync Server 2013 kann ein erweiterter Anwesenheitsdaten Schutzmodus für einen einzelnen Benutzer konfiguriert werden, um zu verhindern, dass lync-Benutzer die Anwesenheitsinformationen des Benutzers nicht in der Kontaktliste des Benutzers sehen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-174">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="d8fe1-175">Der Datenschutzmodus für verstärkte Anwesenheit hindert Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 nicht daran, die Anwesenheitsinformationen eines Benutzers zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-175">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="d8fe1-176">Ausführliche Informationen finden Sie unter [What es New for Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in der Dokumentation "erste Schritte" und [Konfigurieren des Datenschutzmodus für erweiterte Anwesenheit in lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-176">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="d8fe1-177">**Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen nicht der Kontrolle der Client-oder Systemverwaltung.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-177">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="d8fe1-178">Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-178">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="d8fe1-179">In den folgenden Tabellen sind die Daten aufgeführt, die über ein öffentliches Netzwerk verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d8fe1-179">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="d8fe1-180">Erweiterte Anwesenheitsdaten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-180">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8fe1-181">Offen gelegte Daten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-181">Data Disclosed</span></span></th>
<th><span data-ttu-id="d8fe1-182">Mögliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d8fe1-182">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8fe1-183">Persönliche Daten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-183">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-184">Name, Titel, Unternehmen, e-Mail-Adresse, Zeitzone</span><span class="sxs-lookup"><span data-stu-id="d8fe1-184">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fe1-185">Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="d8fe1-185">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-186">Geschäftlich, mobil, privat</span><span class="sxs-lookup"><span data-stu-id="d8fe1-186">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fe1-187">Kalenderdaten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-187">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-188">Frei/gebucht, out-of-Town Notice, Besprechungs Details (für Personen, die Zugriff auf Ihren Kalender haben)</span><span class="sxs-lookup"><span data-stu-id="d8fe1-188">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fe1-189">Anwesenheitsstatus</span><span class="sxs-lookup"><span data-stu-id="d8fe1-189">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-190">Abwesend, verfügbar, gebucht, nicht stören, offline</span><span class="sxs-lookup"><span data-stu-id="d8fe1-190">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="d8fe1-191">Pflichtdaten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-191">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8fe1-192">Offen gelegte Daten</span><span class="sxs-lookup"><span data-stu-id="d8fe1-192">Data Disclosed</span></span></th>
<th><span data-ttu-id="d8fe1-193">Beispiel Informationen</span><span class="sxs-lookup"><span data-stu-id="d8fe1-193">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8fe1-194">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8fe1-194">IP Address</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-195">Tatsächliche Computer- oder NAT-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8fe1-195">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fe1-196">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="d8fe1-196">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="d8fe1-197">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d8fe1-197">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

