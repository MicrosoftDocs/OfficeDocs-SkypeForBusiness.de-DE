---
title: Konfigurieren von Unified Messaging auf Microsoft Exchange
TOCTitle: Konfigurieren von Unified Messaging auf Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398129(v=OCS.15)
ms:contentKeyID: 49293072
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Unified Messaging auf Microsoft Exchange

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Thema wird beschrieben, wie Sie Exchange Unified Messaging (UM) auf einem Microsoft Exchange Server für die Verwendung mit Enterprise-VoIP konfigurieren.


> [!NOTE]
> Die Cmdlet-Beispiele in diesem Thema zeigen die Syntax für die Exchange 2007-Version der Exchange-Verwaltungsshell. Wenn Sie Exchange 2010 oder Exchange 2013 ausführen, finden Sie weitere Informationen in der entsprechenden Dokumentation (siehe Verweis).



## So konfigurieren Sie einen Server mit Exchange Server UM

1.  Erstellen Sie einen Satz mit UM-SIP-URI-Wählplänen für jedes Enterprise-VoIP-Standortprofil. Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, erstellen Sie einen neuen Wählplan mit der Sicherheitseinstellung **Secured (bevorzugt)**.
    

    > [!WARNING]
    > Wenn Sie die Sicherheit auf <STRONG>SIPSecured</STRONG> festlegen, führt dies zu einer ausschließlichen Verschlüsselung des SIP-Datenverkehrs (diese Einstellung wurde bisher empfohlen). Beachten Sie, dass diese Sicherheitseinstellung für einen Wählplan nicht ausreicht, wenn dieser zur Erzwingung einer Verschlüsselung konfiguriert wurde, da der Pool in diesem Fall eine Verschlüsselung des SIP- und des RTP-Datenverkehrs anfordert. Wenn die Sicherheitsstufen des Wählplans und Pools nicht kompatibel sind, können keine Exchange UM-Aufrufe vom Front-End-Pool durchgeführt werden, und es wird ein Fehler mit dem Hinweis "Inkompatible Sicherheitseinstellung" ausgegeben.

    
    Wenn Sie die Exchange-Verwaltungsshell verwenden, geben Sie Folgendes ein:
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zur Vorgehensweise für Office Communications Server 2007 finden Sie auf der Seite "Erstellen eines SIP-URI-Wählplans für Unified Messaging" unter [http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x407) und auf der Seite "New-UMDialplan: Exchange 2007-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "Erstellen von UM-Wähleinstellungen" unter [http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x407) und "New-UMDialplan: Exchange 2010-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2013 finden Sie auf der Seite "Unified Messaging" unter [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x407).
    

    > [!NOTE]
    > Ob Sie die Sicherheitsstufe <STRONG>SIPSecured</STRONG> oder <STRONG>Secured</STRONG> auswählen, hängt davon ab, ob SRTP (Secure Real-time Transport Protocol) für die Medienverschlüsselung aktiviert oder deaktiviert ist. Für die Lync Server 2010-Integration in Exchange UM sollte die Einstellung mit der Verschlüsselungsstufe in der Lync Server-Medienkonfiguration übereinstimmen. Die Lync Server-Medienkonfiguration kann durch Ausführen des Cmdlets <STRONG>Get-CsMediaConfiguration</STRONG> angezeigt werden. Ausführliche Informationen finden Sie unter "Get-CsMediaConfiguration" in der Lync Server-Verwaltungsshell-Dokumentation.<BR>Ausführliche Informationen zur Auswahl der geeigneten VoIP-Sicherheitseinstellungen finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013</A>.



2.  Führen Sie das folgende Cmdlet aus, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die einzelnen UM-Wähleinstellungen abzurufen:
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zur Vorgehensweise für Exchange 2007 finden Sie auf der Seite "Get-UMDialplan: Exchange 2007-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268678\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268678%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "Get-UMDialplan: Exchange 2010-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2013 finden Sie auf der Seite "Unified Messaging" unter [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x407).

3.  Notieren Sie die Namen aller UM-Wählpläne. Je nach Version von Exchange Server benötigen Sie später den FQDN jedes Wählplans als Name für den zugehörigen Wählplan in Lync Server, damit die Wählplannamen übereinstimmen.
    

    > [!NOTE]
    > Die Namen der Lync Server-Wähleinstellungen müssen nur dann den Namen der UM-Wähleinstellungen entsprechen, wenn die UM-Wähleinstellungen auf einer Exchange-Version <EM>vor</EM> Exchange&nbsp;2010&nbsp;SP1 ausgeführt werden.



