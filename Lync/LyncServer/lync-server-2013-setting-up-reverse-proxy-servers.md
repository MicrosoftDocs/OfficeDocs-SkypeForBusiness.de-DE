---
title: 'Lync Server 2013: Einrichten von Reverseproxyservern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Einrichten von Reverseproxyservern für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-08_

Für Microsoft lync Server 2013-Edgeserver-Bereitstellungen ist ein HTTPS-Reverseproxy im Umkreisnetzwerk für externe Clients erforderlich, um auf die lync Server 2013-Webdienste (so genannte *Webkomponenten* in Office Communications Server) auf dem Director zuzugreifen. und den privaten Pool des Benutzers. Zu den Features, die einen externen Zugriff über einen Reverseproxy erfordern, gehören die folgenden:

  - Aktivieren von externen Benutzern zum Herunterladen von Besprechungsinhalten für Ihre Besprechungen

  - Aktivieren von externen Benutzern zum Erweitern von Verteilergruppen

  - Aktivieren von Remotebenutzern zum Herunterladen von Dateien aus dem Adressbuchdienst

  - Zugriff auf den lync Web App-Client

  - Zugreifen auf die Webseite "Einstellungen für Einwahlkonferenzen"

  - Aktivieren externer Geräte zum Herstellen einer Verbindung mit dem Geräte Update-Webdienst und Abrufen von Updates

  - Aktivieren von mobilen Anwendungen zum automatischen Auffinden und Verwenden der Mobilitäts-URLs (MCX) aus dem Internet.

  - Aktivieren des lync 2013-Clients, der lync Windows Store-App und des lync 2013 Mobile-Clients zum Auffinden der URLs von lync Discover (autodiscover) und Verwenden der Unified Communications Web-API (UCWA).

Wir empfehlen, den HTTP-Reverseproxy so zu konfigurieren, dass alle Webdienste in allen Pools veröffentlicht werden. Publishing https://ExternalFQDN/\* veröffentlicht alle virtuellen IIS-Verzeichnisse für einen Pool. Sie benötigen eine Veröffentlichungsregel für jeden Standard Edition-Server, Front-End-Pool oder Director-oder Director-Pool in Ihrer Organisation.

Darüber hinaus müssen Sie die einfachen URLs veröffentlichen. Wenn die Organisation über einen Director-oder Director-Pool verfügt, lauscht der HTTP-Reverseproxy auf HTTP/HTTPS-Anforderungen an die einfachen URLs und stellt Sie dem virtuellen Verzeichnis der externen Webdienste im Director-oder Director-Pool zur Ver, Proxys. Wenn Sie keinen Director bereitgestellt haben, müssen Sie einen Pool angeben, um Anforderungen an einfache URLs zu verarbeiten. (Wenn es sich nicht um den Home-Pool des Benutzers handelt, wird er an die Webdienste im Home-Pool des Benutzers weitergeleitet). Die einfachen URLs können von einer dedizierten Webveröffentlichungsregel verarbeitet werden, oder Sie können Sie den öffentlichen Namen der Webveröffentlichungsregel für den Director hinzufügen. Außerdem müssen Sie die URL des externen AutoErmittlungsdiensts veröffentlichen.

Sie können Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 oder Internet Information Server 7,0, 7,5 oder 8,0 mit Application Request Routing (IIS arr) als Reverse-Proxy verwenden. In den detaillierten Schritten in diesem Abschnitt wird beschrieben, wie Sie das Forefront Threat Management Gateway 2010 konfigurieren, und die Schritte zum Konfigurieren von ISA Server 2006 sind nahezu identisch. Es werden auch Anleitungen für IIS arr bereitgestellt. Wenn Sie einen anderen Reverseproxy verwenden, konsultieren Sie die Dokumentation für dieses Produkt, und ordnen Sie die hier definierten Anforderungen den zugehörigen Features in anderen Reverse-Proxys zu.

<div>


