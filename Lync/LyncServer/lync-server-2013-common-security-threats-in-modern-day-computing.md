---
title: 'Lync Server 2013: häufige Sicherheitsrisiken in der modernen Computernutzung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="b9d18-102">Häufige Sicherheitsbedrohungen in der modernen EDV</span><span class="sxs-lookup"><span data-stu-id="b9d18-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9d18-103">_**Letztes Änderungsdatum des Themas:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="b9d18-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="b9d18-104">Da es sich bei lync Server 2013 um ein Kommunikationssystem auf Unternehmensniveau handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken können.</span><span class="sxs-lookup"><span data-stu-id="b9d18-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="b9d18-105">Angriff mit kompromittierten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="b9d18-105">Compromised-Key Attack</span></span>

<span data-ttu-id="b9d18-p101">Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. Bei der Infrastruktur öffentlicher Schlüssel (Public Key Infrastructure, PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="b9d18-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="b9d18-108">Der private Schlüssel, der sich im Besitz des jeweiligen Zertifikatinhabers befindet</span><span class="sxs-lookup"><span data-stu-id="b9d18-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="b9d18-109">Der Sitzungsschlüssel, der nach der erfolgreichen Identifikation und dem Sitzungsschlüsselaustausch durch die Kommunikationspartner verwendet wird</span><span class="sxs-lookup"><span data-stu-id="b9d18-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="b9d18-p102">Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="b9d18-112">Lync Server 2013 verwendet die PKI-Features im Windows Server-Betriebssystem, um die für die Verschlüsselung verwendeten Schlüsseldaten für die TLS-Verbindungen (Transport Layer Security) zu schützen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="b9d18-113">Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="b9d18-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="b9d18-114">Denial-of-Service-Angriff auf das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b9d18-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="b9d18-p104">Ein *Denial-of-Service-Angriff* liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Nutzer verhindert. Hierbei überfluten Angreifer den Dienst mit legitimen Anforderungen, sodass er für die berechtigten Nutzer nicht mehr erreichbar ist. Bei einem Denial-of-Service-Angriff eröffnen sich den Angreifern folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="b9d18-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="b9d18-118">Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="b9d18-119">Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.</span><span class="sxs-lookup"><span data-stu-id="b9d18-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="b9d18-120">Er kann die Spuren seines Angriffs vertuschen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="b9d18-121">Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.</span><span class="sxs-lookup"><span data-stu-id="b9d18-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="b9d18-122">Abhöraktionen ("Sniffing", "Snooping")</span><span class="sxs-lookup"><span data-stu-id="b9d18-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="b9d18-p105">*Abhöraktionen* sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies wird auch als „Schnüffeln“ (auch „Lauschangriff“, englisch *Sniffing* oder *Snooping*) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="b9d18-127">Die Standardempfehlung und-Einstellung für den Datenverkehr in Microsoft lync Server 2013 besteht darin, MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS vom Client zum Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="b9d18-128">Diese Schutzmaßnahme macht einen derartigen Angriff innerhalb der Zeitspanne, in der eine Unterhaltung erfolgt, äußerst schwer oder unmöglich.</span><span class="sxs-lookup"><span data-stu-id="b9d18-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="b9d18-129">Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr wird verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b9d18-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="b9d18-130">Damit können Abhöraktionen nicht verhindert werden, aber Angreifer können den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.</span><span class="sxs-lookup"><span data-stu-id="b9d18-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="b9d18-p107">Das TURN-Protokoll (Traversal Using Relay NAT) setzt keine Verschlüsselung des Datenverkehrs voraus. Die Daten, die darüber versendet werden, unterliegen dem Schutz durch die Nachrichtenintegrität. Es ist rein theoretisch möglich, sie abzuhören, aber die Informationen, die über das TURN-Protokoll gesendet werden (d. h. die IP-Adressen und der Port), können direkt extrahiert werden, indem die Quell- und Zieladressen der Pakete angezeigt werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des Schlüssels überprüft, der von bestimmten Objekten abgeleitet wird. Dazu gehört auch ein TURN-Kennwort, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, so wird auch der Mediendatenverkehr verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="b9d18-135">Identitätsvortäuschung (Spoofing der IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="b9d18-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="b9d18-136">*Spoofing* liegt vor, wenn Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermitteln und verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="b9d18-137">Nach einem erfolgreichen Angriff können sich Angreifer als die normalerweise durch diese IP-Adresse identifizierte Entität ausgeben.</span><span class="sxs-lookup"><span data-stu-id="b9d18-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="b9d18-138">Im Kontext von Microsoft lync Server 2013 tritt diese Situation nur dann in das Spiel ein, wenn ein Administrator die folgenden Schritte ausgeführt hat:</span><span class="sxs-lookup"><span data-stu-id="b9d18-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="b9d18-139">Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)</span><span class="sxs-lookup"><span data-stu-id="b9d18-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="b9d18-140">Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert.</span><span class="sxs-lookup"><span data-stu-id="b9d18-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="b9d18-141">Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b9d18-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="b9d18-142">Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual TLS-Verbindungen).</span><span class="sxs-lookup"><span data-stu-id="b9d18-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="b9d18-143">Ein Angreifer kann aber weiterhin die Adresse des DNS-Servers spoofen, der von lync Server 2013 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9d18-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="b9d18-144">Da die Authentifizierung in lync jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das zum Spoofing einer der Parteien in der Kommunikation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b9d18-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="b9d18-145">Man-in-the-Middle-Angriff</span><span class="sxs-lookup"><span data-stu-id="b9d18-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="b9d18-146">Von einem „Man-in-the-Middle-Angriff“ spricht man, wenn Angreifer die Kommunikation zwischen zwei Nutzern ohne deren Wissen über ihren eigenen Computer leiten.</span><span class="sxs-lookup"><span data-stu-id="b9d18-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="b9d18-147">Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="b9d18-148">Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b9d18-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="b9d18-149">Dies kann passieren, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie den DNS-Eintrag (Domain Name System) so ändern können, dass Clients auf ihrem Weg zum Server über den Computer der Angreifer geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="b9d18-150">Ein Man-in-the-Middle-Angriff kann auch bei Mediendatenverkehr zwischen zwei Clients erfolgen, wobei jedoch in skype16_server_short Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="b9d18-151">In Microsoft lync Server 2013 Punkt-zu-Punkt-Audio-, Video-und Anwendungsfreigabe werden Datenströme jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="b9d18-152">Server wie Gruppenchat nutzen HTTPS zur Erhöhung der Sicherheit des Webdatenverkehrs.</span><span class="sxs-lookup"><span data-stu-id="b9d18-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="b9d18-153">Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)</span><span class="sxs-lookup"><span data-stu-id="b9d18-153">RTP Replay Attack</span></span>

<span data-ttu-id="b9d18-p111">Bei einem *Angriff mit Aufzeichnungswiederholung* wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP können Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="b9d18-156">SPIM (Spam over Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="b9d18-156">Spim</span></span>

<span data-ttu-id="b9d18-p112">Unter *SPIM* sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="b9d18-161">Viren und Würmer</span><span class="sxs-lookup"><span data-stu-id="b9d18-161">Viruses and Worms</span></span>

<span data-ttu-id="b9d18-p113">Ein *Virus* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Für seine Arbeit benötigt der Virus einen Host, wie z. B. eine Datei, eine E-Mail oder ein Programm. Wie ein Virus ist ein *Wurm* ebenfalls eine Codeeinheit, die auf die Reproduktion zusätzlicher, ähnlicher Codeeinheiten programmiert ist. Im Gegensatz zum Virus wird jedoch kein Host benötigt. Viren und Würmer treten vornehmlich bei Dateiübertragungen zwischen Clients auf oder, wenn URLs von anderen Nutzern gesendet werden. Befindet sich auf Ihrem Computer ein Virus, kann er beispielsweise Ihre Identität verwenden und Chatnachrichten in Ihrem Namen senden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="b9d18-167">Informationen zur Identifikation von Personen</span><span class="sxs-lookup"><span data-stu-id="b9d18-167">Personally Identifiable Information</span></span>

<span data-ttu-id="b9d18-168">Microsoft lync Server 2013 hat das Potenzial, Informationen über ein öffentliches Netzwerk offenzulegen, die möglicherweise mit einer Person verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="b9d18-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="b9d18-169">Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:</span><span class="sxs-lookup"><span data-stu-id="b9d18-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="b9d18-170">**Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer für die Freigabe oder nicht Freigabe über einen Link zu einem Föderationspartner oder mit Kontakten in einer Organisation auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="b9d18-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="b9d18-171">Diese Daten werden nicht an Benutzer in einem öffentlichen IM-Netzwerk weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="b9d18-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="b9d18-172">Client-Richtlinien und andere Client-Konfigurationen können dem Systemadministrator eine gewisse Kontrolle verschaffen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="b9d18-173">In lync Server 2013 kann der Erweiterte Anwesenheitsdaten Schutzmodus für einen einzelnen Benutzer so konfiguriert werden, dass lync-Benutzer nicht in der Kontaktliste des Benutzers die Anwesenheitsinformationen des Benutzers sehen können.</span><span class="sxs-lookup"><span data-stu-id="b9d18-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="b9d18-174">Der Datenschutzmodus für erhöhte Anwesenheit verhindert nicht, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen.</span><span class="sxs-lookup"><span data-stu-id="b9d18-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="b9d18-175">Ausführliche Informationen finden Sie unter [Neuerungen für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in der Dokumentation "erste Schritte" und [Konfigurieren des Datenschutzmodus für erhöhte Anwesenheit in lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9d18-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b9d18-176">**Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen nicht der Kontrolle durch den Client oder die System Administration.</span><span class="sxs-lookup"><span data-stu-id="b9d18-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="b9d18-177">Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b9d18-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="b9d18-178">In den folgenden Tabellen wird angegeben, welche Daten über ein öffentliches Netzwerk offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b9d18-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="b9d18-179">Erweiterte Anwesenheitsdaten</span><span class="sxs-lookup"><span data-stu-id="b9d18-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9d18-180">Offengelegte Daten</span><span class="sxs-lookup"><span data-stu-id="b9d18-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="b9d18-181">Mögliche Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b9d18-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9d18-182">Persönliche Daten</span><span class="sxs-lookup"><span data-stu-id="b9d18-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="b9d18-183">Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone</span><span class="sxs-lookup"><span data-stu-id="b9d18-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d18-184">Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="b9d18-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="b9d18-185">Geschäftlich, mobil, privat</span><span class="sxs-lookup"><span data-stu-id="b9d18-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d18-186">Kalenderdaten</span><span class="sxs-lookup"><span data-stu-id="b9d18-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="b9d18-187">Frei/Gebucht, Abwesenheitsmitteilung, Besprechungsdetails (für Personen mit Zugriff auf Ihren Kalender)</span><span class="sxs-lookup"><span data-stu-id="b9d18-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d18-188">Anwesenheitsstatus</span><span class="sxs-lookup"><span data-stu-id="b9d18-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="b9d18-189">Abwesend, verfügbar, gebucht, nicht stören, offline</span><span class="sxs-lookup"><span data-stu-id="b9d18-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="b9d18-190">Pflichtdaten</span><span class="sxs-lookup"><span data-stu-id="b9d18-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9d18-191">Offengelegte Daten</span><span class="sxs-lookup"><span data-stu-id="b9d18-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="b9d18-192">Beispieldaten</span><span class="sxs-lookup"><span data-stu-id="b9d18-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9d18-193">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="b9d18-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="b9d18-194">Tatsächliche Computer- oder NAT-Adresse</span><span class="sxs-lookup"><span data-stu-id="b9d18-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d18-195">SIP-URI</span><span class="sxs-lookup"><span data-stu-id="b9d18-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="b9d18-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9d18-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

