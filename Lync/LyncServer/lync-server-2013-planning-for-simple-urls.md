---
title: 'Lync Server 2013: Planung für einfache URLs'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="fb5fd-102">Planung für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5fd-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5fd-103">_**Letztes Änderungsdatum des Themas:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="fb5fd-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="fb5fd-104">Durch einfache URLs können Sie Ihren Benutzern die Teilnahme an Besprechungen erleichtern und die Verwaltung von lync Server-Verwaltungstools für Ihre Administratoren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="fb5fd-105">Lync Server unterstützt drei einfache URLs:</span><span class="sxs-lookup"><span data-stu-id="fb5fd-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="fb5fd-106">**Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="fb5fd-107">Ein Beispiel für eine einfache URL für Besprechungen ist https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="fb5fd-108">Eine URL für eine bestimmte Besprechung kann https://meet.contoso.com/ *username*/7322994 sein.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="fb5fd-109">Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="fb5fd-110">**Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="fb5fd-111">Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung der persönlichen Identifikationsnummer ( PIN) und zugewiesene Konferenz Informationen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="fb5fd-112">Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="fb5fd-113">Ein Beispiel für die einfache Dial-in-URL https://dialin.contoso.comist.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="fb5fd-114">Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="fb5fd-115">Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die lync Server-Systemsteuerung öffnen, indem er die einfache Administrator-URL in einen Browser eingibt.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="fb5fd-116">Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="fb5fd-117">Ein Beispiel für die einfache Administrator-URL isthttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fb5fd-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="fb5fd-118">Einfacher URL-Bereich</span><span class="sxs-lookup"><span data-stu-id="fb5fd-118">Simple URL Scope</span></span>

