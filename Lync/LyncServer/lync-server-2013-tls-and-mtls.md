---
title: 'Lync Server 2013: TLS und MTLS'
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
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="9e999-102">TLS und MTLS für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e999-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e999-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9e999-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9e999-104">Die Protokolle „Transport Layer Security“ (TLS) und „Mutual Transport Layer Security“ (MTLS) bieten eine verschlüsselte Kommunikation und Endpunktauthentifizierung im Internet.</span><span class="sxs-lookup"><span data-stu-id="9e999-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="9e999-105">Microsoft lync Server 2013 verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="9e999-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="9e999-106">Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt.</span><span class="sxs-lookup"><span data-stu-id="9e999-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="9e999-107">SIP-Kommunikation vom Client zum Server findet über TLS statt.</span><span class="sxs-lookup"><span data-stu-id="9e999-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="9e999-108">TLS ermöglicht Benutzern über Ihre Client Software, die lync Server 2013-Server zu authentifizieren, mit denen Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="9e999-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="9e999-109">In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an.</span><span class="sxs-lookup"><span data-stu-id="9e999-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="9e999-110">Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9e999-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="9e999-111">Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9e999-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="9e999-112">Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt.</span><span class="sxs-lookup"><span data-stu-id="9e999-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="9e999-113">In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9e999-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="9e999-114">Server-zu-Server-Verbindungen nutzen MTLS für die gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9e999-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="9e999-115">Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus.</span><span class="sxs-lookup"><span data-stu-id="9e999-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="9e999-116">Die Zertifikate beweisen jedem Server die Identität des anderen.</span><span class="sxs-lookup"><span data-stu-id="9e999-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="9e999-117">In lync Server 2013-Bereitstellungen werden von der Unternehmenszertifizierungsstelle ausgestellte Zertifikate, die sich während Ihres Gültigkeitszeitraums befinden und von der ausstellenden Zertifizierungsstelle nicht widerrufen werden, automatisch für alle internen Clients und Server als gültig erachtet, weil alle Mitglieder einer Active Directory-Domäne Vertrauen Sie der Unternehmenszertifizierungsstelle in dieser Domäne.</span><span class="sxs-lookup"><span data-stu-id="9e999-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="9e999-118">In Verbundszenarien muss die ausstellende Zertifizierungsstelle für beide Verbundpartner vertrauenswürdig sein.</span><span class="sxs-lookup"><span data-stu-id="9e999-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="9e999-119">Jeder Partner kann auf Wunsch eine andere Zertifizierungsstelle verwenden, solange diese Zertifizierungsstelle auch für den anderen Partner vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="9e999-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="9e999-120">Diese Vertrauenswürdigkeit wird am einfachsten erreicht, wenn die Edgeserver das Zertifikat der Stammzertifizierungsstelle des Partners in den vertrauenswürdigen Stammzertifizierungsstellen haben oder eine Zertifizierungsstelle von Drittanbietern verwendet wird, die für beide Beteiligte vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="9e999-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="9e999-121">TLS und MTLS verhindern Lauschangriffe und Man-in-the-Middle-Angriffe.</span><span class="sxs-lookup"><span data-stu-id="9e999-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="9e999-122">Ein Man-in-the-Middle-Angriff leitet die Kommunikation zwischen zwei Netzwerkeinheiten ohne Wissen einer der beiden Parteien über den Computer des Angreifers um.</span><span class="sxs-lookup"><span data-stu-id="9e999-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="9e999-123">TLS-und lync Server 2013-Spezifikation von vertrauenswürdigen Servern (nur die im Topologie-Generator angegebenen) verringern das Risiko eines man-in-the-Middle-Angriffs teilweise auf der Anwendungsschicht, indem die durchgängige Verschlüsselung mithilfe der Kryptografie mit öffentlichem Schlüssel koordiniert wird. zwischen den beiden Endpunkten und ein Angreifer ein gültiges und vertrauenswürdiges Zertifikat mit dem zugehörigen privaten Schlüssel haben und für den Namen des Diensts ausgestellt werden muss, zu dem der Client kommuniziert, um die Kommunikation zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="9e999-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="9e999-124">Letztendlich müssen Sie jedoch die besten Sicherheitsmethoden für Ihre Netzwerkinfrastruktur (in diesem Fall Corporate DNS) befolgen.</span><span class="sxs-lookup"><span data-stu-id="9e999-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="9e999-125">Lync Server 2013 geht davon aus, dass der DNS-Server auf die gleiche Weise als vertrauenswürdig eingestuft wird wie Domänencontroller und globale Kataloge, doch DNS bietet eine Schutzebene gegen DNS-Hijack-Angriffe, indem verhindert wird, dass der Server eines Angreifers erfolgreich auf eine Anforderung an den gefälschten Namen.</span><span class="sxs-lookup"><span data-stu-id="9e999-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="9e999-126">Die folgende Abbildung zeigt auf einer hohen Ebene, wie lync Server 2013 die Verwendung von MTLS zum Erstellen eines Netzwerks vertrauenswürdiger Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e999-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="9e999-127">**Vertrauenswürdige Verbindungen in einem lync Server-Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="9e999-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="9e999-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="9e999-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

