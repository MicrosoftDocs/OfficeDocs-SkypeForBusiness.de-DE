---
title: 'Lync Server 2013: Einrichten von Reverse-Proxyservern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521812"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Einrichten von Reverse-Proxyservern für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-08_

Für Microsoft lync Server 2013 Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk erforderlich, damit externe Clients auf den lync Server 2013-Webdienste (als *Webkomponenten* in Office Communications Server) auf dem Director und dem Home-Pool des Benutzers zugreifen können. Beispielsweise ist für die folgenden Funktionen ein externer Zugriff über einen Reverseproxy erforderlich:

  - Herunterladen von Besprechungsinhalten durch externe Benutzer

  - Erweitern von Verteilergruppen durch externe Benutzer

  - Herunterladen von Dateien aus dem Adressbuchdienst durch Remotebenutzer

  - Zugriff auf den lync Web App-Client.

  - Zugriff auf die Webseite mit Einstellungen für Einwahlkonferenzen

  - Herstellen einer Verbindung mit dem Geräteaktualisierungswebdienst und Abrufen von Updates durch externe Geräte

  - Aktivieren von mobilen Anwendungen zum automatischen ermitteln und Verwenden von Mobility-URLs (MCX) aus dem Internet.

  - Aktivieren des lync 2013-Clients, der lync Windows Store-App und lync 2013 mobilen Clients zum Auffinden der lync Discover (autodiscover)-URLs und Verwenden von Unified Communications Web API (UCWA).

Es wird empfohlen, den HTTP-Reverseproxy zum Veröffentlichen aller Webdienste in sämtlichen Pools zu konfigurieren. Veröffentlichen https://ExternalFQDN/ \* veröffentlicht alle virtuellen IIS-Verzeichnisse für einen Pool. Sie benötigen eine Veröffentlichungsregel für jeden Standard Edition-Server, Front-End-Pool oder Director oder Director-Pool in Ihrer Organisation.

Darüber hinaus müssen Sie die einfachen URLs veröffentlichen. Wenn die Organisation über einen Director oder einen Director-Pool verfügt, fängt der HTTP-Reverseproxy HTTP/HTTPS-Anforderungen an die einfachen URLs ab und leitet sie an das virtuelle Verzeichnis der externen Webdienste auf dem Director oder dem Director-Pool weiter. Wenn Sie keinen Director bereitgestellt haben, müssen Sie einen Pool zur Verarbeitung von Anforderungen für einfache URLs festlegen. (Wenn es sich hierbei nicht um den Homepool des Benutzers handelt, wird eine Weiterleitung an die Webdienste im Homepool des Benutzers durchgeführt.) Die einfachen URLs können durch eine dedizierte Webveröffentlichungsregel verarbeitet werden, oder Sie können sie zu den öffentlichen Namen der Webveröffentlichungsregel für den Director hinzufügen. Sie müssen auch die externe AutoErmittlungsdienst-URL veröffentlichen.

Sie können Microsoft Forefront Threat Management Gateway 2010, ISA (Microsoft Internet Security and Acceleration Server) 2006 SP1 oder Internet Information Server 7,0, 7,5 oder 8,0 mit dem Application Request Routing (IIS arr) als Reverse-Proxy verwenden. In den detaillierten Schritten in diesem Abschnitt wird beschrieben, wie Sie Forefront Threat Management Gateway 2010 konfigurieren, und die Schritte zum Konfigurieren von ISA Server 2006 sind nahezu identisch. Außerdem werden Anleitungen für IIS arr bereitgestellt. Wenn Sie einen anderen Reverseproxy verwenden, lesen Sie in der Dokumentation zu diesem Produkt nach, und ordnen Sie die hier definierten Anforderungen den zugehörigen Features in anderen Reverse-Proxys zu.

<div>


> [!IMPORTANT]  
> IIS ARR (Internet Information Server Application Request Routing) ist eine vollständig getestete und unterstützte Option für die Implementierung eines Reverse-Proxys für lync Server 2010 und lync Server 2013. Im November 2012 haben Microsoft den Lizenzverkauf von Forefront Threat Management Gateway 2010 oder TMG eingestellt. TMG ist weiterhin ein vollständig unterstütztes Produkt und steht weiterhin für Geräte zur Verfügung, die von Drittanbietern vertrieben werden. Außerdem bieten viele Hardware-Lastenausgleichsgeräte von Drittanbietern und Firewalls Unterstützung für Reverse-Proxys. Für Hardwarelastenausgleichs und Firewalls, die Reverse-Proxyfunktionen bereitstellen, erkundigen Sie sich bei Ihrem Anbieter nach spezifischen Anweisungen zum Konfigurieren des Produkts für die Bereitstellung von Reverse-Proxy Unterstützung für lync Server. Sie können auch Drittanbieteranzeigen, die die Dokumentation für Ihr Produkt an Microsoft übermittelt haben. Die Unterstützung wird vom Drittanbieter für die Lösung bereitgestellt. Informationen zu Drittanbietern, die bei der Bereitstellung von Lösungen aktiv sind, finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=268730">für Microsoft lync qualifizierte Infrastruktur</A>.



</div>

In den folgenden Themen und Verfahren werden Forefront Threat Management Gateway 2010 und IIS arr als Grundlage für die Bereitstellungs-und Konfigurationsverfahren verwendet.

  - [Konfigurieren von Webfarm-FQDNs für lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Konfigurieren von Netzwerkadaptern in lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Überprüfen des Zugriffs über den Reverseproxy in lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Vorbereitung

Für die erfolgreiche Bereitstellung von Forefront Threat Management Gateway 2010 als Reverseproxy müssen Sie einen Server einrichten und konfigurieren, indem Sie die Voraussetzungen und Hardwareanforderungen beachten, die in der Forefront Threat Management Gateway 2010-Dokumentation angegeben sind. Lesen Sie das folgende Thema, das für eine ordnungsgemäße Konfiguration der Hardware und für die Installation von Forefront Threat Management Gateway 2010 auf dem Server festgelegt ist, bevor Sie fortfahren.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Hardwareempfehlungen für Forefront TMG 2010](https://go.microsoft.com/fwlink/?linkid=291293)

Wenn Sie IIS arr erfolgreich als Reverse-Proxy bereitstellen möchten, lesen Sie die folgenden Themen, um die Hardware und die erforderliche Software zu konfigurieren.

  - <span></span>  
    Informationen zum Installieren von IIS auf Windows Server 2008 oder Windows Server 2008 R2 finden Sie unter [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Informationen zum Installieren von IIS auf Windows Server 2012 finden Sie unter [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Informationen zum Installieren von IIS auf Windows Server 2012 R2 finden Sie unter [Installing IIS 8,5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Wenn Sie die Routingerweiterung für Anwendungsanforderungen für IIS herunterladen möchten, befolgen Sie die Anweisungen unter [Application Request Routing v 2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    So installieren Sie arr für die Anweisungen unter [install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Die derzeit veröffentlichten Anweisungen gelten für arr 2,0. Für die Installation der Erweiterung gibt es keinen Unterschied zwischen den beiden Versionen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

