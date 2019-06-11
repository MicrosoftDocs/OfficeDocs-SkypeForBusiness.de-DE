---
title: DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="825c5-102">DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="825c5-103">_**Letztes Änderungsdatum des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="825c5-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="825c5-104">Die DNS-Einträge (Domain Name System), die erforderlich sind, um einen Verbund mit Office Communications Server-oder lync Server-Partnern zu definieren, werden durch ihre Entscheidung bestimmt, die automatische DNS-Erkennung Ihrer Domäne durch andere Perspective-Partner zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="825c5-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="825c5-105">Wenn Sie die \_sipfederationtls veröffentlichen. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="825c5-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="825c5-106">*SIP-Domänenname\> \<* SRV-Eintrag, kann jede andere SIP-Verbunddomäne ihren Verbund "entdecken".</span><span class="sxs-lookup"><span data-stu-id="825c5-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="825c5-107">Sie können steuern, welche Verbunddomänen mit Ihnen kommunizieren können, indem Sie die Einstellungen Domänen und Blockierte Domänen in der lync Server-Systemsteuerung zulassen oder die Konfiguration der zugelassenen oder blockierten Domänen mithilfe der lync Server-Verwaltungsshell und der \*\* Get\*\*-, **Sets**-, **New**-, **Remove-CsAllowedDomain** -und **-CsBlockedDomain-PowerShell-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="825c5-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="825c5-108">Weitere Informationen zum Konfigurieren dieser Einstellungen und zur Verwendung der PowerShell-Cmdlets finden Sie unter " **Verwandte Themen** " am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="825c5-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="825c5-109">In der Tabelle "Zusammenfassung der DNS-Einträge" werden die erforderlichen Einträge für eine offene oder auffindbare Föderation dargestellt.</span><span class="sxs-lookup"><span data-stu-id="825c5-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="825c5-110">Wenn Sie die Verbund Ermittlung nicht implementieren möchten, können Sie sich entscheiden, die \_sipfederationtls nicht zu konfigurieren. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="825c5-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="825c5-111">*SIP-Domänen\> Namen Eintrag. \<*</span><span class="sxs-lookup"><span data-stu-id="825c5-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="825c5-112">Es gibt bestimmte Szenarien, in denen Sie über die _sipfederationtls. _tcp verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="825c5-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="825c5-113"><EM>SIP-Domänenname&gt; &lt;</EM> SRV-Eintrag, aber Sie möchten keinen auffindbaren Verbund haben.</span><span class="sxs-lookup"><span data-stu-id="825c5-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="825c5-114">In einem solchen Fall haben Sie die Mobilität für Ihre Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="825c5-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="825c5-115">Das Mobility Push Notification Clearing House (PNCH) ist ein spezieller Föderations, der für Microsoft lync Mobile-Clients auf Apple iPhone oder iPad mit dem lync 2010-Mobilclient oder Windows Phone mit den mobilen lync 2010 Mobile-oder lync 2013-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="825c5-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="825c5-116">Die _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="825c5-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="825c5-117"><EM>SIP-Domänenname&gt; &lt;</EM> SRV-Eintrag wird im Fall von Mobilität und Push-Benachrichtigung verwendet.</span><span class="sxs-lookup"><span data-stu-id="825c5-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="825c5-118">Um dieses Problem zu vermeiden und ihre Auffindbarkeit zu kontrollieren, deaktivieren Sie die Einstellung <STRONG>enable Partner Domain Discovery</STRONG> , um Discovery zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="825c5-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="825c5-119">Zum Konfigurieren von xmpp (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS-Einträge (Domain Name System) auf einem externen DNS-Server, die die Datensätze in den Access-Edgedienst Ihres Edge-Servers oder Edge-Pools auflösen.</span><span class="sxs-lookup"><span data-stu-id="825c5-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="825c5-120">Wenn Sie DNS (Domain Name System) für die öffentliche Instant Messaging-Konnektivität konfigurieren, werden Sie feststellen, dass die Konfiguration, die externe Benutzer unterstützt, öffentliche Chat Verbindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="825c5-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="825c5-121">Wenn Sie Ihren Edge-Server oder Edge-Pool bereits konfiguriert haben, sollten Sie über die DNS-Einträge verfügen, die für die Unterstützung öffentlicher Chat Verbindungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="825c5-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="825c5-122">DNS-Zusammenfassung – SIP-Föderation einschließlich öffentlicher Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="825c5-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="825c5-123">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="825c5-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="825c5-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="825c5-124">FQDN</span></span></th>
<th><span data-ttu-id="825c5-125">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="825c5-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="825c5-126">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="825c5-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="825c5-127">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="825c5-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="825c5-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="825c5-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="825c5-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="825c5-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="825c5-130">Die externe Schnittstelle für den Zugriff auf den Edgedienst ist für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (genannt Enhanced Federation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="825c5-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="825c5-131">Dieser SRV-Eintrag ist für Mobilität und das Clearing House für die Push-Benachrichtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="825c5-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="825c5-132">In Fällen, in denen mehrere SIP-Domänen vorhanden sind, erstellen und veröffentlichen Sie einen SRV-Eintrag für jede Domäne, die lync Mobile-Clients enthält.</span><span class="sxs-lookup"><span data-stu-id="825c5-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="825c5-133">Der Push-Benachrichtigungsdienst und der Apple Push-Benachrichtigungsdienst funktionieren möglicherweise nicht wie erwartet, wenn kein expliziter SRV-Eintrag für die einzelnen SIP-Domänen vorhanden ist, die die Bereitstellung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="825c5-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="825c5-134">DNS Summary – Extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="825c5-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="825c5-135">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="825c5-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="825c5-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="825c5-136">FQDN</span></span></th>
<th><span data-ttu-id="825c5-137">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="825c5-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="825c5-138">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="825c5-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="825c5-139">Externer DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="825c5-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="825c5-140">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="825c5-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="825c5-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="825c5-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="825c5-142">XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten durch die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf die Lync-fähiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="825c5-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="825c5-143">Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="825c5-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="825c5-144">Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="825c5-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="825c5-145">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="825c5-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="825c5-146">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="825c5-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="825c5-147">IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</span><span class="sxs-lookup"><span data-stu-id="825c5-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="825c5-148">Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet.</span><span class="sxs-lookup"><span data-stu-id="825c5-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="825c5-149">In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="825c5-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="825c5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="825c5-150">See Also</span></span>


[<span data-ttu-id="825c5-151">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="825c5-152">Konfigurieren von Pushbenachrichtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="825c5-153">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="825c5-154">Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="825c5-155">Ermitteln von DNS-Anforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="825c5-156">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825c5-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