> [!IMPORTANT]  
> Internet Information Server Application Request Routing (IIS arr) ist eine vollständig getestete und unterstützte Option für die Implementierung eines Reverse-Proxys für lync Server 2010 und lync Server 2013. Im November 2012 hat Microsoft den Lizenzverkauf von Forefront Threat Management Gateway 2010 oder TMG eingestellt. TMG ist nach wie vor ein vollständig unterstütztes Produkt und steht weiterhin für Verkauf von Geräten zur Verfügung, die von Drittanbietern verkauft werden. Darüber hinaus bieten viele Hardware-Load-Balancer und Firewalls von Drittanbietern Reverse-Proxy-Unterstützung. Bei Hardwarelastenausgleichs und Firewalls, die Reverse-Proxyfunktionen bereitstellen, erkundigen Sie sich bei Ihrem Anbieter nach spezifischen Anweisungen zum Konfigurieren des Produkts, um die Unterstützung für den Reverse-Proxy für lync Server bereitzustellen. Sie können auch Drittanbieteranzeigen, die die Dokumentation für Ihr Produkt an Microsoft übermittelt haben. Der Support wird von der Drittpartei für Ihre Lösung bereitgestellt. Informationen zu Drittanbietern, die bei der Bereitstellung von Lösungen aktiv sind, finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=268730">für Microsoft lync qualifizierte Infrastruktur</A>.



</div>

Die folgenden Themen und Verfahren verwenden Forefront Threat Management Gateway 2010 und IIS arr als Grundlage für die Bereitstellungs-und Konfigurationsverfahren.

  - [Konfigurieren von Webfarm-FQDNs für Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Konfigurieren von Netzwerkadaptern in Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Überprüfen oder Konfigurieren der Authentifizierung und Zertifizierung für virtuelle IIS-Verzeichnisse in Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Überprüfen des Zugriffs über den Reverseproxy in Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Bevor Sie beginnen

Wenn Sie Forefront Threat Management Gateway 2010 als Reverse-Proxy erfolgreich bereitstellen möchten, müssen Sie einen Server einrichten und konfigurieren, indem Sie die Voraussetzungen und Hardwareanforderungen verwenden, die in der Forefront Threat Management Gateway 2010-Dokumentation definiert sind. Lesen Sie das folgende Thema, das für die ordnungsgemäße Konfiguration der Hardware und die Installation von Forefront Threat Management Gateway 2010 auf dem Server festgesetzt ist, bevor Sie fortfahren.

  - <span></span>  
    [Forefront Threat Management-Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Empfehlungen für Forefront TMG 2010-Hardware](http://go.microsoft.com/fwlink/?linkid=291293)

Wenn Sie IIS arr erfolgreich als Reverse-Proxy bereitstellen möchten, lesen Sie die folgenden Themen, um die Hardware und die erforderliche Software zu konfigurieren.

  - <span></span>  
    Informationen zum Installieren von IIS unter Windows Server 2008 oder Windows Server 2008 R2 finden Sie unter [Installieren von IIS 7 unter Windows Server 2008 oder Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296) .

  - <span></span>  
    Informationen zum Installieren von IIS unter Windows Server 2012 finden Sie unter [Installieren von IIS 8 unter Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Informationen zum Installieren von IIS unter Windows Server 2012 R2 finden Sie unter [Installieren von IIS 8,5 unter Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687) .

  - <span></span>  
    Zum Herunterladen der Anwendungs Anforderungs-Routingerweiterung für IIS befolgen Sie die Anweisungen unter [Application Request Routing v 2.5 herunterladen](http://go.microsoft.com/fwlink/?linkid=291298) .

  - <span></span>  
    So installieren Sie arr für die Anweisungen unter [Installieren von Anwendungs Anforderungs Routing, Version 2](http://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Die aktuell geposteten Anweisungen gelten für arr 2,0. Für die Installation der Erweiterung gibt es keinen Unterschied zwischen den beiden Versionen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

