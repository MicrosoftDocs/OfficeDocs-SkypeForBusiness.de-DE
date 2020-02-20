---
title: 'Lync Server 2013: Public Key-Infrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ba5224d6663050295c5fddf9ea08e230f78506
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="77303-102">Öffentliche Schlüsselinfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77303-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77303-103">_**Letztes Änderungsstand des Themas:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="77303-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="77303-104">Microsoft lync Server 2013 basiert auf Zertifikaten für die Serverauthentifizierung und zum Einrichten einer Vertrauenskette zwischen Clients und Servern sowie zwischen den verschiedenen Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="77303-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="77303-105">Die Windows Server 2012 R2-, Windows Server 2012-, Windows Server 2008 R2-, Windows Server 2008-und Windows Server 2003 Public Key-Infrastruktur (PKI) stellt die Infrastruktur zum Einrichten und validieren dieser Vertrauenskette bereit.</span><span class="sxs-lookup"><span data-stu-id="77303-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="77303-106">Zertifikate sind digitale IDs.</span><span class="sxs-lookup"><span data-stu-id="77303-106">Certificates are digital IDs.</span></span> <span data-ttu-id="77303-107">Sie identifizieren einen Server namentlich und geben seine Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="77303-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="77303-108">Um sicherzustellen, dass die Informationen in einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgestellt werden, die von Clients oder anderen Servern als vertrauenswürdig eingestuft wird, die eine Verbindung mit dem Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="77303-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="77303-109">Wenn der Server nur mit Clients und Servern in einem privaten Netzwerk eine Verbindung herstellt, kann eine Unternehmenszertifizierungsstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77303-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="77303-110">Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77303-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="77303-p103">Selbst wenn das Zertifikat gültige Informationen enthält, muss überprüft werden können, ob es sich bei dem Server, der das Zertifikat vorlegt, auch tatsächlich um den Server handelt, für den das Zertifikat ausgestellt wurde. Hier kommt die Public Key-Infrastruktur von Windows ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="77303-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="77303-p104">Jedes Zertifikat ist mit einem öffentlichen Schlüssel verknüpft. Der im Zertifikat genannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur dem Server bekannt ist. Ein Client oder Server, der eine Verbindung herstellt, verwendet den öffentlichen Schlüssel zum Verschlüsseln zufällig gewählter Informationen und sendet diese an den Server. Wenn der Server die Informationen entschlüsselt und im Nur-Text-Format zurücksendet, kann die Einheit, die eine Verbindung herstellt, sicher sein, dass der Server über den privaten Schlüssel für das Zertifikat verfügt und es sich somit um den im Zertifikat genannten Server handelt.</span><span class="sxs-lookup"><span data-stu-id="77303-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77303-117">Nicht alle öffentlichen CAS entsprechen den Anforderungen lync Server 2013 Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="77303-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="77303-118">Sehen Sie am besten in der Liste der zertifizierten Anbieter für öffentliche Zertifizierungsstellen nach.</span><span class="sxs-lookup"><span data-stu-id="77303-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="77303-119">Ausführliche Informationen finden Sie unter Unified Communications Certificate Partners <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>unter.</span><span class="sxs-lookup"><span data-stu-id="77303-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="77303-120">Sperrlisten-Verteilungspunkte</span><span class="sxs-lookup"><span data-stu-id="77303-120">CRL Distribution Points</span></span>

<span data-ttu-id="77303-121">Lync Server 2013 erfordert, dass alle Server Zertifikate mindestens einen Zertifikatsperrlisten-Verteilungspunkt (Certificate Revocation List, CRL) enthalten.</span><span class="sxs-lookup"><span data-stu-id="77303-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="77303-122">CRL-Verteilungspunkte (CDPs) sind Standorte, aus denen Zertifikatsperrlisten heruntergeladen werden können, um zu überprüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, nicht widerrufen wurde und sich das Zertifikat noch innerhalb des Gültigkeitszeitraums befindet.</span><span class="sxs-lookup"><span data-stu-id="77303-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="77303-123">Ein CRL-Verteilungs Pfad wird in den Eigenschaften des Zertifikats als URL vermerkt und ist in der Regel sicheres HTTP.</span><span class="sxs-lookup"><span data-stu-id="77303-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="77303-124">Erweiterte Schlüsselverwendung</span><span class="sxs-lookup"><span data-stu-id="77303-124">Enhanced Key Usage</span></span>

<span data-ttu-id="77303-125">Lync Server 2013 erfordert, dass alle Serverzertifikate zur Unterstützung der EKU (Enhanced Key Usage, EKU) für die Serverauthentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77303-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="77303-126">Das Konfigurieren des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat zum Zweck der Authentifizierung von Servern gültig ist.</span><span class="sxs-lookup"><span data-stu-id="77303-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="77303-127">Diese EKU ist für MTLS unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="77303-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="77303-128">Es ist möglich, mehr als einen Eintrag in der EKU zu haben, sodass das Zertifikat für mehrere Zwecke aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="77303-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77303-p108">Die Clientauthentifizierungs-EKU ist für ausgehende MTLS-Verbindungen von Live Communications Server 2003 und Live Communications Server 2005 erforderlich, wird jetzt aber nicht mehr benötigt. Diese EKU muss jedoch auf Edgeservern vorhanden sein, die über öffentliche Instant Messaging-Dienste eine Verbindung zu AOL herstellen.</span><span class="sxs-lookup"><span data-stu-id="77303-p108">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required. However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

