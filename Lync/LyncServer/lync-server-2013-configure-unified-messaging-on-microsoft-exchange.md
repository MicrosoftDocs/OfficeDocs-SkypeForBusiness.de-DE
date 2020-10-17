---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging für Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b39c10a3fb590acc99771663f5f6e23e3c3095e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520222"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

In diesem Thema wird beschrieben, wie Sie Exchange Unified Messaging (um) auf einem Exchange Server für die Verwendung mit Enterprise-VoIP konfigurieren.

<div>


> [!NOTE]  
> Die Cmdlet-Beispiele in diesem Thema bieten Syntax für die Exchange 2007 Version von Exchange-Verwaltungsshell. Wenn Sie Exchange 2010 oder Exchange 2013 betreiben, lesen Sie die entsprechende Dokumentation, auf die verwiesen wird.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>So konfigurieren Sie einen Server mit Exchange Server UM

1.  Erstellen Sie einen Satz mit UM-SIP-URI-Wähleinstellungen (Session Initiation Protocol, SIP; Uniform Resource Identifier, URI) für jedes Enterprise-VoIP-Standortprofil. Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, erstellen Sie neue Wähleinstellungen mit der Sicherheitseinstellung **Secured (bevorzugt)**.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie den Wert für die Sicherheitseinstellung auf <STRONG>SIP-gesichert</STRONG> festlegen, um nur die Verschlüsselung für den SIP-Datenverkehr zu erzwingen (wie zuvor empfohlen), beachten Sie, dass diese Sicherheitseinstellung für einen Wählplan unzureichend ist, wenn der Front-End-Pool für die Verschlüsselung konfiguriert ist, was bedeutet, dass der Pool für SIP-und RTP-Datenverkehr verschlüsselt werden muss. Wenn die Einstellungen für den Wählplan und die Pool Sicherheit nicht kompatibel sind, tritt bei allen Aufrufen von Exchange um aus dem Front-End-Pool ein Fehler auf, der darauf hinweist, dass eine "inkompatible Sicherheitseinstellung" vorliegt.

    
    </div>
    
    Wenn Sie die Exchange-Verwaltungsshell verwenden, geben Sie Folgendes ein:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Office Communications Server 2007 finden Sie unter "Erstellen eines SIP-URI-Wählplans für Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) und "New-UMDialplan: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .
    
      - Informationen zum Exchange 2010 finden Sie unter "Erstellen eines um-Wählplans" unter [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) und "New-UMDialplan: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .
    
      - Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
    <div>
    

    > [!NOTE]  
    > Ob Sie die Sicherheitsstufe <STRONG>SIPSecured</STRONG> oder <STRONG>Secured</STRONG> auswählen, hängt davon ab, ob SRTP (Secure Real-time Transport Protocol) für die Medienverschlüsselung aktiviert oder deaktiviert ist. Für die lync Server 2010 Integration in Exchange um sollte dies der Verschlüsselungsstufe in der lync Server Medienkonfiguration entsprechen. Die lync Server Medienkonfiguration kann durch Ausführen des Cmdlets <STRONG>Get-CsMediaConfiguration</STRONG> angezeigt werden. Ausführliche Informationen finden Sie unter Get-CsMediaConfiguration in der lync Server-Verwaltungsshell-Dokumentation.<BR>Ausführliche Informationen zum Auswählen der geeigneten VoIP-Sicherheitseinstellung finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment Process for Integration on-premises Unified Messaging and lync Server 2013</A>.

    
    </div>

2.  Führen Sie das folgende Cmdlet aus, um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die einzelnen UM-Wähleinstellungen abzurufen:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Exchange 2007 finden Sie unter "Get-UMDialplan: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .
    
      - Informationen zu Exchange 2010 finden Sie unter "Get-UMDialplan: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .
    
      - Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .

3.  Notieren Sie die Namen aller UM-Wählpläne. Je nach ihrer Version von Exchange Server müssen Sie möglicherweise den FQDN der einzelnen Wähl Plan Namen später als Namen für die entsprechenden lync Server Wähleinstellungen für die um-Wähleinstellungen verwenden, damit die Wähl Plan Namen übereinstimmen.
    
    <div>
    

    > [!NOTE]  
    > Lync Server Wähl Plan Namen müssen nur dann mit um-Wähl Plan Namen übereinstimmen, wenn die um-Wähleinstellungen auf einer <EM>früheren</EM> Exchange-Version als Exchange 2010 SP1 durchführen.

    
    </div>

