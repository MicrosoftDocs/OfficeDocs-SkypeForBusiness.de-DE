---
title: DNS-Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c7b36448f2aa8eb895aebeeaddc6187c1831ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501192"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5e923-102">DNS-Zusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e923-103">_**Letztes Änderungsstand des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="5e923-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="5e923-104">Die Domain Name System (DNS) Datensätze, die zum Definieren eines Verbunds mit Office Communications Server oder lync Server Partnern erforderlich sind, werden durch ihre Entscheidung bestimmt, die automatische DNS-Ermittlung Ihrer Domäne durch andere Perspective-Partner zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="5e923-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="5e923-105">Wenn Sie die \_ sipfederationtls veröffentlichen. \_ TCP.</span><span class="sxs-lookup"><span data-stu-id="5e923-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="5e923-106">*\<SIP domain name\>* SRV-Eintrag, kann jede andere SIP-Verbunddomäne ihren Partnerverbund "ermitteln".</span><span class="sxs-lookup"><span data-stu-id="5e923-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="5e923-107">Sie können steuern, welche Verbunddomänen mit Ihnen kommunizieren können, indem Sie die Einstellungen für Domänen und Blockierte Domänen in der lync Server-Systemsteuerung zulassen oder die Konfiguration der zugelassenen oder blockierten Domänen mithilfe der lync Server-Verwaltungsshell und der Cmdlets **Get**, **Sets**, **New**, **Remove-CsAllowedDomain** und **-CsBlockedDomain** festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e923-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="5e923-108">Weitere Informationen zum Konfigurieren dieser Einstellungen und zur Verwendung der PowerShell-Cmdlets finden Sie unter " **Verwandte Themen** " am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="5e923-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="5e923-109">In der Zusammenfassungstabelle für DNS-Einträge werden die erforderlichen Einträge für einen geöffneten oder auffindbaren Partnerverbund dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5e923-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="5e923-110">Wenn Sie die Verbund Ermittlung nicht implementieren möchten, können Sie sich dafür entscheiden, die sipfederationtls nicht zu konfigurieren \_ . \_ TCP.</span><span class="sxs-lookup"><span data-stu-id="5e923-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="5e923-111">*\<SIP domain name\>* Datensatz.</span><span class="sxs-lookup"><span data-stu-id="5e923-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5e923-112">Es gibt bestimmte Szenarien, in denen Sie über das _sipfederationtls. _tcp verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="5e923-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="5e923-113"><EM> &lt; SIP-Domänen &gt; Namen</EM> -SRV-Eintrag, aber Sie möchten keinen auffindbaren Partnerverbund haben.</span><span class="sxs-lookup"><span data-stu-id="5e923-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="5e923-114">Eine solche Instanz ist der Ort, an dem Sie die Mobilität für Ihre Benutzer bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="5e923-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="5e923-115">Das Mobility Push Notification Clearing House (PNCH) ist ein spezieller Verbundtyp, der für Microsoft lync Mobile-Clients auf Apple iPhone oder iPad mit dem lync 2010 Mobile-Client oder Windows Phone mit dem lync 2010 Mobile oder lync 2013 mobilen Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e923-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="5e923-116">Die _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="5e923-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="5e923-117"><EM> &lt; SIP-Domänen &gt; Namen</EM> -SRV-Eintrag wird im Fall von Mobilität und Push-Benachrichtigung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e923-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="5e923-118">Um dieses Problem zu beheben und die Auffindbarkeit zu kontrollieren, deaktivieren Sie die Einstellung <STRONG>Aktivieren der Partnerdomänen Suche</STRONG> , um die Ermittlung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e923-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="5e923-119">Zum Konfigurieren von xmpp (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS-Einträge (Domain Name System) auf einem externen DNS-Server, mit dem die Datensätze in die Zugriffs-Edgedienst ihrer Edgeserver oder Edgepool aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5e923-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="5e923-120">Wenn Sie DNS (Domain Name System) für die Verbindung mit öffentlichen Instant Messaging-Diensten konfigurieren, werden Sie feststellen, dass die Konfiguration, die externe Benutzer unterstützt, öffentliche Chat Verbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e923-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="5e923-121">Wenn Sie Ihre Edgeserver oder Edgepool bereits konfiguriert haben, sollten Sie über die erforderlichen DNS-Einträge für die Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten verfügen.</span><span class="sxs-lookup"><span data-stu-id="5e923-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="5e923-122">DNS-Zusammenfassung-SIP-Partnerverbund einschließlich der Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="5e923-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e923-123">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="5e923-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5e923-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="5e923-124">FQDN</span></span></th>
<th><span data-ttu-id="5e923-125">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="5e923-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5e923-126">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="5e923-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e923-127">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="5e923-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="5e923-128">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="5e923-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5e923-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e923-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5e923-130">Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung ihres Verbunds für andere potenzielle Verbundpartner erforderlich ist, und wird als "zugelassene SIP-Domänen" bezeichnet ("Enhanced Federation" in früheren Versionen genannt). Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="5e923-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="5e923-131">Dieser SRV-Eintrag ist für die Mobilität und das Push Notification Clearing House erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5e923-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="5e923-132">Wenn es mehr als eine SIP-Domäne gibt, erstellen und veröffentlichen Sie einen SRV-Eintrag für jede Domäne, die lync Mobile-Clients haben wird.</span><span class="sxs-lookup"><span data-stu-id="5e923-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="5e923-133">Der Push-Benachrichtigungsdienst und der Apple Push Notification-Dienst funktionieren möglicherweise nicht wie erwartet, wenn kein expliziter SRV-Eintrag für jede SIP-Domäne vorhanden ist, die von der Bereitstellung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5e923-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="5e923-134">DNS-Zusammenfassung – xmpp (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="5e923-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e923-135">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="5e923-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5e923-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="5e923-136">FQDN</span></span></th>
<th><span data-ttu-id="5e923-137">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="5e923-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="5e923-138">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="5e923-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e923-139">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="5e923-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="5e923-140">_xmpp-Server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="5e923-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5e923-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e923-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5e923-142">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder eine auf den lync-aktivierten Benutzer angewendete Benutzerrichtlinie zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="5e923-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="5e923-143">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5e923-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="5e923-144">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="5e923-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e923-145">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="5e923-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5e923-146">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="5e923-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="5e923-147">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="5e923-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="5e923-148">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="5e923-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="5e923-149">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="5e923-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e923-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e923-150">See Also</span></span>


[<span data-ttu-id="5e923-151">Einrichten des XMPP-Verbunds in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="5e923-152">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="5e923-153">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="5e923-154">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="5e923-155">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="5e923-156">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e923-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

