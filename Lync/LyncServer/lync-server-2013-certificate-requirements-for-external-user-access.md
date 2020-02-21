---
title: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda45706b8c55bf99120ec3776702060998a6921
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-03-29_

Microsoft lync Server 2013 Kommunikationssoftware unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst. Die interne Edge-Schnittstelle verwendet in der Regel ein privates Zertifikat, das von einer internen Zertifizierungsstelle ausgestellt wurde, kann aber auch ein öffentliches Zertifikat verwenden, vorausgesetzt, es stammt von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle. Der Reverseproxy in Ihrer Bereitstellung verwendet ein öffentliches Zertifikat und verschlüsselt die Kommunikation vom Reverseproxy zu Clients und dem Reverseproxy mit internen Servern mithilfe von http (also Transport Layer Security over HTTP).

Im Folgenden finden Sie die Anforderungen für das öffentliche Zertifikat, das für die externen Edgeschnittstellen für Zugriff und Webkonferenzen sowie für den Audio-Video-Authentifizierungsdienst verwendet wird:

  - Das Zertifikat muss von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden, die alternative Antragstellernamen unterstützt. Ausführliche Informationen finden Sie im [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)Microsoft Knowledge Base-Artikel 929395, "Unified Communications Zertifikat Partner für Exchange Server und für Communications Server" unter.

  - Wenn das Zertifikat in einem Edgepool verwendet werden soll, muss es als exportierbares Zertifikat erstellt werden, und es muss auf jedem Edgeserver im Edgepool das gleiche Zertifikat verwendet werden. Der private Schlüssel als exportierbarer Schlüssel ist für die Verwendung mit dem Audio-Video-Authentifizierungsdienst notwendig, der für alle Edgeserver des Pools den gleichen privaten Schlüssel verwenden muss.

  - Wenn Sie die Verfügbarkeit Ihrer Audio/Video-Dienste maximieren möchten, überprüfen Sie die Zertifikatanforderungen für die Implementierung eines entkoppelten A/V-Edgedienst Zertifikats (ein separates A/V-Edgedienst Zertifikat aus dem anderen externen Edge-Zertifikat). Ausführliche Informationen finden Sie unter [Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) und [Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in der Gruppe CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - Der Antragstellername des Zertifikats ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) der Zugriffs-Edgedienst externen Schnittstelle oder VIP des Hardwarelastenausgleichs (beispielsweise Access.contoso.com). ). Der Antragstellername darf kein Platzhalterzeichen sein, er muss ein expliziter Name sein.
    
    <div>
    

    > [!NOTE]  
    > Für lync Server 2013 ist dies nicht mehr erforderlich, wird aber weiterhin für die Kompatibilität mit Office Communications Server empfohlen.

    
    </div>

  - Die Liste der alternativen Antragstellernamen enthält folgende FQDNs:
    
      - Die Zugriffs-Edgedienst externe Schnittstelle oder Hardwaregerät zum Lastenausgleich (beispielsweise SIP.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Auch wenn der Antragstellername des Zertifikats dem FQDN des Zugriffsedges entspricht, muss der alternative Antragstellername auch den FQDN des Zugriffs-Edgeservers enthalten, da TLS (Transport Layer Security) den Antragstellernamen ignoriert und zur Überprüfung die Einträge für alternative Antragstellernamen verwendet.

        
        </div>
    
      - Die externe Edgeschnittstelle für Webkonferenzen oder die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "webcon.contoso.com").
    
      - Wenn Sie die automatische Clientkonfiguration oder Partnerverbundfunktionen nutzen, geben Sie auch alle in Ihrem Unternehmen verwendeten FQDNs der SIP-Domäne an (zum Beispiel "sip.contoso.com", "sip.fabrikam.com").
    
      - Der A/V-Edgedienst verwendet nicht den Antragstellernamen oder die Einträge für alternative Antragstellernamen.
    
    <div>
    

    > [!NOTE]  
    > Die Reihenfolge der FQDNs in den alternativen Antragstellernamen spielt keine Rolle.

    
    </div>

Wenn Sie an einem Standort mehrere Edgeserver mit Lastenausgleich bereitstellen, müssen alle auf den Edgeservern installierten Zertifikate für den Audio-Video-Authentifizierungsdienst von der gleichen Zertifizierungsstelle stammen und den gleichen privaten Schlüssel verwenden. Beachten Sie, dass der private Schlüssel des Zertifikats exportierbar sein muss, unabhängig davon, ob das Zertifikat auf einem oder mehreren Edgeservern verwendet wird. Dies gilt auch, wenn Sie das Zertifikat von einem anderen Computer als dem Edgeserver anfordern.

Folgende Anforderungen gelten für das private (oder öffentliche) Zertifikat für die interne Edgeschnittstelle:

  - Das Zertifikat kann von einer internen Zertifizierungsstelle oder einer vertrauenswürdigen öffentlichen Zertifizierungsstelle ausgestellt werden.

  - Beim Antragstellernamen des Zertifikats handelt es sich üblicherweise um den FQDN der internen Edgeschnittstelle oder um die VIP eines Hardwaregeräts zum Lastenausgleich (zum Beispiel "lsedge.contoso.com"). Für die interne Edgeschnittstelle können Sie jedoch auch ein Platzhalterzertifikat verwenden.

  - Eine Liste mit alternativen Antragstellernamen ist nicht erforderlich.

Der Reverseproxy Ihrer Bereitstellungsdienste erfordert Folgendes:

  - Zugriff externer Benutzer auf Besprechungsinhalte bei Besprechungen

  - Zugriff externer Benutzer für das Erweitern und Anzeigen von Mitgliedern von Verteilergruppen

  - Zugriff externer Benutzer auf herunterladbare Dateien vom Adressbuchdienst

  - Zugriff externer Benutzer auf den lync Web App-Client

  - Zugriff externer Benutzer auf die Webseite für Einwahlkonferenzeinstellungen

  - Zugriff externer Benutzer auf den Standortinformationsdienst

  - Zugriff durch externe Geräte auf den Geräteaktualisierungsdienst und die Berechtigung, Updates anzufordern

Der Reverseproxy veröffentlicht die URLs für die Webkomponenten auf internen Servern. Die Webkomponenten-URLs werden auf dem Director, Front-End-Server oder Front-End-Pool als **externe Webdienste** im Topologie-Generator definiert.

Einträge mit Platzhalterzeichen werden im Feld für den alternativen Antragstellernamen des für den Reverseproxy zugewiesenen Zertifikats unterstützt. Ausführliche Informationen dazu, wie Sie die Zertifikatanforderung für den Reverseproxy konfigurieren, finden Sie unter [Anforderung und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Siehe auch


[Unterstützung von Platzhalterzertifikaten in lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

