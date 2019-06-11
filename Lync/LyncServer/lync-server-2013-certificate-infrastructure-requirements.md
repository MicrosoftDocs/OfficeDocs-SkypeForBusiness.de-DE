---
title: 'Lync Server 2013: Anforderungen in Bezug auf die Zertifikatsinfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-06-23_

Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS-und MTLS-Verbindungen (Mutual TLS).

Lync Server verwendet Zertifikate für die folgenden Zwecke:

  - TLS-Verbindungen zwischen Client und Server

  - MTLS-Verbindungen zwischen Servern

  - Föderation mithilfe der automatischen DNS-Ermittlung von Partnern

  - Zugriff von Remotebenutzern auf Sofortnachrichten

  - Zugriff externer Benutzer auf Audio/Video-Sitzungen (A/V), Anwendungsfreigabe und Konferenzen

  - Mobile Anforderungen mithilfe der automatischen Ermittlung von Webdiensten

Für lync Server gelten die folgenden allgemeinen Voraussetzungen:

  - Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.

  - Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.

  - Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Lync Server 2013 unterstützt die SHA-1-und SHA-2-Suite von Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Anforderungen des Betriebssystems. Informationen zur Unterstützung des Betriebs [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)Systems finden Sie unter.
    
    <div>
    

    > [!NOTE]  
    > Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei der Anmeldung und Problemen mit der Anrufweiterleitung führen. 

    
    </div>

  - Die automatische Registrierung wird für interne Server unterstützt, auf denen lync Server ausgeführt wird.

  - Die automatische Registrierung wird für lync Server Edge-Server nicht unterstützt.

  - Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle übermitteln, müssen Sie Sie von einem Computer übermitteln, auf dem Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.
    
    Beachten Sie, dass KB922706 zwar Unterstützung für das Beheben von Problemen beim Registrieren von webzertifikaten für eine Windows Server 2003 Certificate Services-Webregistrierung bietet, es jedoch nicht möglich ist, Windows Server 2008, Windows Vista oder Windows 7 zu verwenden, um eine Zertifikat von einer Windows Server 2003-Zertifizierungsstelle

  - Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt. Empfohlen werden Schlüssellängen ab 2.048 Bit.

  - Der Standard-Digest-oder Hash-Signaturalgorithmus ist RSA. Die Algorithmen\_ECDH P256,\_ECDH P384 und ECDH\_P521 werden ebenfalls unterstützt. 

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Zertifikatanforderungen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Zertifikatanforderungen für die Mobilität in Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

