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
ms.openlocfilehash: e13f7e23f3404191f7251c1f49bda6f8935a2929
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e5f45-102">Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f45-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f45-103">_**Letztes Änderungsdatum des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="e5f45-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="e5f45-104">Gehen Sie wie folgt vor, um zu überprüfen, ob Ihre Benutzer auf Informationen auf dem Reverse-Proxy zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e5f45-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="e5f45-105">Möglicherweise müssen Sie die Firewall-Konfiguration und DNS-Konfiguration (Domain Name System) durchführen, bevor Access ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e5f45-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="e5f45-106">So überprüfen Sie, ob Sie über das Internet auf die Website zugreifen können</span><span class="sxs-lookup"><span data-stu-id="e5f45-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="e5f45-107">Öffnen Sie einen Webbrowser, und geben Sie die URLs in der **Adress** Leiste ein, die Clients für den Zugriff auf die Adressbuchdateien und die Website für Konferenzen wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5f45-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="e5f45-108">Geben Sie für den Adressbuch Server eine URL ein, die der **https://externalwebfarmFQDN/abs** folgenden ähnelt: wobei externalwebfarmFQDN der externe FQDN der externen Webdienste ist, der Adressbuchdienste hostet.</span><span class="sxs-lookup"><span data-stu-id="e5f45-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="e5f45-109">Der Benutzer sollte eine HTTP-Abfrage erhalten, da die Verzeichnissicherheit im Ordner "Adressbuch Server" standardmäßig für die Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e5f45-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="e5f45-110">Geben Sie für Konferenzen eine URL ein, die der folgenden **https://externalwebfarmFQDN/meet** ähnelt: wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die Besprechungsinhalte hostet.</span><span class="sxs-lookup"><span data-stu-id="e5f45-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="e5f45-111">Diese URL sollte die Seite zur Problembehandlung für Konferenzen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5f45-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="e5f45-112">Sie können aber auch sicherstellen, dass Ihre einfache URL für Konferenzfunktionen ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e5f45-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="e5f45-113">Eine einfache URL für die Konferenzteilnahme ist möglicherweisehttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5f45-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="e5f45-114">Geben Sie für die Erweiterung der Verteilergruppe eine URL ein, die **https://externalwebfarmFQDN/GroupExpansion/service.svc**der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="e5f45-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="e5f45-115">Der Benutzer sollte eine HTTP-Challenge erhalten, da die Verzeichnissicherheit des Verteilergruppen-Erweiterungs Diensts standardmäßig für die Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e5f45-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="e5f45-116">Geben Sie für Einwahl die einfache URL ein, die der folgenden **https://externalwebfarmFQDN/dialin** ähnelt, wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die die Einwahlseite für Einwahlkonferenzen hostet.</span><span class="sxs-lookup"><span data-stu-id="e5f45-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="e5f45-117">Der Benutzer sollte an die Einwahlseite weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e5f45-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="e5f45-118">Sie können aber auch sicherstellen, dass Ihre einfache URL-Einwahlfunktion ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e5f45-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="e5f45-119">Ein Beispiel für eine einfache URL für die Einwahl ist möglicherweisehttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5f45-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="e5f45-120">Um zu bestätigen, dass die Auto Ermittlungs-URL https://lyncdiscoverfunktioniert, geben Sie.</span><span class="sxs-lookup"><span data-stu-id="e5f45-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="e5f45-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="e5f45-121">externaldomainFQDN.</span></span> <span data-ttu-id="e5f45-122">Der Browser sollte Sie dazu auffordern, eine Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5f45-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="e5f45-123">Wählen Sie Editor aus, um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5f45-123">Select Notepad to open it.</span></span> <span data-ttu-id="e5f45-124">Eine typische Antwort wäre ähnlich wie bei:</span><span class="sxs-lookup"><span data-stu-id="e5f45-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

