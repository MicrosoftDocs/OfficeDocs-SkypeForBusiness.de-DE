---
title: 'Lync Server 2013: Konfigurationsanforderungen für Reverse Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555169f6de67ae23bc63d81aad549b0033a6696c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507742"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Konfigurationsanforderungen für Reverse Proxy in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-05_

Lync Server 2013 auferlegt eine Reihe von Anforderungen für die Kommunikation vom externen Client, die dann an die externen Webdienste übergeben werden, die auf dem Director, Directorpool, Front-End-Server oder Front-End-Pool gehostet werden. Der Reverseproxy ist auch für die Veröffentlichung des Office-webapps-Servers zuständig, wenn Sie den Benutzern Konferenzen anbieten.

<div>


> [!NOTE]  
> In lync Server 2013 wird kein bestimmter Reverseproxy angegeben, den Sie verwenden müssen. In lync Server 2013 werden nur die betrieblichen Anforderungen definiert, die der Reverseproxy in der Lage sein muss. In der Regel können der Reverseproxy, den Sie bereits in Ihrer Infrastruktur bereitgestellt haben, die Anforderungen erfüllen.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Reverseproxyanforderungen

Bei den Funktions Vorgängen, die von einem Reverseproxy erwartet werden, handelt es sich um folgende Aufgaben: lync Server 2013

  - Verwenden Sie SSL (Secure Socket Layer) und TLS (Transport Layer Security) mithilfe von Zertifikaten, die von einer öffentlichen Zertifizierungsstelle erworben wurden, um eine Verbindung mit den veröffentlichten externen Webdiensten des Directors, Directorpool, Front-End-Server oder Front-End-Pool herzustellen. Der Director und der Front-End-Server können sich in einem Lastenausgleichspool mit Hardwarelastenausgleich befinden.

  - Die Möglichkeit, interne Websites mit Zertifikaten für die Verschlüsselung zu veröffentlichen oder Sie bei Bedarf über einen unverschlüsselten Weg zu veröffentlichen.

  - Kann eine intern gehostete Website extern mithilfe eines vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) veröffentlichen.

  - Alle Inhalte der gehosteten Website können veröffentlicht werden. Standardmäßig können Sie die von den **/\*** meisten Webservern erkannte Direktive verwenden, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen. Sie können die Direktive auch ändern, beispielsweise **/UWCA/ \* **, was bedeutet "Veröffentlichen aller Inhalte unter dem virtuellen Verzeichnis Ucwa".

  - Muss konfigurierbar sein, damit Secure Sockets Layer (SSL) und/oder TLS-Verbindungen (Transport Layer Security) mit Clients erforderlich sind, die Inhalte von einer veröffentlichten Website anfordern.

  - Zertifikate mit den Einträgen des alternativen Antragstellernamens müssen akzeptiert werden.

  - Muss in der Lage sein, das Binden eines Zertifikats an einen Listener oder eine Schnittstelle zuzulassen, über die der FQDN der externen Webdienste aufgelöst wird. Listener-Konfigurationen sind Schnittstellen vorzuziehen. Viele Listener können auf einer einzigen Schnittstelle konfiguriert werden.

  - Die Konfiguration der Hostheader Behandlung muss zugelassen werden. Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.

  - Überbrückung von SSL-und TLS-Datenverkehr von einem extern definierten Port (beispielsweise TCP 443) an einen anderen definierten Port (beispielsweise TCP 4443). Der Reverseproxy kann das Paket beim Empfang entschlüsseln und dann das Paket beim Senden erneut verschlüsseln.

  - Überbrückung von unverschlüsseltem TCP-Datenverkehr von einem Port (beispielsweise TCP 80) an einen anderen (beispielsweise TCP 8080).

  - Zulassen der Konfiguration von, oder akzeptieren, NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

