---
title: 'Lync Server 2013: Konfigurieren einer statischen Route für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d773658b17d846409e303c23204f86ea1f0fce77
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507672"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-22_

Für die Remote Anrufsteuerung muss jeder lync Server-Pool mit einem Pfad vom Pool zum SIP/CSTA-Gateway konfiguriert werden, das eine Verbindung mit der PBX-Anlage (Private Branch Exchange, Nebenstellenanlage) herstellt. Dieser Pfad erfordert, dass jeder Pool über eine statische Route für jedes Gateway verfügt, für das der Pool SIP-Anrufsteuerungsnachrichten für Anrufe an die Nebenstellenanlage proxyt. Wenn Sie eine globale statische Route für die Remoteanrufsteuerung konfigurieren, wird für jeden Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>So konfigurieren Sie eine statische Route für die Remoteanrufsteuerung

1.  Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet **New-CsStaticRoute** zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie einen der folgenden Schritte aus, um eine statische Route zu erstellen und Sie in der Variablen $TLSRoute oder $TCPRoute zu platzieren:
    
    <div class="">
    

    > [!TIP]  
    > Um untergeordnete Domänen einer Domäne abzugleichen, können Sie einen Platzhalterwert im Parameter MatchUri angeben. Beispiel: <STRONG>*. contoso.net</STRONG>. Dieser Wert entspricht einer Domäne, die mit dem Suffix <STRONG>contoso.net</STRONG>endet.

    
    </div>
    
      - Geben Sie für eine TLS-Verbindung (Transport Layer Security) den folgenden Befehl an der Eingabeaufforderung ein:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Beispiel:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Wenn UseDefaultCertificate auf false festgelegt ist, müssen Sie TLSCertIssuer-und TLSCertSerialNumber-Parameter angeben. Diese Parameter geben den Namen der Zertifizierungsstelle an, die das in der statischen Route verwendete Zertifikat ausgestellt hat, sowie die Seriennummer des jeweiligen TLS-Zertifikats. Ausführliche Informationen zu diesen Parametern finden Sie unter lync Server-Verwaltungsshell Hilfe, indem Sie an der Eingabeaufforderung Folgendes eingeben:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Geben Sie für eine TCP-Verbindung (Transmission Control Protocol) den folgenden Befehl an der Eingabeaufforderung ein:
        
        <div class="">
        

        > [!NOTE]  
        > Wenn Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) angeben, müssen Sie zuerst einen Domain Name System (DNS) einen Datensatz konfigurieren.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Zum Beispiel:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Im folgenden sind die Standardwerte für optionale Parameter für statische Routen angegeben:
        
          - Enabled = true
        
          - MatchOnlyPhoneUri = false
        
          - ReplaceHostInRequestUri = false
        
        Es wird dringend empfohlen, diese Standardwerte nicht zu ändern. Wenn Sie jedoch einen dieser Parameter ändern müssen, lesen Sie lync Server-Verwaltungsshell Hilfe, indem Sie an der Eingabeaufforderung Folgendes eingeben:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Führen Sie nach Bedarf eine der folgenden Aktionen aus, um eine neu erstellte statische Route im zentralen Verwaltungsspeicher beizubehalten:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

