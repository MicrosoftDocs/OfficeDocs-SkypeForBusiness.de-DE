---
title: 'Lync Server 2013: Szenarien für Reverseproxys'
TOCTitle: Szenarien für Reverseproxys
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204691(v=OCS.15)
ms:contentKeyID: 49293243
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Szenarien für Reverseproxys in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-01-21_

Reverseproxys sind in Lync Server 2013 erforderlich, um Zugriff auf Dienste und Ressourcen wie z. B. die einfachen Besprechungs- und Einwahl-URLs, Adressbücher, Besprechungsinhalte, Verteilerlistenerweiterungen, Mobilitätsdienste usw. bereitzustellen. Das gängige Reverseproxyszenario in Lync Server 2013 besteht darin, dass externen Clients (z. B. dem Desktopclient oder dem Lync Web App-Client) Zugriff auf die externen Director- oder Front-End-Server-Webdienste gewährt wird.

**Reverseproxy und externe Webdienste**

![Reverseproxy und externe Webdienste](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Reverseproxy und externe Webdienste")

Während der Planungsphase definieren Sie die Voraussetzungen für den Reverseproxy in einer Lync Server 2013-Bereitstellung. Der Reverseproxy ermöglicht ermöglicht den Zugriff auf Features für die folgenden externen Clients:

  - Microsoft Lync 2013-Desktopclient

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Windows Store-App für Lync

Beim Planen Ihrer Lync Server 2013-Bereitstellung ordnen Sie den Reverseproxyfeatures die tatsächlichen Anforderungen für Lync Server 2013 zu.

1.  Externe Clients stellen an Port TCP 443 eine Verbindung zum Reverseproxy her und verwenden SSL (Secure Socket Layer) oder TLS (SSL) oder (Transport Layer Security). Microsoft Lync Mobile-Clients können an Port TCP 80 eine Verbindung herstellen; dies ist jedoch nur möglich, wenn bei der ersten Verbindung mit den Lync-Ermittlungsdiensten und dem Administrator die richtigen DNS (Domain Name Service)-CNAME (oder Alias)-Einträge konfiguriert wurden, und wenn akzeptiert wird, dass diese Kommunikation unverschlüsselt ist.

2.  Externe Lync Server 2013-Webdienste (bereitgestellt auf dem Front-End-Server und/oder dem Director) erwarten einer Verbindung von einem Reverseproxy an Port TCP 4443; dabei wird eine SSL/TLS-Verbindung erwartet.
    

    > [!IMPORTANT]
    > Die vorgeschlagenen Standardüberwachungsports für die externen Webdienste sind TCP&nbsp;8080 für HTTP-Datenverkehr und TCP&nbsp;4443 für HTTPS-Datenverkehr. Topologie-Generator bietet eine Möglichkeit, die Standardeinstellungen zu überschreiben und eigene Überwachungsports für die externen Webdienste festzulegen. Es muss berücksichtigt werden, dass der Reverseproxy mit den externen Webdiensten und die externen Webdienste mit dem Reverseproxy kommunizieren. Der externe Client kommuniziert mit dem Reverseproxy an Port TCP&nbsp;443, Sie können den Port, an dem der Reverseproxy mit den externen Webdiensten kommuniziert jedoch neu festlegen. Die Optionen in Topologie-Generator zum Außerkraftsetzen der Standardüberwachungsports für die Webdienste ermöglicht Ihnen das Lösen von Überwachungsportkonflikten, die in Ihrer Infrastruktur u.&nbsp;U. auftreten.



3.  Externe Lync Server 2013-Webdienste erwarten einen nicht veränderten Hostheader vom Client um zu identifizieren, welchen Dienst und welches Webserververzeichnis der Client zu verwenden versucht. Anfragen sollten aussehen, als kämen sie vom Reverseproxy.

4.  Die externen Webdienste verwenden verwenden definierte virtuelle Webserververzeichnisse (vDir), welche die den Clients zur Verfügung gestellten Dienste bereitstellen. Bestimmte extern identifizierbare Webdienste sind:
    
      - Das vDir "Meet" für Webkonferenzbesprechungen
    
      - Das vDir "Dialin" für Telefonzugriff und Telefonkonferenzen
    
      - Das vDir "Autodiscover" für Windows Store-App für Lync, Lync Mobile und den Lync 2013-Desktopclient. Die AutoErmittlung in Lync Server 2013 ist unter dem DNS-Namen "lyncdiscover" bekannt.
    
      - Auf nicht definierte Dienste greift der externe Client durch direkte Aufrufe der externen Webdienste zu. Beispielsweise wird auf die Verteilergruppenerweiterung (DLX) und den Adressbuchdienst (ABS) durch direkte Aufrufe der externen Webdienste und der zugeordneten vDirs zugegriffen. Der Client kennt den tatsächlichen Pfad zum vDir und erstellt basierend auf diesen Informationen eine URL (Uniform Record Locator). Der Client greift auf den Adressbuchdienst mit einer ähnlichen URL wir der folgenden zu: `https://externalweb.contoso.com/abs/handler`.
    
      - Der Office Web Apps-Server wird bei Konferenzen als Teil der Lync Server-Topologie definiert und konfiguriert.
        

        > [!NOTE]
        > Der Office Web Apps-Server ist ein separater Rollenserver und wird nicht als Teil der externen Webdienste konfiguriert. Dieser Server wird für den Clientzugriff separat veröffentlicht.



5.  Definieren Sie SSL-Bridging für jeden Dienst. Der externe Port TCP 443 wird dem externen Webdienstport TCP 4443 zugeordnet. Für unverschlüsseltes HTTP wird Port TCP 80 dem externen Webdienstport TCP 8080 zugeordnet.

6.  Planen von Reverseproxylistenern zum Veröffentlichen von Webserverressourcen

7.  Fordern Sie das Zertifikat für den Reverseproxy basierend auf den Diensten an, die angeboten werden, und konfigurieren Sie es. Wenn dieses Zertifikat mit den richtigen alternativen Antragstellernamen konfiguriert ist, kann es von allen konfigurierten Listenern auf dem Reverseproxyserver gemeinsam verwendet werden.

Verfügbare Ressourcen für die Planung Ihrer Reverseproxybereitstellung:

  - [Datenerfassung in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Portzusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS-Zusammenfassung für Reverseproxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

