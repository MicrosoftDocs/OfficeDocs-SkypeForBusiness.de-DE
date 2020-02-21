---
title: 'Lync Server 2013: Szenarien für Reverse Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3b987cfc1a982139aa0151e43918f0ed082034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Szenarien für Reverse Proxy in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-21_

Reverse-Proxies sind in lync Server 2013 erforderlich, um Zugriff auf Dienste und Ressourcen wie die Besprechungs-und Einwahl-URLs, Adressbuch, Besprechungsinhalte, Verteilerlistenerweiterung, Mobilitätsdienste und andere bereitzustellen. Das typische Reverse-Proxy-Szenario in lync Server 2013 ist, externen Clients (beispielsweise dem Desktop Client oder lync Web App-Client) Zugriff auf den Director oder Front-End-Server externe Webdienste zu ermöglichen.

**Reverse-Proxy und externe Webdienste**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

In der Planungsphase definieren Sie die Anforderungen für den Reverseproxy in einer lync Server 2013-Bereitstellung. Der Reverseproxy ermöglicht den Zugriff auf Features für die folgenden externen Clients:

  - Microsoft lync 2013-Desktop Client

  - Microsoft Lync Web App

  - Microsoft lync Mobile

  - Lync Windows Store-App

Bei der Planung Ihrer lync Server 2013-Bereitstellung ordnen Sie die tatsächlichen Anforderungen für lync Server 2013 den Reverse-Proxyfunktionen zu.

1.  Externe Clients stellen eine Verbindung mit dem Reverseproxy an Port TCP 443 her und verwenden Secure Socket Layer (SSL) oder TLS (Transport Layer Security). Microsoft lync Mobile-Clients können eine Verbindung mit Port TCP 80 herstellen, jedoch nur, wenn die anfängliche Verbindung mit den lync Discover-Diensten hergestellt wird und der Administrator die entsprechenden DNS-Einträge (Domain Name System) konfiguriert hat und akzeptiert, dass dieser die Kommunikation wird nicht verschlüsselt.

2.  Lync Server 2013 externe Webdienste (auf dem Front-End-Server und/oder dem Director bereitgestellt) erwarten eine Verbindung von einem Reverseproxy auf Port TCP 4443, und es wird erwartet, dass die Verbindung SSL/TLS ist.
    
    <div>
    

    > [!IMPORTANT]  
    > Die empfohlenen standardüberwachungs-Ports für die externen Webdienste sind TCP 8080 für HTTP-Datenverkehr und TCP 4443 für HTTPS-Datenverkehr. Der Topologie-Generator bietet die Möglichkeit, die Standardwerte außer Kraft zu setzen und eigene Abhör-Ports für die externen Webdienste zu definieren. Beachten Sie, dass der Reverseproxy mit den externen Webdiensten kommuniziert und die externen Clients mit dem Reverse-Proxy kommunizieren. Der externe Client kommuniziert mit dem Reverseproxy auf Port TCP 443, aber Sie können neu definieren, welchen Port der Reverseproxy mit den externen Webdiensten kommuniziert. Mit den Optionen im Topologie-Generator zum außer Kraft setzen der standardüberwachungs-Ports für die Webdienste können Sie Abhör Portkonflikte beheben, die in Ihrer Infrastruktur auftreten können.

    
    </div>

3.  Lync Server 2013 externe Webdienste erwarten einen unmodifizierten Host Header vom Client, um zu ermitteln, welches Dienst-und Webserververzeichnis der Client zu verwenden versucht. Anforderungen sollten so angezeigt werden, als ob Sie von einem Reverseproxy stammen.

4.  Die externen Webdienste verwenden definierte virtuelle Webserververzeichnisse (vDir), die die für Clients angebotenen Dienste bereitstellen. Bestimmte extern identifizierbare Webdienste sind:
    
      - "Meet"-vDir für Webkonferenzbesprechungen
    
      - Die "Dialin"-vDir für Telefon Zugriff und Telefonkonferenzen
    
      - Die "AutoErmittlung"-vDir für lync Windows Store-App, lync Mobile und den Desktop Client lync 2013. Die AutoErmittlung in lync Server 2013 ist unter dem DNS-Namen "lyncdiscover" bekannt.
    
      - Auf Dienste, die nicht definiert sind, erfolgt der Zugriff durch den externen Client durch direkte Aufrufe an die externen Webdienste. Beispielsweise erfolgt der Zugriff auf die Verteilergruppenerweiterung (dlx) und den Adressbuchdienst (ABS) durch direkte Aufrufe an die externen Webdienste und die zugehörige vDirs. Der Client kennt den tatsächlichen Pfad zum vDir und erstellt basierend auf diesen Informationen einen Uniform Record Locator (URL). Der Client würde auf den Adressbuchdienst zugreifen, indem er eine URL wie`https://externalweb.contoso.com/abs/handler`
    
      - Der Office-webapps-Server, wenn Konferenzen als Teil der lync Server Topologie definiert und konfiguriert werden
        
        <div>
        

        > [!NOTE]  
        > Der Office webapps-Server ist ein separater Rollen Server und ist nicht als Teil der externen Webdienste konfiguriert. Dieser Server wird separat für den Clientzugriff veröffentlicht.

        
        </div>

5.  Definieren Sie SSL-Bridging für jeden Dienst. Der externe Port TCP 443 wird dem externen Webdienste-Port von TCP 4443 zugeordnet. Für unverschlüsseltes http wird Port TCP 80 dem externen Webdienste-Port TCP 8080 zugeordnet.

6.  Planen von Reverse-Proxy Listenern zum Veröffentlichen von Webserverressourcen

7.  Fordern und konfigurieren Sie das Zertifikat für den Reverseproxy basierend auf den Diensten, die angeboten werden. Wenn diese mit den richtigen alternativen Antragstellernamen konfiguriert sind, kann dieses Zertifikat von allen konfigurierten Listener auf dem Reverseproxy gemeinsam verwendet werden.

Verfügbare Ressourcen für die Planung Ihrer Reverseproxybereitstellung:

  - [Datensammlung in lync Server 2013](lync-server-2013-data-collection.md)

  - [Zertifikatzusammenfassung-Reverseproxy in lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Port Zusammenfassung-Reverseproxy in lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS-Zusammenfassung-Reverseproxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

