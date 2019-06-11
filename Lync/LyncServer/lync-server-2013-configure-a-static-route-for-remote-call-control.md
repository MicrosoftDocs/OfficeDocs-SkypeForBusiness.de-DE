---
title: 'Lync Server 2013: Konfigurieren einer statischen Route für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6a388c602d30e6f60eac0c575d7640f63993f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Die Remote Anrufsteuerung setzt voraus, dass jeder lync Server-Pool mit einem Pfad von diesem Pool zum SIP/CSTA-Gateway konfiguriert ist, das eine Verbindung mit der PBX (Private Branch Exchange) herstellt. Dieser Pfad setzt voraus, dass jeder Pool über eine statische Route für jedes Gateway verfügt, für das der Pool SIP-Anruf Steuerungsmeldungen erhält, die mit Anrufen an die Telefonanlage verknüpft sind. Wenn Sie eine globale statische Route für die Remoteanrufsteuerung konfigurieren, wird für jeden Pool, der nicht mit einer statischen Route auf der Poolebene konfiguriert ist, die globale statische Route verwendet.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>So konfigurieren Sie eine statische Route für die Remoteanrufsteuerung

1.  Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder einer rollenbasierten zugriffssteuerungsrolle (Role-Based Access Control, RBAC) installiert ist, der Sie das Cmdlet **New-CsStaticRoute** zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie eine der folgenden Aktionen aus, um eine statische Route zu erstellen und Sie in der Variablen $TLSRoute oder $TCPRoute zu speichern:
    
    <div class="">
    

    > [!TIP]  
    > Wenn Sie untergeordnete Domänen einer Domäne abgleichen möchten, können Sie im MatchUri-Parameter einen Platzhalterwert angeben. Beispiel: <STRONG>*. contoso.net</STRONG>. Dieser Wert entspricht jeder Domäne, die mit dem Suffix <STRONG>contoso.net</STRONG>endet.

    
    </div>
    
      - Bei einer TLS-Verbindung (Transport Layer Security) geben Sie Folgendes an der Eingabeaufforderung ein:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Beispiel:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Wenn UseDefaultCertificate auf "false" festgelegt ist, müssen Sie TLSCertIssuer-und TLSCertSerialNumber-Parameter angeben. Diese Parameter geben den Namen der Zertifizierungsstelle an, die das in der statischen Route verwendete Zertifikat ausgestellt hat, und die Seriennummer des jeweiligen TLS-Zertifikats. Details zu diesen Parametern finden Sie unter Hilfe zur lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung Folgendes eingeben:
        
            Get-Help New-CsStaticRoute -Full
    
      - Bei einer TCP-Verbindung (Transmission Control Protocol) geben Sie Folgendes an der Eingabeaufforderung ein:
        
        <div class="">
        

        > [!NOTE]  
        > Wenn Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) angeben, müssen Sie zuerst einen DNS-Eintrag (Domain Name System) konfigurieren.

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Beispiel:
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Im folgenden finden Sie die Standardwerte für optionale Parameter für statische Routen:
        
          - Enabled = wahr
        
          - MatchOnlyPhoneUri = falsch
        
          - ReplaceHostInRequestUri = falsch
        
        Wir empfehlen dringend, diese Standardwerte nicht zu ändern. Wenn Sie jedoch einen dieser Parameter ändern müssen, lesen Sie Hilfe zur lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung Folgendes eingeben:
        
            Get-Help New-CsStaticRoute -Full

4.  Führen Sie eine der folgenden Aktionen aus, um eine neu erstellte statische Route im zentralen Verwaltungsspeicher beizubehalten:
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

