---
title: 'Lync Server 2013: Planen für einfache URLs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="50e4b-102">Planen von einfachen URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e4b-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e4b-103">_**Letztes Änderungsstand des Themas:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="50e4b-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="50e4b-104">Einfache URLs erleichtern die Teilnahme an Besprechungen für Ihre Benutzer und erleichtern Ihnen die Verwaltung von lync Server Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="50e4b-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="50e4b-105">Lync Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="50e4b-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="50e4b-106">**Meet**: Dient als Basis-URL für alle Konferenzen, die am Standort oder in der Organisation abgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="50e4b-107">Ein Beispiel für eine einfache Meet-URL https://meet.contoso.comist.</span><span class="sxs-lookup"><span data-stu-id="50e4b-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="50e4b-108">Eine URL für eine bestimmte Besprechung ist https://meet.contoso.com/möglicherweise *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="50e4b-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="50e4b-109">Mit der einfachen Meet-URL sind Links für den Besprechungsbeitritt einfach zu verstehen, leicht zu kommunizieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="50e4b-110">**Dial-in**: Ermöglicht den Zugriff auf die Webseite mit den Einstellungen für eine Einwahlkonferenz.</span><span class="sxs-lookup"><span data-stu-id="50e4b-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="50e4b-111">Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (also für Besprechungen, die nicht geplant werden müssen) und DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung der persönlichen Identifikationsnummer ( PIN) und zugewiesene Konferenz Informationen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="50e4b-112">Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben.</span><span class="sxs-lookup"><span data-stu-id="50e4b-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="50e4b-113">Ein Beispiel für die einfache Einwahl-URL ist https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="50e4b-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="50e4b-114">Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="50e4b-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="50e4b-115">Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die lync Server-Systemsteuerung öffnen, indem er die einfache admin-URL in einen Browser eingibt.</span><span class="sxs-lookup"><span data-stu-id="50e4b-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="50e4b-116">Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="50e4b-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="50e4b-117">Ein Beispiel für die einfache admin-URL isthttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="50e4b-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="50e4b-118">Bereich einer einfachen URL</span><span class="sxs-lookup"><span data-stu-id="50e4b-118">Simple URL Scope</span></span>

