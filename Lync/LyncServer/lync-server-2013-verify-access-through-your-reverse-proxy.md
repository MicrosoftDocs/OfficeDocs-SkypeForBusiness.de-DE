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
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518712"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Überprüfen des Zugriffs über den Reverseproxy in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-29_

Überprüfen Sie mit dem folgenden Verfahren, ob die Benutzer auf Informationen auf dem Reverseproxy zugreifen können. Möglicherweise müssen Sie die Firewall- und die DNS-Konfiguration (Domain Name System) vollständig abschließen, bevor der Zugriff ordnungsgemäß funktioniert.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>So überprüfen Sie den Zugriff über das Internet auf die Website

  - Öffnen Sie einen Webbrowser, und geben Sie in der Adressleiste**** die URLs ein, die von den Clients für den Zugriff auf die Adressbuchdateien und die Website für Konferenzen verwendet werden.
    
      - Geben Sie für Adressbuch Server eine URL ein, die der folgenden ähnelt: **https://externalwebfarmFQDN/abs** wobei externalwebfarmFQDN der externe FQDN der externen Webdienste ist, von denen Adressbuchdienste gehostet werden. Der Benutzer sollte eine HTTP-Anforderung erhalten, da die Verzeichnissicherheit für den Ordner des Adressbuchservers standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie für Konferenzen eine URL ein, die der folgenden ähnelt: **https://externalwebfarmFQDN/meet** wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die Besprechungsinhalte hostet. Unter dieser URL sollte die Problembehandlungsseite für Konferenzen angezeigt werden. Überprüfen Sie alternativ, ob Ihre einfache URL für Konferenzen korrekt funktioniert. Ein Beispiel für eine einfache URL für den Konferenz Beitritt ist möglicherweise https://meet.contoso.com
    
      - Geben Sie für die Erweiterung der Verteilergruppe eine URL ein, die der folgenden ähnelt: **https://externalwebfarmFQDN/GroupExpansion/service.svc** . Der Benutzer sollte eine HTTP-Anforderung erhalten, weil die Verzeichnissicherheit für den Erweiterungsdienst von Verteilergruppen standardmäßig für die Windows-Authentifizierung konfiguriert ist.
    
      - Geben Sie bei Einwahl die einfache URL ähnlich der folgenden ein, **https://externalwebfarmFQDN/dialin** wobei externalwebfarmFQDN der externe FQDN der Webfarm ist, die die Einwahlseite für Einwahlkonferenzen hostet. Der Benutzer sollte auf die Seite zur Einwahl geleitet werden. Überprüfen Sie alternativ, ob Ihre einfache URL für Einwahlkonferenzen korrekt funktioniert. Ein Beispiel für eine einfache URL für die Einwahl ist möglicherweise https://dialin.contoso.com
    
      - Geben Sie ein, um zu bestätigen, dass die Auto Ermittlungs-URL funktionsfähig ist https://lyncdiscover . externaldomainFQDN. Der Browser sollte Sie auffordern, eine Datei zu öffnen. Wählen Sie Editor aus, um ihn zu öffnen. Eine typische Antwort wäre ähnlich wie:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

