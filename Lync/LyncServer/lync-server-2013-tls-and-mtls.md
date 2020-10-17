---
title: 'Lync Server 2013: TLS und MTLS'
description: 'Lync Server 2013: TLS und MTLS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ccee47e635435dd5f0d5eae03711c0cd5e517b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541791"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="0da3a-103">TLS und MTLS für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da3a-103">TLS and MTLS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0da3a-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0da3a-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0da3a-105">TLS-(Transport Layer Security) und MTLS-Protokolle (Mutual Transport Layer Security) bieten verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet.</span><span class="sxs-lookup"><span data-stu-id="0da3a-105">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="0da3a-106">Microsoft lync Server 2013 verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="0da3a-106">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="0da3a-107">Die gesamte SIP-Kommunikation zwischen den Servern erfolgt über MTLS.</span><span class="sxs-lookup"><span data-stu-id="0da3a-107">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="0da3a-108">Die SIP-Kommunikation von Client zu Server erfolgt über TLS.</span><span class="sxs-lookup"><span data-stu-id="0da3a-108">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="0da3a-109">Mit TLS können Benutzer über Ihre Client Software die lync Server 2013 Server authentifizieren, mit denen Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="0da3a-109">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="0da3a-110">Bei einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an.</span><span class="sxs-lookup"><span data-stu-id="0da3a-110">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="0da3a-111">Ein gültiges Zertifikat muss von einer auch für den Client vertrauenswürdigen Zertifizierungsstelle ausgegeben worden sein, und der DNS-Name des Servers muss mit dem DNS-Namen des Zertifikats übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0da3a-111">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="0da3a-112">Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel zu verschlüsseln, die zur Kommunikation verwendet werden sollen, damit nur der ursprüngliche Besitzer des Zertifikats den privaten Schlüssel zum Entschlüsseln der Kommunikationsinhalte verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="0da3a-112">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="0da3a-113">Die daraus resultierende Verbindung ist vertrauenswürdig, und im weiteren Verlauf wird keine Authentifizierung von anderen vertrauenswürdigen Servern oder Clients angefordert.</span><span class="sxs-lookup"><span data-stu-id="0da3a-113">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="0da3a-114">In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten auf TLS-Basis zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0da3a-114">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="0da3a-115">Server-zu-Server-Verbindungen basieren auf MTLS für die gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0da3a-115">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="0da3a-116">Bei einer MTLS-Verbindung wird der Server mit einer Nachricht und dem empfangenden Server mit Exchange-Zertifikaten von einer gegenseitig vertrauenswürdigen Zertifizierungsstelle verbunden.</span><span class="sxs-lookup"><span data-stu-id="0da3a-116">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="0da3a-117">Die Zertifikate beweisen die Identität der einzelnen Server auf der anderen.</span><span class="sxs-lookup"><span data-stu-id="0da3a-117">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="0da3a-118">In lync Server 2013 Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die während des Gültigkeitszeitraums von der ausstellenden Zertifizierungsstelle nicht widerrufen werden, automatisch von allen internen Clients und Servern als gültig betrachtet, da alle Mitglieder einer Active Directory Domäne der Unternehmenszertifizierungsstelle in dieser Domäne vertrauen.</span><span class="sxs-lookup"><span data-stu-id="0da3a-118">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="0da3a-119">In Verbundszenarien muss die ausstellende Zertifizierungsstelle von beiden Verbundpartnern als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="0da3a-119">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="0da3a-120">Jeder Partner kann bei Bedarf eine andere Zertifizierungsstelle verwenden, solange die Zertifizierungsstelle auch vom anderen Partner als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="0da3a-120">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="0da3a-121">Diese Vertrauensstellung kann am einfachsten durch die Edgeserver mit dem Zertifikat der Stammzertifizierungsstelle des Partners in ihren vertrauenswürdigen Stammzertifizierungsstellen oder durch die Verwendung einer Drittanbieter-Zertifizierungsstelle erreicht werden, die von beiden Seiten als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="0da3a-121">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="0da3a-122">TLS und MTLS helfen, Abhör-und man-in-the-Middle-Angriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="0da3a-122">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="0da3a-123">Bei einem man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten über den Computer des Angreifers ohne das Wissen einer Partei weiter.</span><span class="sxs-lookup"><span data-stu-id="0da3a-123">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="0da3a-124">TLS-und lync Server 2013 Spezifikation vertrauenswürdiger Server (nur die im Topologie-Generator angegebenen) mindern das Risiko eines man-in-the-Middle-Angriffs teilweise auf der Anwendungsebene mithilfe von End-to-End-Verschlüsselung, die mithilfe der Kryptografie mit öffentlichen Schlüsseln zwischen den beiden Endpunkten koordiniert wird. ein Angreifer muss über ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel verfügen und für den Namen des Diensts ausgegeben werden, mit dem der Client kommuniziert, um die Kommunikation zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="0da3a-124">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="0da3a-125">Letztendlich müssen Sie jedoch die besten Sicherheitsmethoden mit Ihrer Netzwerkinfrastruktur befolgten (in diesem Fall Corporate DNS).</span><span class="sxs-lookup"><span data-stu-id="0da3a-125">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="0da3a-126">Lync Server 2013 geht davon aus, dass der DNS-Server auf die gleiche Weise wie Domänencontrollern und globalen Katalogen als vertrauenswürdig eingestuft wird, aber DNS bietet eine Schutzebene gegen DNS-Hijack-Angriffe, indem verhindert, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gefälschten Namen antwortet.</span><span class="sxs-lookup"><span data-stu-id="0da3a-126">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="0da3a-127">In der folgenden Abbildung wird auf einer hohen Ebene gezeigt, wie lync Server 2013 MTLS verwendet, um ein Netzwerk vertrauenswürdiger Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0da3a-127">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="0da3a-128">**Vertrauenswürdige Verbindungen in einem Lync Server-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="0da3a-128">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="0da3a-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="0da3a-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