<span data-ttu-id="50e4b-119">Sie können Ihre einfachen URLs auf globaler Ebene konfigurieren oder unterschiedliche einfache URLs für jeden zentralen Standort in Ihrer Organisation angeben.</span><span class="sxs-lookup"><span data-stu-id="50e4b-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="50e4b-120">Wenn sowohl eine einfache URL des globalen Bereichs als auch eine einfache URL für den Website Bereich angegeben wird, hat die einfache URL des Websitebereichs Vorrang.</span><span class="sxs-lookup"><span data-stu-id="50e4b-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="50e4b-p105">In den meisten Fällen wird empfohlen, einfache URLs nur auf globaler Ebene festzulegen, sodass sich die einfache URL für Besprechungen nicht ändert, wenn ein Benutzer von einem Standort an einen anderen wechselt. Eine Ausnahme stellen Organisationen dar, die unterschiedliche Telefonnummern für Einwahlbenutzer an unterschiedlichen Standorten verwenden. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die einfache URL für die Einwahl) als einfache URL auf Standortebene festlegen, müssen Sie auch die weiteren einfachen URLs für diesen Standort auf Standortebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e4b-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50e4b-124">Wenn Sie einfache URLs mit Website Bereich verwenden, können Ihre Benutzer nicht zwischen Front-End-Pools an unterschiedlichen Standorten navigieren, ohne dass Benutzer alle geplanten Besprechungen Umplanen, da sich die einfachen URLs der Besprechung zwischen den Websites unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="50e4b-125">Dies umfasst Failover-Szenarien, in denen sich Pools in Sicherungsbeziehungen an unterschiedlichen Standorten befinden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="50e4b-126">Wenn Sie ein Failover zwischen Websites durchführen müssen, bei denen einfache URLs auf Websiteebene bereitgestellt werden, können Benutzer aufgrund des Bereichs für die URL nicht an Ihren Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="50e4b-127">Weitere Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="50e4b-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="50e4b-128">Sie können globale einfache URLs im Topologie-Generator festlegen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="50e4b-129">Zum Festlegen einer einfachen URL auf Standortebene müssen Sie das Cmdlet "Set-CsSimpleURLConfiguration" verwenden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="50e4b-130">Benennen von einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="50e4b-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="50e4b-p108">Es gibt drei empfohlene Optionen für die Benennung einfacher URLs. Die Auswahl der Benennungsoption hat Auswirkungen darauf, wie Sie Ihre DNS-A-Einträge und Zertifikate zur Unterstützung einfacher URLs einrichten. Bei jeder Option müssen Sie eine einfache URL für Besprechungen (Meet) für jede SIP-Domäne in Ihrer Organisation konfigurieren. Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="50e4b-134">Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="50e4b-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="50e4b-135">Ausführliche Informationen zu den erforderlichen DNS-A-Einträgen und-Zertifikaten finden Sie unter [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) und [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="50e4b-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="50e4b-136">Bei Option 1 erstellen Sie einen neue SIP-Domänennamen für jede einfache URL.</span><span class="sxs-lookup"><span data-stu-id="50e4b-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="50e4b-137">Wenn Sie sich für diese Option entscheiden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL muss in Ihren Zertifikaten benannt sein.</span><span class="sxs-lookup"><span data-stu-id="50e4b-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="50e4b-138">Benennung einfacher URLs – Option 1</span><span class="sxs-lookup"><span data-stu-id="50e4b-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-139"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50e4b-140"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-141">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="50e4b-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="50e4b-142">https://meet.contoso.com, https://meet.fabrikam.comusw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="50e4b-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-143">Einwahl</span><span class="sxs-lookup"><span data-stu-id="50e4b-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-144">Admin</span><span class="sxs-lookup"><span data-stu-id="50e4b-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="50e4b-p109">Bei Option 2 basieren die einfachen URLs auf dem Domänennamen "lync.contoso.com". Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs unterstützt. Dieser DNS-A-Eintrag referenziert "lync.contoso.com". Zusätzlich benötigen Sie weiterhin separate DNS-A-Einträge für weitere SIP-Domänen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="50e4b-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="50e4b-149">Benennung einfacher URLs – Option 2</span><span class="sxs-lookup"><span data-stu-id="50e4b-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-150"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50e4b-151"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-152">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="50e4b-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="50e4b-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetusw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="50e4b-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-154">Einwahl</span><span class="sxs-lookup"><span data-stu-id="50e4b-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-155">Admin</span><span class="sxs-lookup"><span data-stu-id="50e4b-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="50e4b-156">Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs für Besprechungen (Meet) zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="50e4b-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="50e4b-157">Benennung einfacher URLs – Option 3</span><span class="sxs-lookup"><span data-stu-id="50e4b-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-158"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="50e4b-159"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="50e4b-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-160">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="50e4b-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50e4b-161">Einwahl</span><span class="sxs-lookup"><span data-stu-id="50e4b-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50e4b-162">Admin</span><span class="sxs-lookup"><span data-stu-id="50e4b-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="50e4b-163">Benennung einfacher URLs und Überprüfungsregeln</span><span class="sxs-lookup"><span data-stu-id="50e4b-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="50e4b-164">Der Topologie-Generator und die lync Server-Verwaltungsshell-Cmdlets erzwingen mehrere Validierungsregeln für ihre einfachen URLs.</span><span class="sxs-lookup"><span data-stu-id="50e4b-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="50e4b-165">Sie müssen einfache URLs für Besprechungen und Einwahl angeben, die Festlegung einer einfachen Admin-URL ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="50e4b-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="50e4b-166">Jede SIP-Domäne muss über eine separate einfache URL für Besprechungen (Meet) verfügen, Sie benötigen jedoch nur eine einfache URL für die Einwahl (Dialin) und eine einfache Admin-URL für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="50e4b-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="50e4b-167">Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen aufweisen und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie nicht "lync.contoso.com/Meet" als einfache Meet-URL und "lync/contoso.com/Meet/Dialin" als einfache URL für die Einwahl verwenden).</span><span class="sxs-lookup"><span data-stu-id="50e4b-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="50e4b-168">Einfache URL-Namen dürfen nicht den FQDN eines Pools oder Portinformationen enthalten (beispielsweise https://FQDN:88/meet nicht zulässig).</span><span class="sxs-lookup"><span data-stu-id="50e4b-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="50e4b-169">Alle einfachen URLs müssen mit dem Präfix "https://" beginnen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="50e4b-p112">Einfache URLs können ausschließlich alphanumerische Zeichen enthalten – a-z, A-Z, 0-9 und Punkt (.). Wenn Sie andere Zeichen verwenden, funktioniert die einfache URL möglicherweise nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="50e4b-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="50e4b-172">Ändern von einfachen URLs nach der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="50e4b-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="50e4b-173">Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge und Zertifikate für einfache URLs bewusst sein.</span><span class="sxs-lookup"><span data-stu-id="50e4b-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="50e4b-174">Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern.</span><span class="sxs-lookup"><span data-stu-id="50e4b-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="50e4b-175">Wenn beispielsweise von https://lync.contoso.com/Meet in https://meet.contoso.com geändert wird, wird die Basis-URL von lync.contoso.com in Meet.contoso.com geändert, sodass Sie die DNS-Einträge und Zertifikate für den Verweis auf Meet.contoso.com ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="50e4b-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="50e4b-176">Wenn Sie die einfache URL von https://lync.contoso.com/Meet in https://lync.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="50e4b-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="50e4b-177">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="50e4b-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50e4b-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50e4b-178">See Also</span></span>


[<span data-ttu-id="50e4b-179">DNS-Anforderungen für einfache URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e4b-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

