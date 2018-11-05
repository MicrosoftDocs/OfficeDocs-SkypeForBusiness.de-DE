---
title: 'Lync Server 2013: Konfigurieren einer statischen Route für die Remoteanrufsteuerung'
TOCTitle: Konfigurieren einer statischen Route für die Remoteanrufsteuerung
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615051(v=OCS.15)
ms:contentKeyID: 49295934
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Für die Remoteanrufsteuerung muss jeder Lync Server-Pool mit einem Pfad von diesem Pool zu dem SIP/CSTA-Gateway konfiguriert sein, das mit der Nebenstellenanlage verbunden ist. Dabei muss jeder Pool über eine statische Route für jedes Gateway verfügen, über das der Pool SIP-Anrufsteuerungsnachrichten weiterleitet, die Anrufen bei der Nebenstellenanlage zugeordnet sind. Wenn Sie eine globale statische Route für die Anrufsteuerung konfigurieren, verwendet jeder Pool, für den nicht auf Poolebene eine statische Route konfiguriert wurde, diese globale statische Route.

## So konfigurieren Sie eine statische Route für die Remoteanrufsteuerung

1.  Melden Sie sich bei einem Computer mit installierter Lync Server-Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder unter Verwendung einer rollenbasierten Zugriffssteuerungsrolle an, der Sie das Cmdlet **New-CsStaticRoute** zugewiesen haben.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie einen der folgenden Schritte aus, um eine statische Route zu erstellen und in die Variable "$TLSRoute" oder "$TCPRoute" einzufügen:
    

    > [!TIP]
    > Zum Abgleich von untergeordneten Domänen einer Domäne können Sie im Parameter "MatchUri" einen Platzhalterwert angeben. Beispiel: <STRONG>*.contoso.net</STRONG> . Dieser Wert gilt für alle Domänen, die auf das Suffix <STRONG>contoso.net</STRONG> enden.

    
      - Geben Sie für eine TLS-Verbindung (Transport Layer Security) den folgenden Befehl an der Eingabeaufforderung ein:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Beispiel:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Wenn "UseDefaultCertificate" auf "False" gesetzt ist, müssen Sie die Parameter "TLSCertIssuer" und "TLSCertSerialNumber" angeben. Diese Parameter geben den Namen der Zertifizierungsstelle, die das in der statischen Route verwendete Zertifikat ausgestellt hat, sowie die Seriennummer dieses TLS-Zertifikats an. Ausführliche Informationen zu diesen Parametern finden Sie in der Hilfe zur Lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung diese Zeichenfolge eingeben:
        
            Get-Help New-CsStaticRoute -Full
    
      - Geben Sie für eine TCP-Verbindung (Transmission Control Protocol) den folgenden Befehl an der Eingabeaufforderung ein:
        

        > [!NOTE]
        > Wenn Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) angeben, müssen Sie zuerst einen DNS-A-Eintrag (Domain Name System) konfigurieren.

        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Beispiel:
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Die optionalen Parameter für statische Routen weisen folgende Standardwerte auf:
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Es wird dringend empfohlen, diese Standardwerte nicht zu ändern. Wenn Sie jedoch einen dieser Parameter ändern müssen, finden Sie weitere Informationen in der Hilfe zur Lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung Folgendes eingeben:
        
            Get-Help New-CsStaticRoute -Full

4.  Führen Sie einen der folgenden Befehle aus, um eine neu erstellte statische Route dauerhaft im zentralen Verwaltungsspeicher zu speichern:
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}

       &nbsp;
    
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}

## Siehe auch

#### Aufgaben

[Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

