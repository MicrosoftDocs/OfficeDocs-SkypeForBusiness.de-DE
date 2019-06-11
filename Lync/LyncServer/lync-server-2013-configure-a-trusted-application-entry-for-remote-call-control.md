---
title: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-11-02_

Das SIP/CSTA-Gateway muss als vertrauenswürdige Anwendung konfiguriert sein, damit lync Server eine statische Route zum Weiterleiten von Anrufen an das Gateway anwenden kann.

<div>


> [!IMPORTANT]
> Wenn Sie Benutzer aus einer früheren Version der lync Server-Bereitstellung migrieren, müssen Sie sicherstellen, dass Sie alle vorhandenen Einträge für vertrauenswürdige Anwendungen (zuvor als autorisierte Hosteinträge bezeichnet) entfernt haben, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie die Verfahren in Dieses Thema. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.<BR>Wenn Sie beabsichtigen, eine neue Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) bereitzustellen, müssen Sie sicherstellen, dass die <STRONG>Beschränkung der Dienstnutzung auf ausgewählte IP-Adressen</STRONG> für vorhandene Vertrauenswürdige Anwendungen und Pools festgelegt werden soll, wenn Sie dasselbe verwenden möchten. TCP-Port für die neue vertrauenswürdige Anwendung.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>So konfigurieren Sie einen Eintrag für vertrauenswürdige Anwendungen für das SIP/CSTA-Gateway

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder einer rollenbasierten zugriffssteuerungsrolle (Role-Based Access Control, RBAC) installiert ist, der Sie das Cmdlet **New-CsTrustedApplicationPool** zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie zum Erstellen eines vertrauenswürdigen Anwendungseintrags eine der folgenden Aktionen aus:
    
      - Bei einer TLS-Verbindung (Transport Layer Security) geben Sie Folgendes an der Eingabeaufforderung ein:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Beispiel:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Bei einer TCP-Verbindung (Transmission Control Protocol) geben Sie Folgendes an der Eingabeaufforderung ein:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Beispiel:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Führen Sie eine der folgenden Aktionen aus, um dem Pool die vertrauenswürdige Anwendung hinzuzufügen:
    
      - Geben Sie bei einer TLS-Verbindung Folgendes an der Eingabeaufforderung ein:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Beispiel:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Geben Sie bei einer TCP-Verbindung Folgendes an der Eingabeaufforderung ein:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Beispiel:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Geben Sie an der Eingabeaufforderung Folgendes ein, um die veröffentlichten Änderungen zu implementieren, die Sie an der Topologie vorgenommen haben:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