4.  Fügen Sie den Wählplan dem Server mit Exchange um wie folgt hinzu:
    
      - Wenn Sie sich zur Verwendung der Exchange-Verwaltungskonsole entscheiden, können Sie die Wähleinstellungen aus der Eigenschaftenseite des Servers hinzufügen. Genaue Anweisungen finden Sie in der Exchange Server-Produktdokumentation.
        
        Informationen zum Exchange 2007 finden Sie unter "Hinzufügen eines Unified Messaging-Servers zu Wähleinstellungen" unter [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .
        
        Informationen zu Exchange 2010 finden Sie unter "anzeigen oder Konfigurieren der Eigenschaften eines um-Servers" unter [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .
        
        Informationen zu Exchange 2013 finden Sie unter "Unified Messaging" unter [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, führen Sie für jeden Exchange UM-Server den folgenden Befehl aus:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Vergewissern Sie sich vor dem Ausführen des folgenden Schritts, dass für alle Enterprise-VoIP-Benutzer ein Exchange Server-Postfach konfiguriert wurde.<BR>Informationen zu Exchange 2007 finden Sie in der Exchange Server 2007 TechNet-Bibliothek unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .<BR>Informationen zu Exchange 2010 finden Sie in der Exchange Server 2010 TechNet-Bibliothek unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .<BR>Wenn Sie eine Postfachrichtlinie für jeden in Schritt 1 erstellten Satz mit Wähleinstellungen festlegen, verwenden Sie entweder die Standardrichtlinie oder eine von Ihnen selbst erstellte Richtlinie.

    
    </div>

5.  Navigieren Sie zu \<Exchange installation directory\> \\ Skripts, und geben Sie Folgendes ein, wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird:
    ```console
    exchucutil.ps1
    ```
    Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server bereitgestellt wird.
    
    Falls Sie über einen oder mehrere Sätze mit UM-Wähleinstellungen verfügen, die mehreren IP-Gateways zugeordnet sind, fahren Sie mit Schritt 6 fort. Falls Ihre Wähleinstellungen jeweils nur einem IP-Gateway zugeordnet sind, überspringen Sie Schritt 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie "exchucutil.ps1" ausgeführt haben. Andernfalls werden von lync Server Unified Messaging in der Topologie nicht erkannt.

    
    </div>

6.  Deaktivieren Sie über die Exchange-Verwaltungsshell oder -Verwaltungskonsole ausgehende Anrufe für alle IP-Gateways, mit Ausnahme des Ihren Wähleinstellungen zugeordneten IP-Gateways.
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist erforderlich, um sicherzustellen, dass ausgehende Anrufe des Servers, der Exchange Server Unified Messaging ausführt, an externe Benutzer (beispielsweise wie bei Szenarien mit "Play-on-Phone") zuverlässig die Unternehmensfirewall durchlaufen.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Wählen Sie als UM-IP-Gateway für ausgehende Anrufe das Gerät aus, das voraussichtlich den meisten Datenverkehr verarbeitet. Lassen Sie ausgehenden Datenverkehr über ein IP-Gateway nicht zu, das eine Verbindung mit einem Pool von lync Server Directors herstellt. Vermeiden Sie auch Pools an einem anderen zentralen Standort oder einem Zweigstellenstandort. Verhindern Sie mithilfe einer der folgenden Methoden, dass ausgehende Anrufe über ein IP-Gateway geleitet werden:

    
    </div>
    
      - Wenn Sie die Exchange-Verwaltungsshell verwenden, deaktivieren Sie die einzelnen IP-Gateways mit folgendem Befehl:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Informationen zu Exchange 2007 finden Sie unter "festlegen-UMIPGateway: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .
        
        Informationen zu Exchange 2010 finden Sie unter "festlegen-UMIPGateway: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .
    
      - Wenn Sie die Exchange-Verwaltungskonsole verwenden, deaktivieren Sie das Kontrollkästchen **Ausgehende Anrufe über dieses IP-Gateway zulassen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Falls Ihre UM-SIP-URI-Wähleinstellungen nur einem einzigen IP-Gateway zugeordnet sind, dürfen Sie ausgehende Anrufe über dieses Gateway nicht sperren.

    
    </div>

7.  Erstellen Sie eine automatische UM-Telefonzentrale für jeden lync Server Wähleinstellungen.
    
    <div>
    

    > [!IMPORTANT]  
    > Verwenden Sie im Namen der automatischen Telefonzentrale keine Leerzeichen.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Ausführliche Informationen finden Sie hier:
    
      - Informationen zu Exchange 2007 finden Sie unter "New-UMAutoAttendant: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .
    
      - Informationen zu Exchange 2010 finden Sie unter "New-UMAutoAttendant: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .
    
    Der folgende Schritt sollte für jeden Benutzer ausgeführt werden, nachdem Sie lync Server Benutzer für Enterprise-VoIP aktiviert und deren SIP-URIs kennen.

8.  Ordnen Sie den UM-Wähleinstellungen Exchange UM-Benutzer zu (von denen jeder mit einem Exchange-Postfach konfiguriert sein sollte), und erstellen Sie einen SIP-URI für jeden Benutzer.
    
    <div>
    

    > [!NOTE]  
    > Das <STRONG>SIPResourceIdentifier</STRONG> im folgenden Beispiel muss die SIP-Adresse des lync Server Benutzers sein.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Weitere Informationen finden Sie unter:
    
      - Informationen zu Exchange 2007 finden Sie unter "Enable-UMMailbox: Exchange 2007 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .
    
      - Informationen zu Exchange 2010 finden Sie unter "Enable-UMMailbox: Exchange 2010 Help" unter [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

