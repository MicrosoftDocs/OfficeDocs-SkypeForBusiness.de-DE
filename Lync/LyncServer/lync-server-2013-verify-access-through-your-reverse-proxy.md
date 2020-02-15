---
title: 'Lync Server 2013: Überprüfen des Zugriffs über den Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="9c657-102">Überprüfen des Zugriffs über den Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c657-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c657-103">_**Letztes Änderungsstand des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="9c657-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="9c657-p101">Überprüfen Sie mit dem folgenden Verfahren, ob die Benutzer auf Informationen auf dem Reverseproxy zugreifen können. Möglicherweise müssen Sie die Firewall- und die DNS-Konfiguration (Domain Name System) vollständig abschließen, bevor der Zugriff ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9c657-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="9c657-106">So überprüfen Sie den Zugriff über das Internet auf die Website</span><span class="sxs-lookup"><span data-stu-id="9c657-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="9c657-107">Öffnen Sie einen Webbrowser, und geben Sie in der Adressleiste\*\*\*\* die URLs ein, die von den Clients für den Zugriff auf die Adressbuchdateien und die Website für Konferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c657-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="9c657-108">Geben Sie für Adressbuch Server eine URL ein, die der folgenden **https://externalwebfarmFQDN/abs** ähnelt: wobei externalwebfarmFQDN der externe FQDN der externen Webdienste ist, von denen Adressbuchdienste gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="9c657-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="9c657-109">Der Benutzer sollte eine HTTP-Anforderung erhalten, da die Verzeichnissicherheit für den Ordner des Adressbuchservers standardmäßig für die Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9c657-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="9c657-110">Geben Sie für Konferenzen eine URL ein, die der folgenden **https://externalwebfarmFQDN/meet** ähnelt: wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die Besprechungsinhalte hostet.</span><span class="sxs-lookup"><span data-stu-id="9c657-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="9c657-111">Unter dieser URL sollte die Problembehandlungsseite für Konferenzen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c657-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="9c657-112">Überprüfen Sie alternativ, ob Ihre einfache URL für Konferenzen korrekt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9c657-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="9c657-113">Ein Beispiel für eine einfache URL für den Konferenz Beitritt ist möglicherweisehttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c657-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="9c657-114">Geben Sie für die Erweiterung der Verteilergruppe eine URL ein, die **https://externalwebfarmFQDN/GroupExpansion/service.svc**der folgenden ähnelt:.</span><span class="sxs-lookup"><span data-stu-id="9c657-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="9c657-115">Der Benutzer sollte eine HTTP-Anforderung erhalten, weil die Verzeichnissicherheit für den Erweiterungsdienst von Verteilergruppen standardmäßig für die Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9c657-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="9c657-116">Geben Sie bei Einwahl die einfache URL ähnlich der folgenden **https://externalwebfarmFQDN/dialin** ein, wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die die Einwahlseite für Einwahlkonferenzen hostet.</span><span class="sxs-lookup"><span data-stu-id="9c657-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="9c657-117">Der Benutzer sollte auf die Seite zur Einwahl geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c657-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="9c657-118">Überprüfen Sie alternativ, ob Ihre einfache URL für Einwahlkonferenzen korrekt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9c657-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="9c657-119">Ein Beispiel für eine einfache URL für die Einwahl ist möglicherweisehttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c657-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="9c657-120">Geben https://lyncdiscoverSie ein, um zu bestätigen, dass die Auto Ermittlungs-URL funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="9c657-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="9c657-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="9c657-121">externaldomainFQDN.</span></span> <span data-ttu-id="9c657-122">Der Browser sollte Sie auffordern, eine Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c657-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="9c657-123">Wählen Sie Editor aus, um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c657-123">Select Notepad to open it.</span></span> <span data-ttu-id="9c657-124">Eine typische Antwort wäre ähnlich wie:</span><span class="sxs-lookup"><span data-stu-id="9c657-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