<span data-ttu-id="fb5fd-119">Sie können Ihre einfachen URLs so konfigurieren, dass Sie einen globalen Bereich aufweisen, oder Sie können für jede zentrale Website in Ihrer Organisation unterschiedliche einfache URLs angeben.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="fb5fd-120">Wenn sowohl eine einfache URL für einen globalen Bereich als auch eine einfache URL für einen Website Bereich angegeben wird, hat die einfache URL des Websitebereichs Vorrang.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="fb5fd-121">In den meisten Fällen empfiehlt es sich, einfache URLs nur auf globaler Ebene festzulegen, damit die einfache URL des Benutzers nicht geändert wird, wenn Sie von einer Website zu einer anderen wechseln.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="fb5fd-122">Ausnahmen sind Organisationen, die unterschiedliche Telefonnummern für Einwahlbenutzer an verschiedenen Standorten verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="fb5fd-123">Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die Einwahl einfache URL) auf einer Website als einfache URL auf Websiteebene festzulegen, müssen Sie auch die anderen einfachen URLs auf dieser Website auf Websiteebene festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb5fd-124">Wenn Sie sich für die Verwendung von einfachen URLs mit Website Bereich entscheiden, können Ihre Benutzer nicht zwischen Front-End-Pools an verschiedenen Standorten wechseln, ohne dass die Benutzer alle geplanten Besprechungen erneut planen, da sich die einfachen URLs der Besprechung zwischen Websites unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="fb5fd-125">Dazu gehören Failover-Szenarien, in denen sich Pools in Sicherungsbeziehungen auf separaten Websites befinden.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="fb5fd-126">Wenn Sie ein Failover zwischen Websites durchführen müssen, bei denen einfache URLs mit Website Bereich bereitgestellt werden, können Benutzer aufgrund des Bereichs für URL nicht an Ihren Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="fb5fd-127">Weitere Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="fb5fd-128">Sie können globale einfache URLs im Topologie-Generator einrichten.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="fb5fd-129">Um eine einfache URL auf Websiteebene einzurichten, müssen Sie das Cmdlet "Satz-CsSimpleURLConfiguration" verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="fb5fd-130">Benennen Ihrer einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="fb5fd-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="fb5fd-131">Es gibt drei Empfohlene Optionen für das Benennen von einfachen URLs.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="fb5fd-132">Welche Option Sie auswählen, hat Auswirkungen auf die Art und Weise, wie Sie Ihre DNS A-Einträge und Zertifikate einrichten, die einfache URLs unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="fb5fd-133">Bei jeder Option müssen Sie eine einfache URL für jede SIP-Domäne in Ihrer Organisation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="fb5fd-134">Sie benötigen immer nur eine einfache URL in ihrer gesamten Organisation für die Einwahl und eine für Administratoren, unabhängig davon, wie viele SIP-Domänen Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="fb5fd-135">Details zu den erforderlichen DNS-A-Einträgen und-Zertifikaten finden Sie unter [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) und [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="fb5fd-136">In Option 1 erstellen Sie für jede einfache URL einen neuen SIP-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="fb5fd-137">Wenn Sie diese Option verwenden, benötigen Sie einen separaten DNS-a-Eintrag für jede einfache URL, und jede einfache URL muss in ihren Zertifikaten benannt sein.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="fb5fd-138">Einfache URL-Benennungs Option 1</span><span class="sxs-lookup"><span data-stu-id="fb5fd-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-139"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="fb5fd-140"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-141">Treffen</span><span class="sxs-lookup"><span data-stu-id="fb5fd-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="fb5fd-142">https://meet.contoso.comhttps://meet.fabrikam.comusw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="fb5fd-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-143">Einwahl</span><span class="sxs-lookup"><span data-stu-id="fb5fd-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-144">Admin</span><span class="sxs-lookup"><span data-stu-id="fb5fd-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fb5fd-145">Bei Option 2 basieren einfache URLs auf dem Domänennamen lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="fb5fd-146">Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="fb5fd-147">Dieser DNS-A-Eintrag verweist auf lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="fb5fd-148">Darüber hinaus benötigen Sie für andere SIP-Domänen in Ihrer Organisation weiterhin getrennte DNS-A-Einträge.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="fb5fd-149">Einfache URL-Benennungs Option 2</span><span class="sxs-lookup"><span data-stu-id="fb5fd-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-150"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="fb5fd-151"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-152">Treffen</span><span class="sxs-lookup"><span data-stu-id="fb5fd-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="fb5fd-153">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meetusw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="fb5fd-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-154">Einwahl</span><span class="sxs-lookup"><span data-stu-id="fb5fd-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-155">Admin</span><span class="sxs-lookup"><span data-stu-id="fb5fd-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fb5fd-156">Option 3 ist am nützlichsten, wenn Sie über viele SIP-Domänen verfügen und diese getrennte einfache URLs erfüllen sollen, aber den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="fb5fd-157">Einfache URL-Benennungs Option 3</span><span class="sxs-lookup"><span data-stu-id="fb5fd-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-158"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="fb5fd-159"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="fb5fd-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-160">Treffen</span><span class="sxs-lookup"><span data-stu-id="fb5fd-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb5fd-161">Einwahl</span><span class="sxs-lookup"><span data-stu-id="fb5fd-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb5fd-162">Admin</span><span class="sxs-lookup"><span data-stu-id="fb5fd-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="fb5fd-163">Einfache URL-Benennungs-und Gültigkeitsprüfungsregeln</span><span class="sxs-lookup"><span data-stu-id="fb5fd-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="fb5fd-164">Der Topologie-Generator und die lync Server-Verwaltungsshell erzwingen mehrere Gültigkeitsprüfungsregeln für ihre einfachen URLs.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="fb5fd-165">Sie müssen einfache URLs für Meet und Dialin festlegen, die Einstellung für "Administrator" ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="fb5fd-166">Jede SIP-Domäne muss über eine separate einfache URL-Adresse verfügen, Sie benötigen jedoch nur eine einfache Wähl-URL und eine einfache Administrator-URL für Ihre gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="fb5fd-167">Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen haben und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie lync.contoso.com/Meet nicht als ihre einfache URL und lync.contoso.com/Meet/Dialin als Ihre Einwahl einfache URL festlegen).</span><span class="sxs-lookup"><span data-stu-id="fb5fd-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="fb5fd-168">Einfache URL-Namen dürfen den FQDN eines Pools oder keine Portinformationen (beispielsweise https://FQDN:88/meet nicht zulässig) enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="fb5fd-169">Alle einfachen URLs müssen mit dem https://-Präfix beginnen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="fb5fd-170">Einfache URLs können nur alphanumerische Zeichen enthalten (also a-z, a-z, 0-9 und der Punkt (.).</span><span class="sxs-lookup"><span data-stu-id="fb5fd-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="fb5fd-171">Wenn Sie andere Zeichen verwenden, funktionieren die einfachen URLs möglicherweise nicht erwartungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="fb5fd-172">Ändern einfacher URLs nach der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="fb5fd-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="fb5fd-173">Wenn Sie nach der anfänglichen Bereitstellung eine einfache URL ändern, müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="fb5fd-174">Wenn sich die Basis einer einfachen URL ändert, müssen Sie auch die DNS-Einträge und Zertifikate ändern.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="fb5fd-175">Wenn Sie beispielsweise https://lync.contoso.com/Meet https://meet.contoso.com die Basis-URL von lync.contoso.com in Meet.contoso.com ändern, müssen Sie die DNS-Einträge und Zertifikate so ändern, dass Sie auf Meet.contoso.com verweisen.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="fb5fd-176">Wenn Sie die einfache URL von https://lync.contoso.com/Meet in https://lync.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="fb5fd-177">Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="fb5fd-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb5fd-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb5fd-178">See Also</span></span>


[<span data-ttu-id="fb5fd-179">DNS-Anforderungen für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5fd-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

