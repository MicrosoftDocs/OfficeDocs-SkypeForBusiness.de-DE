---
title: 'Lync Server 2013: Verschlüsselung'
description: 'Lync Server 2013: Verschlüsselung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575651"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="e8028-103">Verschlüsselung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8028-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8028-104">_**Letztes Änderungsstand des Themas:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="e8028-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="e8028-105">Microsoft lync Server 2013 verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="e8028-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="e8028-106">Der gesamte Datenverkehr zwischen den Servern erfordert MTLS, und zwar unabhängig davon, ob die Daten innerhalb des internen Netzwerks verbleiben oder den internen Netzwerkumkreis verlassen.</span><span class="sxs-lookup"><span data-stu-id="e8028-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="e8028-107">TLS ist optional, wird jedoch dringend zwischen dem Vermittlungsserver und dem Mediengateway empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e8028-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="e8028-108">Wenn TLS für diesen Link konfiguriert ist, ist MTLS erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e8028-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="e8028-109">Aus diesem Grund muss das Gateway mit einem Zertifikat von einer für den Vermittlungsserver vertrauenswürdigen Zertifizierungsstelle konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e8028-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8028-110">Eine Sicherheitsempfehlung zu SSL 3,0 wurde in 2014 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e8028-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="e8028-111">Das Deaktivieren von SSL 3,0 in lync Server 2013 ist eine unterstützte Option.</span><span class="sxs-lookup"><span data-stu-id="e8028-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="e8028-112">Weitere Informationen zur Sicherheitsempfehlung finden Sie unter <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="e8028-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="e8028-114">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="e8028-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e8028-115">Um sicherzustellen, dass das stärkste kryptografische Protokoll verwendet wird, bietet lync Server 2013 TLS-Verschlüsselungsprotokolle in der folgenden Reihenfolge für Clients an: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8028-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="e8028-116">TLS ist ein wichtiger Aspekt von lync Server 2013 und ist daher erforderlich, um eine unterstützte Umgebung beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="e8028-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="e8028-p104">Die Anforderungen für den Datenverkehr zwischen Clients sind davon abhängig, ob dieser Datenverkehr die interne Unternehmensfirewall durchquert. Für komplett internen Datenverkehr kann TLS oder TCP verwendet werden. (Lediglich bei TLS wird die Sofortnachricht verschlüsselt.)</span><span class="sxs-lookup"><span data-stu-id="e8028-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="e8028-119">In der folgenden Tabelle werden die Protokollanforderungen für die einzelnen Datenverkehrstypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8028-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="e8028-120">Schutz des Datenverkehrs</span><span class="sxs-lookup"><span data-stu-id="e8028-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8028-121">Datenverkehrstyp</span><span class="sxs-lookup"><span data-stu-id="e8028-121">Traffic type</span></span></th>
<th><span data-ttu-id="e8028-122">Geschützt durch</span><span class="sxs-lookup"><span data-stu-id="e8028-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8028-123">Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="e8028-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="e8028-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="e8028-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8028-125">Client-zu-Server</span><span class="sxs-lookup"><span data-stu-id="e8028-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="e8028-126">TLS</span><span class="sxs-lookup"><span data-stu-id="e8028-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8028-127">Sofortnachrichten und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="e8028-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="e8028-128">TLS (wenn für TLS konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="e8028-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8028-129">Audio-, Video- und Desktopfreigabe von Medien</span><span class="sxs-lookup"><span data-stu-id="e8028-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="e8028-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="e8028-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8028-131">Desktopfreigabe (Signaldaten)</span><span class="sxs-lookup"><span data-stu-id="e8028-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="e8028-132">TLS</span><span class="sxs-lookup"><span data-stu-id="e8028-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8028-133">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="e8028-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="e8028-134">TLS</span><span class="sxs-lookup"><span data-stu-id="e8028-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8028-135">Herunterladen von Besprechungsinhalten und Adressbüchern, Erweiterung der Verteilergruppe</span><span class="sxs-lookup"><span data-stu-id="e8028-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="e8028-136">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e8028-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="e8028-137">Medienverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e8028-137">Media Encryption</span></span>

<span data-ttu-id="e8028-138">Der Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport Protocol), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e8028-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="e8028-139">Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Mediationsserver und seinem internen Next Hop fließen, ebenfalls mit SRTP verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e8028-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="e8028-140">Medien, die in beide Richtungen zwischen dem Vermittlungsserver und einem Mediengateway fließen, werden standardmäßig nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e8028-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="e8028-141">Das Vermittlungsserver kann die Verschlüsselung für das Mediengateway unterstützen, das Gateway muss jedoch MTLS und das Speichern eines Zertifikats unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e8028-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8028-142">Audio/Video (A/V) wird mit der neuen Version von Windows Live Messenger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8028-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="e8028-143">Wenn Sie einen A/V-Partnerverbund mit Windows Live Messenger implementieren, müssen Sie auch die Microsoft Lync Server 2010-Verschlüsselungsstufe ändern.</span><span class="sxs-lookup"><span data-stu-id="e8028-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="e8028-144">Standardmäßig lautet die Verschlüsselungsstufe "Erforderlich".</span><span class="sxs-lookup"><span data-stu-id="e8028-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="e8028-145">Sie müssen diese Einstellung in unterstützt ändern, indem Sie die lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8028-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="e8028-146">Weitere Informationen finden Sie unter <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e8028-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e8028-147">Der Datenverkehr für Audio-und Video Medien wird nicht zwischen Microsoft lync 2013 und Windows Live-Clients verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e8028-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="e8028-148">FIPS</span><span class="sxs-lookup"><span data-stu-id="e8028-148">FIPS</span></span>

<span data-ttu-id="e8028-149">Lync Server 2013 und Microsoft Exchange Server 2013 arbeiten mit Unterstützung für FIPS (Federal Information Processing Standard) 140-2-Algorithmen, wenn die Windows Server-Betriebssysteme für die Verwendung der FIPS 140-2-Algorithmen für die Systemkryptografie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e8028-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="e8028-150">Um die FIPS-Unterstützung zu implementieren, müssen Sie jeden Server konfigurieren, der lync Server 2013 ausführt, um ihn zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e8028-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="e8028-151">Ausführliche Informationen zur Verwendung von FIPS-kompatiblen Algorithmen und zur Implementierung der FIPS-Unterstützung finden Sie im Microsoft Knowledge Base-Artikel 811833, die Auswirkungen der Aktivierung der Sicherheitseinstellung "System Kryptografie: FIPS-konforme Algorithmen für Verschlüsselung, Hashing und Signierung verwenden" unter Windows XP und in höheren Windows-Versionen unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="e8028-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="e8028-152">Ausführliche Informationen zur Unterstützung von FIPS 140-2 und zu Einschränkungen in Exchange 2010 finden Sie unter Exchange 2010 SP1 und Unterstützung für FIPS-konforme Algorithmen unter [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="e8028-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

