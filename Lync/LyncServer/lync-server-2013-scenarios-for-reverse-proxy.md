---
title: 'Lync Server 2013: Szenarien für Reverseproxys'
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
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Szenarien für Reverseproxys in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-21_

Umgekehrte Proxys sind in lync Server 2013 für den Zugriff auf Dienste und Ressourcen wie die Besprechungs-und Einwahl einfachen URLs, das Adressbuch, den Besprechungsinhalt, die Erweiterung der Verteilerliste, Mobilitätsdienste und andere erforderlich. Das typische Reverse-Proxy-Szenario in lync Server 2013 ist es, externen Clients (beispielsweise dem Desktop Client oder lync Web App-Client) Zugriff auf externe Webdienste des Director-oder Front-End-Servers zu ermöglichen.

**Reverse-Proxy und externe Webdienste**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

Während der Planungsphase definieren Sie die Anforderungen für den Reverse Proxy in einer lync Server 2013-Bereitstellung. Der Reverse-Proxy ermöglicht den Zugriff auf Features für die folgenden externen Clients:

  - Microsoft lync 2013-Desktop Client

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Windows Store-App für Lync

Bei der Planung Ihrer lync Server 2013-Bereitstellung ordnen Sie die tatsächlichen Anforderungen für lync Server 2013 den Reverse-Proxy Features zu.

1.  Externe Clients stellen eine Verbindung mit dem Reverse Proxy auf Port TCP 443 her und verwenden Secure Socket Layer (SSL) oder Transport Layer Security (TLS). Microsoft lync Mobile-Clients können eine Verbindung mit Port TCP 80 herstellen, allerdings nur, wenn die anfängliche Verbindung mit den lync Discover-Diensten hergestellt wird und der Administrator die richtigen DNS-Einträge (Domain Name System) konfiguriert hat, und akzeptiert, dass diese die Kommunikation wird nicht verschlüsselt.

2.  Lync Server 2013-externe Webdienste (bereitgestellt auf dem Front-End-Server und/oder der Director) erwarten eine Verbindung von einem Reverseproxy auf Port TCP 4443, und es wird erwartet, dass die Verbindung SSL/TLS ist.
    
    <div>
    

    > [!IMPORTANT]  
    > Die empfohlenen Standard Überwachungsanschlüsse für die externen Webdienste sind TCP 8080 für HTTP-Datenverkehr und TCP 4443 für HTTPS-Datenverkehr. Der Topologie-Generator bietet die Möglichkeit, die Standardeinstellungen zu überschreiben und ihre eigenen Überwachungsanschlüsse für die externen Webdienste zu definieren. Beachten Sie, dass der Reverse-Proxy mit den externen Webdiensten kommuniziert und die externen Clients mit dem Reverse-Proxy kommunizieren. Der externe Client kommuniziert mit dem Reverseproxy auf Port TCP 443, aber Sie können neu definieren, welchen Port der Reverse-Proxy mit den externen Webdiensten kommuniziert. Mit den Optionen im Topologie-Generator können Sie die standardmäßigen Überwachungsanschlüsse für die Webdienste überschreiben, um die Überwachung von Port Konflikten zu beheben, die in Ihrer Infrastruktur auftreten können.

    
    </div>

3.  Lync Server 2013-externe Webdienste erwarten einen unveränderten Host Header vom Client, um zu ermitteln, welches Dienst-und Webserververzeichnis der Client verwenden möchte. Anforderungen sollten so aussehen, als ob Sie vom Reverse-Proxy stammen

4.  Die externen Webdienste verwenden definierte Webserver Virtual Directories (vDir), die die für Clients angebotenen Dienste bereitstellen. Bestimmte extern identifizierbare Webdienste sind:
    
      - Die "Besprechung"-vDir für Webkonferenzbesprechungen
    
      - "Dialin"-vDir für Telefon-und Telefonkonferenzen
    
      - Der "Auto Ermittlungs-vDir" für die lync Windows Store-App, lync Mobile und den Desktop Client lync 2013. Die AutoErmittlung in lync Server 2013 ist unter dem DNS-Namen "lyncdiscover" bekannt.
    
      - Auf Dienste, die nicht definiert sind, wird vom externen Client durch direkte Anrufe an die externen Webdienste zugegriffen. So können Sie beispielsweisedurch direkte Anrufe an externe Webdienste und zugeordnete vDirs auf die Expansion von Verteilergruppen (dlx) und den Adressbuchdienst (ABS) zugreifen. Der Client kennt den tatsächlichen Pfad zum vDir und erstellt basierend auf diesen Informationen einen Uniform Record Locator (URL). Der Clientzugriff auf den Adressbuchdienst mit einer URL ähnlich wie`https://externalweb.contoso.com/abs/handler`
    
      - Der Office Web Apps-Server, wenn Konferenzen als Teil der lync Server-Topologie definiert und konfiguriert sind
        
        <div>
        

        > [!NOTE]  
        > Der Office Web Apps-Server ist ein separater Rollen Server und nicht als Teil der externen Webdienste konfiguriert. Dieser Server wird separat für den Clientzugriff veröffentlicht.

        
        </div>

5.  Definieren Sie SSL-Bridging für jeden Dienst. Der externe Port TCP 443 wird dem external Web Services-Port von TCP 4443 zugeordnet. Für unverschlüsselte http wird Port TCP 80 dem externen Webdienste-Port TCP 8080 zugeordnet.

6.  Planen von Reverse Proxy-Listenern zum Veröffentlichen von Webserverressourcen

7.  Sie können das Zertifikat für den Reverse-Proxy basierend auf den angebotenen Diensten anfordern und konfigurieren. Wenn dieses Zertifikat mit dem richtigen Alternativen Betreff-Namen konfiguriert wurde, kann es von allen konfigurierten Listener auf dem Reverse-Proxy Server freigegeben werden.

Ressourcen, die für die Planung der Reverse-Proxybereitstellung verfügbar sind:

  - [Datenerfassung in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Portzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS-Zusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