4.  Fügen Sie die Wähleinstellungen folgendermaßen dem Server hinzu, auf dem Exchange UM ausgeführt wird:
    
      - Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, können Sie die Wähleinstellungen aus der Eigenschaftenseite des Servers hinzufügen. Genaue Anweisungen finden Sie in der Exchange Server-Produktdokumentation.
        
        Informationen zur Vorgehensweise für Exchange 2007 finden Sie auf der Seite "Hinzufügen eines Unified Messaging-Servers zu einem Wählplan" unter [http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x407).
        
        Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "Anzeigen oder Konfigurieren der Eigenschaften eines UM-Servers" unter [http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x407).
        
        Informationen zur Vorgehensweise für Exchange 2013 finden Sie auf der Seite "Unified Messaging" unter [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x407).
    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, führen Sie für jeden Exchange UM-Server den folgenden Befehl aus:
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    

    > [!NOTE]
    > Vergewissern Sie sich vor dem Ausführen des folgenden Schritts, dass für alle Enterprise-VoIP-Benutzer ein Exchange Server-Postfach konfiguriert wurde.<BR>Informationen zur Vorgehensweise für Exchange 2007 finden Sie in der Exchange Server 2007-TechNet-Bibliothek unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0x407</A>.<BR>Informationen zur Vorgehensweise für Exchange 2010 finden Sie in der Exchange Server 2010-TechNet-Bibliothek unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0x407</A>.<BR>Wenn Sie eine Postfachrichtlinie für jeden in Schritt&nbsp;1 erstellten Satz mit Wähleinstellungen festlegen, verwenden Sie entweder die Standardrichtlinie oder eine von Ihnen selbst erstellte Richtlinie.



5.  Navigieren Sie zu "\<*Installationsverzeichnis von Exchange*\>\\Scripts", und geben Sie Folgendes ein, wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird:
    
        exchucutil.ps1
    
    Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    Hierbei gibt *FQDN der Gesamtstruktur* die Gesamtstruktur an, in der Lync Server bereitgestellt wird.
    
    Falls Sie über einen oder mehrere Sätze mit UM-Wähleinstellungen verfügen, die mehreren IP-Gateways zugeordnet sind, fahren Sie mit Schritt 6 fort. Falls Ihre Wähleinstellungen jeweils nur einem IP-Gateway zugeordnet sind, überspringen Sie Schritt 6.
    

    > [!IMPORTANT]
    > Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie "exchucutil.ps1" ausgeführt haben. Andernfalls erkennt Lync Server Unified Messaging nicht in der Topologie.



6.  Deaktivieren Sie über die Exchange-Verwaltungsshell oder -Verwaltungskonsole ausgehende Anrufe für alle IP-Gateways, mit Ausnahme des Ihren Wähleinstellungen zugeordneten IP-Gateways.
    

    > [!NOTE]
    > Dieser Schritt ist notwendig, damit ausgehende Anrufe des Exchange Server&nbsp;Unified Messaging-Servers an externe Benutzer (z.&nbsp;B. in Szenarien mit Wiedergabe über Telefon) die Unternehmensfirewall zuverlässig passieren.

    

    > [!IMPORTANT]
    > Wählen Sie als UM-IP-Gateway für ausgehende Anrufe das Gerät aus, das voraussichtlich den meisten Datenverkehr verarbeitet. Leiten Sie den ausgehenden Datenverkehr nicht über ein IP-Gateway, das mit einem Pool von Lync Server-Director-Servern verbunden ist. Vermeiden Sie auch Pools an einem anderen zentralen Standort oder einem Zweigstellenstandort. Verhindern Sie mithilfe einer der folgenden Methoden, dass ausgehende Anrufe über ein IP-Gateway geleitet werden:

    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, deaktivieren Sie die einzelnen IP-Gateways mit folgendem Befehl:
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Informationen zur Vorgehensweise für Exchange 2007 finden Sie auf der Seite "Set-UMIPGateway: Exchange 2007-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0x407).
        
        Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "Set-UMIPGateway: Exchange 2010-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0x407).
    
      - Wenn Sie die Exchange-Verwaltungskonsole verwenden, deaktivieren Sie das Kontrollkästchen **Ausgehende Anrufe über dieses IP-Gateway zulassen**.
    

    > [!IMPORTANT]
    > Falls Ihre UM-SIP-URI-Wähleinstellungen nur einem einzigen IP-Gateway zugeordnet sind, dürfen Sie ausgehende Anrufe über dieses Gateway nicht sperren.



7.  Erstellen Sie eine automatische UM-Telefonzentrale für jeden Satz mit Lync Server-Wähleinstellungen.
    

    > [!IMPORTANT]
    > Verwenden Sie im Namen der automatischen Telefonzentrale keine Leerzeichen.

    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zur Vorgehensweise für Exchange 2007 finden Sie auf der Seite "New-UMAutoAttendant: Exchange 2007-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "New-UMAutoAttendant: Exchange 2010-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0x407).
    
    Der folgende Schritt sollte für jeden Benutzer ausgeführt werden, nachdem Sie Lync Server-Benutzer für Enterprise-VoIP aktiviert haben und ihre SIP-URIs kennen.

8.  Ordnen Sie den UM-Wähleinstellungen Exchange UM-Benutzer zu (von denen jeder mit einem Exchange-Postfach konfiguriert sein sollte), und erstellen Sie einen SIP-URI für jeden Benutzer.
    

    > [!NOTE]
    > Beim Wert von <STRONG>SIPResourceIdentifier</STRONG> im folgenden Beispiel muss es sich um die SIP-Adresse des Lync Server-Benutzers handeln.

    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zur Vorgehensweise für Exchange 2007 finden Sie auf der Seite "Enable-UMMailbox: Exchange 2007-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0x407).
    
      - Informationen zur Vorgehensweise für Exchange 2010 finden Sie auf der Seite "Enable-UMMailbox: Exchange 2010-Hilfe" unter [http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0x407).

