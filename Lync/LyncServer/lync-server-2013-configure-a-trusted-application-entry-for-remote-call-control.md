---
title: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung
description: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5341dc220853670cf000f5b0d5dc379c02fa51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570071"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-11-02_

Das SIP/CSTA-Gateway muss als vertrauenswürdige Anwendung konfiguriert sein, damit lync Server eine statische Route für die Weiterleitung von Anrufen an das Gateway anwenden können.

<div>


> [!IMPORTANT]
> Wenn Sie Benutzer aus einer früheren Version von lync Server-Bereitstellung migrieren, müssen Sie unbedingt alle vorhandenen Einträge für vertrauenswürdige Anwendungen (zuvor als autorisierte Hosteinträge bezeichnet) entfernt haben, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie die Verfahren in diesem Thema befolgen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.<BR>Wenn Sie die Bereitstellung einer neuen Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) planen, müssen Sie überprüfen, ob die <STRONG>Einschränkung der Dienstnutzung auf ausgewählte IP-Adressen</STRONG> für vorhandene Vertrauenswürdige Anwendungen und Pools festgelegt werden soll, wenn Sie denselben TCP-Port für die neue vertrauenswürdige Anwendung verwenden möchten.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>So konfigurieren Sie Einträge für vertrauenswürdige Anwendungen für das SIP/CSTA-Gateway

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet **New-CsTrustedApplicationPool** zugewiesen haben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Gehen Sie zum Erstellen eines Eintrags für eine vertrauenswürdige Anwendung folgendermaßen vor:
    
      - Geben Sie für eine TLS-Verbindung (Transport Layer Security) den folgenden Befehl an der Eingabeaufforderung ein:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Beispiel:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Geben Sie für eine TCP-Verbindung (Transmission Control Protocol) den folgenden Befehl an der Eingabeaufforderung ein:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Beispiel:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Gehen Sie folgendermaßen vor, um die vertrauenswürdige Anwendung zu einem Pool hinzuzufügen:
    
      - Geben Sie für eine TLS-Verbindung den folgenden Befehl an der Eingabeaufforderung ein:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Beispiel:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Geben Sie für eine TCP-Verbindung den folgenden Befehl an der Eingabeaufforderung ein:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Beispiel:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Zur Implementierung der veröffentlichten Topologieänderungen geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

