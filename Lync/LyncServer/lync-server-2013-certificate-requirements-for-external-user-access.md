---
title: 'Lync Server 2013: Zertifikatanforderungen für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-03-29_

Die Microsoft lync Server 2013-Kommunikationssoftware unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst. Die interne Edge-Schnittstelle verwendet in der Regel ein privates Zertifikat, das von einer internen Zertifizierungsstelle ausgestellt wurde, kann aber auch ein öffentliches Zertifikat verwenden, vorausgesetzt, dass es von einer vertrauenswürdigen öffentlichen Zertifizierungsstelle stammt. Der Reverseproxy in Ihrer Bereitstellung verwendet ein öffentliches Zertifikat und verschlüsselt die Kommunikation vom Reverse Proxy an Clients und den Reverse-Proxy an interne Server mithilfe von http (also Transport Layer Security over HTTP).

Im folgenden sind die Anforderungen für das öffentliche Zertifikat für Access-und Webkonferenz-Edge-externe Schnittstellen sowie der A/V-Authentifizierungsdienst:

  - Das Zertifikat muss von einer genehmigten öffentlichen Zertifizierungsstelle ausgestellt werden, die den alternativen Antragstellernamen unterstützt. Ausführliche Informationen finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Microsoft Knowledge Base-Artikel 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server" unter.

  - Wenn das Zertifikat in einem Edge-Pool verwendet wird, muss es als exportierbar erstellt werden, wobei auf jedem Edgeserver im Edge-Pool dasselbe Zertifikat verwendet wird. Die Anforderung des exportierbaren privaten Schlüssels beruht auf dem A/V-Authentifizierungsdienst, bei dem derselbe private Schlüssel auf allen Edgeserver im Pool verwendet werden muss.

  - Wenn Sie die Verfügbarkeit für Ihre Audio-und Video Dienste maximieren möchten, überprüfen Sie die Zertifikatanforderungen für die Implementierung eines entkoppelte a/v-Edgedienst Zertifikats (d. h. ein separates a/v-Edgedienst Zertifikat aus den anderen externen Edge-Zertifikat Zwecken). Ausführliche Informationen finden Sie unter [Änderungen in lync Server 2013, die Auswirkungen auf die Planung von Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)-Servern haben, [Planen von Edgeserver-Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) und bereit [Stellen von AV-und OAuth-Zertifikaten in lync Server 2013 mithilfe von-Rolle in CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - Der Antragstellername des Zertifikats ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Access Edge Service oder das Hardware-Lastenausgleichsmodul VIP (beispielsweise Access.contoso.com). ). Der Name des Antragstellers darf kein Platzhalterzeichen aufweisen, er muss ein expliziter Name sein.
    
    <div>
    

    > [!NOTE]  
    > Bei lync Server 2013 ist dies nicht mehr erforderlich, wird jedoch weiterhin für die Kompatibilität mit Office Communications Server empfohlen.

    
    </div>

  - Die Liste Subject Alternative Name enthält die FQDNs der folgenden:
    
      - Die externe Schnittstelle für den Access Edge-Dienst oder das Hardwarelastenausgleich-VIP-Element (beispielsweise SIP.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Auch wenn der Name des Zertifikat Antragstellers mit dem FQDN des Access-Edge identisch ist, muss der Alternative Subjektname auch den Access-Edge-FQDN enthalten, da Transport Layer Security (TLS) den Namen des Antragstellers ignoriert und die Einträge für den alternativen Subjektnamen verwendet für Überprüfung.

        
        </div>
    
      - Die externe Schnittstelle für Web Conferencing Edge oder Hardware Load Balancer VIP (beispielsweise webcon.contoso.com).
    
      - Wenn Sie die automatische Konfiguration oder Föderation des Clients verwenden, schließen Sie auch alle in Ihrem Unternehmen verwendeten SIP-Domänen-FQDNs ein (beispielsweise SIP.contoso.com, SIP.fabrikam.com).
    
      - Der A/V-Edgedienst verwendet nicht den Namen des Antragstellers oder die Einträge des alternativen betreffs.
    
    <div>
    

    > [!NOTE]  
    > Die Reihenfolge der FQDNs in der Liste der alternativen Subjektnamen spielt keine Rolle.

    
    </div>

Wenn Sie mehrere Edgeserver mit Lastenausgleich an einer Website bereitstellen, muss das auf jedem Edgeserver installierte a/V-Authentifizierungsdienst Zertifikat von der gleichen Zertifizierungsstelle sein und denselben privaten Schlüssel verwenden. Beachten Sie, dass der private Schlüssel des Zertifikats exportierbar sein muss, unabhängig davon, ob er auf einem Edgeserver oder auf vielen Edgeserver verwendet wird. Sie muss auch exportierbar sein, wenn Sie das Zertifikat von einem anderen Computer als dem Edgeserver anfordern. Da der A/V-Authentifizierungsdienst den Antragstellernamen oder den alternativen Antragstellernamen nicht verwendet, können Sie das Access-Edge-Zertifikat wieder verwenden, sofern die Anforderungen für den Antragstellernamen und den alternativen Antragstellernamen für den Access-Edge und den Webkonferenz-Edge erfüllt sind. und der private Schlüssel des Zertifikats ist exportierbar.

Voraussetzungen für das private (oder öffentliche) Zertifikat, das für die Edge-interne Schnittstelle verwendet wird, sind wie folgt:

  - Das Zertifikat kann von einer internen Zertifizierungsstelle oder einer genehmigten öffentlichen Zertifikat Zertifizierungsstelle ausgestellt werden.

  - Der Antragstellername des Zertifikats entspricht in der Regel dem FQDN des Edge-internen Interfaces oder dem Hardware Load Balancer VIP (beispielsweise lsedge.contoso.com). Sie können jedoch ein Platzhalterzertifikat auf dem internen Rand verwenden.

  - Es ist keine Liste der alternativen Betreff-Namen erforderlich.

Der Reverse-Proxy in ihren Bereitstellungsdienst Anforderungen für:

  - Zugriff externer Benutzer auf Besprechungsinhalte für Besprechungen

  - Zugriff durch externe Benutzer zum Erweitern und Anzeigen von Mitgliedern von Verteilergruppen

  - Zugriff externer Benutzer auf herunterladbare Dateien aus dem Adressbuchdienst

  - Zugriff externer Benutzer auf den lync Web App-Client

  - Zugriff externer Benutzer auf die Webseite "Einstellungen für Einwahlkonferenzen"

  - Zugriff externer Benutzer auf den standortinformationsdienst

  - Zugriff auf externe Geräte für den Geräteaktualisierungsdienst und Abrufen von Updates

Der Reverse-Proxy veröffentlicht die URLs der internen Server-Webkomponenten. Die Webkomponenten-URLs werden auf dem Director, Front-End-Server oder Front-End-Pool als **externe** Webdienste im Topologie-Generator definiert.

Platzhaltereinträge werden im Feld Subject Alternative Name des dem Reverse-Proxy zugewiesenen Zertifikats unterstützt. Details zum Konfigurieren der Zertifikatanforderung für den Reverseproxy finden Sie unter [anfordern und Konfigurieren eines Zertifikats für den Reverse http-Proxy in lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Siehe auch


[Unterstützung von Platzhalterzertifikaten in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

