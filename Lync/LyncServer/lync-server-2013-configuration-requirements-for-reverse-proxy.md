---
title: 'Lync Server 2013: Konfigurationsanforderungen für Reverse-Proxy'
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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Konfigurationsanforderungen für den Reverse Proxy in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-05_

Lync Server 2013 erlegt den externen Clients einige Anforderungen auf, die an die externen Webdienste weitergegeben werden, die auf dem Director, Director-Pool, Front-End-Server oder Front-End-Pool gehostet werden. Der Reverse-Proxy ist auch für die Veröffentlichung des Office Web Apps-Servers verantwortlich, wenn Sie Ihren Benutzern Konferenzen anbieten.

<div>


> [!NOTE]  
> Lync Server 2013 gibt keinen bestimmten Reverse-Proxy an, den Sie verwenden müssen. Lync Server 2013 definiert nur betriebliche Anforderungen, die der Reverse-Proxy erfüllen muss. In der Regel kann der umgekehrte Proxy, den Sie bereits in Ihrer Infrastruktur bereitgestellt haben, die Anforderungen erfüllen.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Reverse Proxy-Anforderungen

Die funktionsvorgänge, die lync Server 2013 von einem Reverse-Proxy erwartet, sind:

  - Verwenden Sie Secure Socket Layer (SSL) und TLS (Transport Layer Security) mithilfe von Zertifikaten, die von einer öffentlichen Zertifizierungsstelle zum Herstellen einer Verbindung mit den veröffentlichten externen Webdiensten des Director-, Director-Pools, Front-End-Servers oder Front-End-Pools erworben wurden. Der Director und der Front-End-Server können in einem Lastenausgleichspool mithilfe von Hardwarelastenausgleichs verwendet werden.

  - In der Lage, interne Websites mithilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder Sie bei Bedarf über ein unverschlüsseltes Mittel zu veröffentlichen.

  - Sie können eine intern gehostete Website extern mit einem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) veröffentlichen.

  - Kann alle Inhalte der gehosteten Website veröffentlichen. Standardmäßig können Sie die ** / ** von den meisten Webservern erkannte Direktive verwenden, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen. Sie können die Direktive auch ändern, beispielsweise **/UWCA/\***, was bedeutet, dass "alle Inhalte unter dem virtuellen Verzeichnis Ucwa veröffentlicht werden".

  - Muss konfigurierbar sein, damit SSL (Secure Sockets Layer) und/oder TLS-Verbindungen (Transport Layer Security) mit Clients erforderlich sind, die Inhalte von einer veröffentlichten Website anfordern.

  - Sie müssen Zertifikate mit San-Einträgen (Subject Alternative Name) akzeptieren.

  - Muss in der Lage sein, die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zu ermöglichen, über die der FQDN des externen Webdiensts aufgelöst wird. Listenerkonfigurationen sind Schnittstellen vorzuziehen. Viele Listener können in einer einzelnen Schnittstelle konfiguriert werden.

  - Muss für die Konfiguration der Hostheader Behandlung zugelassen werden. Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverse-Proxy geändert zu werden.

  - Bridging des SSL-und TLS-Datenverkehrs von einem extern definierten Port (beispielsweise TCP 443) zu einem anderen definierten Port (beispielsweise TCP 4443). Der Reverse-Proxy entschlüsselt das Paket möglicherweise beim Empfang und verschlüsselt das Paket beim Senden erneut.

  - Bridging des unverschlüsselten TCP-Datenverkehrs von einem Port (beispielsweise TCP 80) zu einem anderen (beispielsweise TCP 8080).

  - Erlauben Sie die Konfiguration von oder akzeptieren Sie die NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

