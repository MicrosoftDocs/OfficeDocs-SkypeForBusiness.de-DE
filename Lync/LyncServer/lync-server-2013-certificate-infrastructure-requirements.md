---
title: Lync Server 2013 Anforderungen an die Zertifikatinfrastruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18666f33becabcbdf61370a32900ae7a4819e0cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508022"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Anforderungen an die Zertifikatinfrastruktur für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-06-23_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS-und MTLS-Verbindungen (Mutual TLS).

Lync Server verwendet Zertifikate für die folgenden Zwecke:

  - TLS-Verbindungen zwischen Client und Server

  - MTLS-Verbindungen zwischen Servern

  - Partnerverbund mit automatischer DNS-Ermittlung von Partnern

  - Zugriff von Remotebenutzern auf Sofortnachrichten

  - Zugriff externer Benutzer auf A/V-Sitzungen, Anwendungsfreigabe und Konferenzen

  - Mobile Anforderungen mithilfe der automatischen Ermittlung von Webdiensten

Für lync Server gelten die folgenden allgemeinen Anforderungen:

  - Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.

  - Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.

  - Alle Zertifikate müssen mit einem vom Betriebssystemunter stützten Signaturalgorithmus signiert werden. Lync Server 2013 unterstützt die SHA-1-und SHA-2-Suite mit Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Betriebssystemanforderungen. Informationen zur Betriebssystemunterstützung finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .
    
    <div>
    

    > [!NOTE]  
    > Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei Anmelde-und Anruf Weiterleitungs Problemen führen.

    
    </div>

  - Die automatische Registrierung wird für interne Server mit lync Server unterstützt.

  - Die automatische Registrierung wird für lync Server-Edge-Server nicht unterstützt.

  - Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle senden möchten, muss diese von einem Computer aus gesendet werden, auf dem entweder Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
    Wenngleich mit Update KB922706 Probleme beim Registrieren von Webzertifikaten für eine Windows Server 2003-Zertifikatdienste-Webregistrierung behoben werden können, ist es mit diesem Update nicht möglich, über Windows Server 2008, Windows Vista oder Windows 7 ein Zertifikat bei einer Windows Server 2003-Zertifizierungsstelle anzufordern.

  - Die Verschlüsselungsschlüssel Längen 1024, 2048 und 4096 werden unterstützt. Die Schlüssellängen von 2048 und höher werden empfohlen.

  - Der standardmäßige Digest-oder Hashsignatur Algorithmus ist RSA. Die \_ Algorithmen ECDH P256, ECDH \_ P384 und ECDH \_ P521 werden ebenfalls unterstützt. 

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatanforderungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Zertifikatanforderungen für die Mobilität in lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

