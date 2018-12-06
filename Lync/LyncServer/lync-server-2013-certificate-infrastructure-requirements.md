---
title: 'Lync Server 2013: Anforderungen in Bezug auf die Zertifikatsinfrastruktur'
TOCTitle: Anforderungen in Bezug auf die Zertifikatinfrastruktur
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398066(v=OCS.15)
ms:contentKeyID: 49292972
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS- (Transport Layer Security) und MTLS-Verbindungen (Mutual TLS).

Lync Server nutzt Zertifikate für die folgenden Zwecke:

  - TLS-Verbindungen zwischen Client und Server

  - MTLS-Verbindungen zwischen Servern

  - Partnerverbund mit automatischer DNS-Ermittlung von Partnern

  - Zugriff von Remotebenutzern auf Sofortnachrichten

  - Zugriff externer Benutzer auf A/V-Sitzungen, Anwendungsfreigabe und Konferenzen

  - Mobile Anforderungen mithilfe der automatischen Ermittlung von Webdiensten

Für Lync Server gelten die folgenden allgemeinen Anforderungen:

  - Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage \[EKU\], erweiterte Schlüsselverwendung für Server) unterstützen.

  - Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.

  - Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Lync Server 2013 unterstützt die Digestgrößen der SHA-1- und SHA-2-Suite (224, 256, 384 und 512 Bit) und entspricht den oder übertrifft die Betriebssystemanforderungen. Informationen zur Betriebssystemunterstützung finden Sie unter [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).

  - Die automatische Registrierung wird für interne Server mit Lync Server unterstützt.

  - Die automatische Registrierung wird für Lync Server-Edgeserver nicht unterstützt.

  - Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle senden möchten, muss diese von einem Computer aus gesendet werden, auf dem entweder Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
    Wenngleich mit Update KB922706 Probleme beim Registrieren von Webzertifikaten für eine Windows Server 2003-Zertifikatdienste-Webregistrierung behoben werden können, ist es mit diesem Update nicht möglich, über Windows Server 2008, Windows Vista oder Windows 7 ein Zertifikat bei einer Windows Server 2003-Zertifizierungsstelle anzufordern.

  - Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt. Empfohlen werden Schlüssellängen ab 2.048 Bit.

  - Der standardmäßige Digest- bzw. Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH\_P256, ECDH\_P384 und ECDH\_P521 werden ebenfalls unterstützt.

## In diesem Abschnitt

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatanforderungen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Zertifikatanforderungen für die Mobilität in Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

