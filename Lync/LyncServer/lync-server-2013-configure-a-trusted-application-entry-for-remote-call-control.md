---
title: 'Lync Server 2013: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung'
TOCTitle: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558636(v=OCS.15)
ms:contentKeyID: 49293675
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-11-02_

Das SIP/CSTA-Gateway muss als vertrauenswürdige Anwendung konfiguriert sein, damit Lync Server eine statische Route zur Weiterleitung von Anrufen an das Gateway anwenden kann.


> [!IMPORTANT]
> Wenn Sie Benutzer von einer vorherigen Version der Lync Server-Bereitstellung migrieren, müssen Sie vor der Ausführung der Verfahren in diesem Thema alle vorhandenen Einträge für vertrauenswürdige Anwendungen (zuvor als autorisierte Hosteinträge bezeichnet) entfernen, die für das SIP/CSTA-Gateway erstellt wurden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in Lync Server 2013 (optional)</A>.



## So konfigurieren Sie Einträge für vertrauenswürdige Anwendungen für das SIP/CSTA-Gateway

1.  Melden Sie sich bei einem Computer mit installierter Lync Server-Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder unter Verwendung einer rollenbasierten Zugriffssteuerungsrolle an, der Sie das Cmdlet **New-CsTrustedApplicationPool** zugewiesen haben.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

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

## Siehe auch

#### Aufgaben

[Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

