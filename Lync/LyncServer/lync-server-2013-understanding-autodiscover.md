---
title: 'Lync Server 2013: Understanding AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 033f3a12ccbe0817f586aa7eb868679fa44541fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="a08b0-102">Grundlegendes zur AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b0-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a08b0-103">_**Letztes Änderungsstand des Themas:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="a08b0-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="a08b0-104">Der lync Server 2013 AutoErmittlungsdienst ist ein Feature, das ursprünglich in Microsoft lync Server 2010 als Teil des kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a08b0-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="a08b0-105">Dieses kumulative Update hat zusätzlich zu Korrekturen Unterstützung für lync Mobile und lync 2013 Clients bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a08b0-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="a08b0-106">In lync Server 2013 ist der AutoErmittlungsdienst ein integraler Bestandteil des Betriebs externer und interner mobiler Clients, und die AutoErmittlung wird auch auf neue Clients ausgedehnt, beispielsweise auf die kürzlich eingeführte lync Windows Store-App für Windows 8.</span><span class="sxs-lookup"><span data-stu-id="a08b0-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="a08b0-107">Die AutoErmittlung wird auch von den lync 2013-Desktop Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="a08b0-108">Die AutoErmittlung wird in lync Server durch die erforderlichen DNS-Einträge (Domain Name System) \*\*lyncdiscover erkannt.\< Domäne\> \*\* und **"lyncdiscoverinternal".\< Domäne\>**.</span><span class="sxs-lookup"><span data-stu-id="a08b0-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="a08b0-109">Darüber hinaus bevorzugen neuere Versionen der lync 2010 und lync 2013 Desktop Clients die AutoErmittlung über die DNS-SRV-Einträge (Domain Name System), wobei DNS-SRV-Einträge nur bei lyncdiscover verwendet werden. \<Domäne\> oder "lyncdiscoverinternal". \<die\> Domäne reagiert nicht oder wird nicht aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="a08b0-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="a08b0-110">Die lync Windows Store-App für Windows 8 und lync Mobile verwendet die AutoErmittlung ausschließlich und bezieht sich nicht auf die herkömmlichen DNS-SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="a08b0-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="a08b0-111">In lync Server 2013 wird die AutoErmittlung erweitert, um dem Client mitzuteilen, welche Elemente, Features und Kommunikationsmethoden dem Client zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a08b0-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="a08b0-112">Die Informationen werden über eine vom Client gesendete Anforderung kommuniziert, und die lync Server-Webdienste antwortet mit einer klar definierten Antwort, die den Namen für den Client bereitstellt, und wie diese Features im Format der AutoErmittlung kontaktiert werden. Antwortdokument.</span><span class="sxs-lookup"><span data-stu-id="a08b0-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="a08b0-113">Die beste Möglichkeit zum Verständnis des Antwortdokuments für die AutoErmittlung, einschließlich der Kommunikation der Webdienste mit Clients über dieses Dokument, besteht darin, die einzelnen Leitungen in einer typischen Antwort aus dem lync-Webdienst-Antwortdokument für die automatische Erkennung zu analysieren und zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a08b0-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="a08b0-114">In den folgenden Details hat sich der Benutzer bereits beim Stammserver authentifiziert, indem er auf eine Authentifizierungsanforderung antwortet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="a08b0-115">Der lync autodiscover-Webdienst ist in den <STRONG>Microsoft Office-Protokollen</STRONG> im Abschnitt <STRONG>Open Specifications</STRONG> der MSDN-Bibliothek ( <STRONG>Microsoft Developer Network</STRONG> ) definiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="a08b0-116">Ausführliche Informationen finden Sie im vollständigen Spezifikationsdokument "lync autodiscover-Webdienstprotokoll" unter <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>:.</span><span class="sxs-lookup"><span data-stu-id="a08b0-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="a08b0-117">Ausführliche Informationen zur Authentifizierung finden Sie unter "OC Authentication-Webdienstprotokoll" <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>unter.</span><span class="sxs-lookup"><span data-stu-id="a08b0-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="a08b0-118">Die Antwort des lync Server-Webdienst-AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a08b0-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="a08b0-119">Die beim Senden der Auto Ermittlungsanforderung zurückgegebene Antwort ist für einen internen oder externen Client identisch.</span><span class="sxs-lookup"><span data-stu-id="a08b0-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="a08b0-120">Einige Parameter, die Standort fähig sind, können sich ändern.</span><span class="sxs-lookup"><span data-stu-id="a08b0-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="a08b0-121">Wenn eine Clientanforderung empfangen wird, der tatsächliche Pool jedoch nicht mit dem Kontakt aufgenommen wurde, wird der Home-Pool des Benutzers für diesen Benutzer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a08b0-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="a08b0-122">Ein Kollege, dessen Benutzerkonto sich in einem anderen Pool befindet, sich aber vom gleichen Büro aus einloggt, würde eine etwas andere Antwort erhalten.</span><span class="sxs-lookup"><span data-stu-id="a08b0-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="a08b0-123">Die Antwort gibt die richtige Front-End-Server oder Front-End-Pool für diesen Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="a08b0-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="a08b0-124">Ein Beispiel für ein Auto Ermittlungs Antwortdokument:</span><span class="sxs-lookup"><span data-stu-id="a08b0-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="a08b0-125">Details zum Auto Ermittlungs Antwort-Dokument</span><span class="sxs-lookup"><span data-stu-id="a08b0-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="a08b0-126">Das Antwortdokument der AutoErmittlung kann in einem von zwei Formaten vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a08b0-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="a08b0-127">Das Standardformat ist ein JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="a08b0-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="a08b0-128">Das andere Format ist XML-Dokument (Extensible Markup Language).</span><span class="sxs-lookup"><span data-stu-id="a08b0-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="a08b0-129">In diesem Beispiel wird der XML-Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-129">The XML is used for this example.</span></span> <span data-ttu-id="a08b0-130">Die Anforderung und die Antwort sind vorhersehbar, da das Dokument über ein definiertes Schema verfügt, das das Format bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a08b0-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="a08b0-131">Die im Dokument beschriebene Textfolge, die das verwendete Schema beschreibt, ist die erste in der Anforderung oder Antwort:</span><span class="sxs-lookup"><span data-stu-id="a08b0-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="a08b0-132">Die Definition von **Zugriffsort = "extern"** gibt an, dass die Anforderung von einem externen Benutzer gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a08b0-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="a08b0-133">SipServerInternalAccess und SipServerExternalAccess werden derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="a08b0-134">Diese Einträge sind für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="a08b0-135">SipClientInternalAccess und SipClientExternalAccess beschreiben den vollqualifizierten Domänennamen und den Port, der von einem internen oder externen Client für den Zugriff auf den definierten SIP-Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a08b0-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="a08b0-136">Der lync-Desktop Client und die lync Windows Store-App verwenden diese Einträge basierend auf Ihrem Standort (intern oder extern), um den Director oder Front-End-Server zu finden.</span><span class="sxs-lookup"><span data-stu-id="a08b0-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="a08b0-137">Die `Autodiscover` Verweise enthalten die Dienst Einstiegspunkte für den AutoErmittlungsdienst.</span><span class="sxs-lookup"><span data-stu-id="a08b0-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="a08b0-138">Das Token-Attribut enthält den Namen des Diensts, und der href ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a08b0-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="a08b0-139">Clients in einem externen Netzwerk verwenden die `External/Autodiscover`.</span><span class="sxs-lookup"><span data-stu-id="a08b0-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="a08b0-140">Der AutoErmittlungsdienst wird als Teil des Bereitstellungsprozesses installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="a08b0-141">`Internal/Autodiscover`wird derzeit nicht verwendet und ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="a08b0-142">Die `AuthBroker` Verweise enthalten die Dienst Einstiegspunkte für den internen und den externen Authentifizierungsbroker-Dienst, in diesem Fall "SIP. svc".</span><span class="sxs-lookup"><span data-stu-id="a08b0-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="a08b0-143">Das Token-Attribut enthält den Namen des Diensts, und der href ist eine URL, die für den Client definiert, in dem der Dienst gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a08b0-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="a08b0-144">Clients im internen Netzwerk werden mit verwendet `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="a08b0-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="a08b0-145">Clients in einem externen Netzwerk verwenden die `External/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="a08b0-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="a08b0-146">Der AuthBroker-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="a08b0-147">Das `WebScheduler` Token verweist auf die URLs für den Clientzugriff auf die webbasierte Planung für lync Server Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="a08b0-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="a08b0-148">Derzeit wird nur der `External/WebScheduler` verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="a08b0-149">Der WebScheduler wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="a08b0-150">`Internal/Mcx`und `External/Mcx` sind die Speicherorte der Mobilitätsdienste, die im kumulativen Update für lync Server 2010 eingeführt wurden: November 2011.</span><span class="sxs-lookup"><span data-stu-id="a08b0-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="a08b0-151">Diese Verweise werden weiterhin von lync 2010 Mobile auf allen unterstützten Geräten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="a08b0-152">Der MCX-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="a08b0-153">**Interne/Ucwa**, **External/Ucwa** und **Ucwa** bieten Clients einen Mittel für den Zugriff auf die Unified Communications-Webanwendungs-Programmierschnittstelle (Ucwa-API oder einfach Ucwa).</span><span class="sxs-lookup"><span data-stu-id="a08b0-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="a08b0-154">`Internal/Ucwa`und `External/Ucwa` virtuelle Verzeichnisse sind Zugriffspunkte, die für die zukünftige Funktionserweiterung reserviert sind und nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a08b0-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="a08b0-155">Das `Ucwa` virtuelle Verzeichnis wird für Microsoft lync Mobile (mit lync Server 2013 eingeführt) auf allen unterstützten Geräten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a08b0-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="a08b0-156">Der UCWA-Dienst wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="a08b0-157">`Internal/XFrame`, **External/Xframe** und **Xframe** bieten Zugriff für UCWA-basierte Serveranwendungen.</span><span class="sxs-lookup"><span data-stu-id="a08b0-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="a08b0-158">Xframe wird als Teil des Bereitstellungsprozesses ihrer internen lync Server 2013-Bereitstellungs-Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="a08b0-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="a08b0-159">Das `Self` Token bezieht sich auf spezifische Informationen für den Client (Benutzer Antworttyp), der die Anforderung macht.</span><span class="sxs-lookup"><span data-stu-id="a08b0-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="a08b0-160">Der Client, der diese Anforderung gestellt hat, war extern, und dieser Verweis auf die AutoErmittlung bezieht sich auf den Benutzer Teil des AutoErmittlungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="a08b0-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a08b0-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a08b0-161">See Also</span></span>


[<span data-ttu-id="a08b0-162">System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b0-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="a08b0-163">Planen der AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08b0-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

