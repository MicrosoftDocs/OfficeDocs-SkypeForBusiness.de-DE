---
title: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer'
TOCTitle: Zertifikatanforderungen für den Zugriff durch externe Benutzer
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398920(v=OCS.15)
ms:contentKeyID: 49295516
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Microsoft Lync Server 2013- Kommunikationssoftware unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für die externen Edgeschnittstellen für Zugriff und Webkonferenzen sowie für die interne Edgeschnittstelle für den Audio-Video-Authentifizierungsdienst. Für die interne Edgeschnittstelle wird üblicherweise ein von einer internen Zertifizierungsstelle ausgestelltes privates Zertifikat verwendet, es kann jedoch auch ein öffentliches Zertifikat verwendet werden, wenn dieses von einer vertrauenswürdigen Zertifizierungsstelle stammt.

Im Folgenden finden Sie die Anforderungen für das öffentliche Zertifikat, das für die externen Edgeschnittstellen für Zugriff und Webkonferenzen sowie für den Audio-Video-Authentifizierungsdienst verwendet wird:

  - Das Zertifikat muss von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden, die alternative Antragstellernamen unterstützt. Genauere Informationen finden Sie in dem Microsoft Knowledge Base-Artikel 929395 "Unified Communications Certificate Partners for Exchange Server and for Communications Server" unter [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).

  - Wenn das Zertifikat in einem Edgepool verwendet werden soll, muss es als exportierbares Zertifikat erstellt werden, und es muss auf jedem Edgeserver im Edgepool das gleiche Zertifikat verwendet werden. Der private Schlüssel als exportierbarer Schlüssel ist für die Verwendung mit dem Audio-Video-Authentifizierungsdienst notwendig, der für alle Edgeserver des Pools den gleichen privaten Schlüssel verwenden muss.

  - Wenn Sie die Betriebszeit für Ihre Audio-/Videodienste maximieren möchten, lesen Sie die Zertifikatanforderungen zum Implementieren eines entkoppelten A/V-Edgedienst-Zertifikats durch (d. h., ein von den anderen externen Edgezertifikaten separates A/V-Edgedienst-Zertifikat). Ausführliche Informationen finden Sie unter [Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) und [Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate).

  - Der Antragstellername für das Zertifikat ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) oder die virtuelle IP-Adresse (VIP) eines Hardwaregeräts zum Lastenausgleich der externen Zugriffs-Edgedienst-Schnittstelle (zum Beispiel access.contoso.com ).
    

    > [!NOTE]
    > Für Lync Server 2013 ist dies nicht mehr zwingend erforderlich, wird jedoch aus Gründen der Kompatibilität mit Office Communications Server weiterhin empfohlen.



  - Die Liste der alternativen Antragstellernamen enthält folgende FQDNs:
    
      - Die externe Zugriffs-Edgedienst-Schnittstelle für den Zugriff oder die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel sip.contoso.com ).
        

        > [!NOTE]
        > Auch wenn der Antragstellername des Zertifikats dem FQDN des Zugriffsedges entspricht, muss der alternative Antragstellername auch den FQDN des Zugriffs-Edgeservers enthalten, da TLS (Transport Layer Security) den Antragstellernamen ignoriert und zur Überprüfung die Einträge für alternative Antragstellernamen verwendet.

    
      - Die externe Edgeschnittstelle für Webkonferenzen oder die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "webcon.contoso.com").
    
      - Wenn Sie die automatische Clientkonfiguration oder Partnerverbundfunktionen nutzen, geben Sie auch alle in Ihrem Unternehmen verwendeten FQDNs der SIP-Domäne an (zum Beispiel "sip.contoso.com", "sip.fabrikam.com").
    
      - Der A/V-Edgedienst verwendet die Einträge für Antragstellername oder den alternativen Antragstellernamen nicht.
    

    > [!NOTE]
    > Die Reihenfolge der FQDNs in den alternativen Antragstellernamen spielt keine Rolle.



Wenn Sie an einem Standort mehrere Edgeserver mit Lastenausgleich bereitstellen, müssen alle auf den Edgeservern installierten Zertifikate für den Audio-Video-Authentifizierungsdienst von der gleichen Zertifizierungsstelle stammen und den gleichen privaten Schlüssel verwenden. Beachten Sie, dass der private Schlüssel des Zertifikats exportierbar sein muss, unabhängig davon, ob das Zertifikat auf einem oder mehreren Edgeservern verwendet wird. Dies gilt auch, wenn Sie das Zertifikat von einem anderen Computer als dem Edgeserver anfordern.

Folgende Anforderungen gelten für das private (oder öffentliche) Zertifikat für die interne Edgeschnittstelle:

  - Das Zertifikat kann von einer internen Zertifizierungsstelle oder einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden.

  - Beim Antragstellernamen des Zertifikats handelt es sich üblicherweise um den FQDN der internen Edgeschnittstelle oder um die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "lsedge.contoso.com"). Für die interne Edgeschnittstelle können Sie jedoch auch ein Platzhalterzertifikat verwenden.

  - Eine Liste mit alternativen Antragstellernamen ist nicht erforderlich.

Der Reverseproxy Ihrer Bereitstellungsdienste erfordert Folgendes:

  - Zugriff externer Benutzer auf Besprechungsinhalte bei Besprechungen

  - Zugriff externer Benutzer für das Erweitern und Anzeigen von Mitgliedern von Verteilergruppen

  - Zugriff externer Benutzer auf herunterladbare Dateien vom Adressbuchdienst

  - Zugriff externer Benutzer auf Lync Web App-Clients

  - Zugriff externer Benutzer auf die Webseite für Einwahlkonferenzeinstellungen

  - Zugriff externer Benutzer auf den Standortinformationsdienst

  - Zugriff durch externe Geräte auf den Geräteaktualisierungsdienst und die Berechtigung, Updates anzufordern

Der Reverseproxy veröffentlicht die URLs für die Webkomponenten auf internen Servern. Die URLs für Webkomponenten werden auf dem Director, Front-End-Server oder Front-End-Pool als die **Externen Webdienste** in Topologie-Generator definiert.

Einträge mit Platzhalterzeichen werden im Feld für den alternativen Antragstellernamen des für den Reverseproxy zugewiesenen Zertifikats unterstützt. Weitere Informationen zur Konfiguration der Zertifikatanforderung für den Reverseproxy finden Sie unter [Anfordern und Konfigurieren eines Zertifikats für den HTTP-Reverseproxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

## Siehe auch

#### Konzepte

[Unterstützung von Platzhalterzertifikaten in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

