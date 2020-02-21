---
title: 'Lync Server 2013: Konfigurieren der passiven Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c2c94bde12e6b8b77060a82f1990b673421de9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Konfigurieren lync Server 2013 passiven Authentifizierung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-11_

Im folgenden Abschnitt wird beschrieben, wie Sie lync Server 2013 mit kumulativen Updates konfigurieren: Juli 2013 zur Unterstützung der passiven Authentifizierung. Sobald aktiviert, müssen lync-Benutzer, die für die zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle Smartcard sowie eine gültige PIN verwenden, um sich mit dem lync 2013 mit kumulativen Updates anzumelden: July 2013 Client.

<div class="">


> [!NOTE]  
> Es wird dringend empfohlen, dass Kunden die passive Authentifizierung für Registrar und Webdienste auf Dienstebene aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen-und Webdienste auf globaler Ebene aktiviert ist, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit dem lync 2013 mit kumulierten Updates anmelden: Clientdesktop Client für Juli 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Webdienstkonfiguration für Directors, Enterprise-Pools und Standard Edition-Server erstellen, die für die passive Authentifizierung aktiviert werden.

**So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration**

1.  Melden Sie sich bei Ihrem lync Server 2013 mit kumulierten Updates an: July 2013-Front-End-Server mit einem lync-Administratorkonto.

2.  Starten Sie die lync Server 2013 Management-Shell.

3.  Erstellen Sie über die Befehlszeile lync Server-Verwaltungsshell eine neue Webdienstkonfiguration für jeden Director, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > Der Wert für den "wsfedpassivemetadatauri"-FQDN ist der Verbunddienst Name des AD FS 2.0 Servers. Den Wert des Verbunddienst namens finden Sie in der AD FS 2.0-Verwaltungskonsole, indem Sie im Navigationsbereich mit der rechten Maustaste auf <STRONG>Dienst</STRONG> klicken und dann <STRONG>Eigenschaften von Verbunddienst bearbeiten</STRONG>auswählen.

    
    </div>

4.  Stellen Sie sicher, dass die Werte UseWsFedPassiveAuth und "wsfedpassivemetadatauri" ordnungsgemäß festgelegt wurden, indem Sie den folgenden Befehl ausführen:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Für Clients ist die passive Authentifizierung die am wenigsten bevorzugte Authentifizierungsmethode für die WebTICKET-Authentifizierung. Für alle Directors, Enterprise-Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, müssen alle anderen Authentifizierungstypen in lync Webdienste deaktiviert werden, indem Sie den folgenden Befehl ausführen:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Stellen Sie sicher, dass alle anderen Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Proxy Konfiguration

Wenn die Zertifikatauthentifizierung für lync Webdienste deaktiviert ist, verwendet der lync-Client einen abzüglich bevorzugten Authentifizierungstyp wie Kerberos oder NTLM, um sich beim Registrierungsstellendienst zu authentifizieren. Die Zertifikatauthentifizierung ist weiterhin erforderlich, damit der lync-Client ein WebTICKET abrufen kann, jedoch müssen Kerberos und NTLM für den Registrierungsstellendienst deaktiviert werden.

In den folgenden Schritten wird beschrieben, wie Sie eine benutzerdefinierte Proxykonfiguration für Edge-Pools, Enterprise-Pools und Standard Edition-Server erstellen, die für die passive Authentifizierung aktiviert werden.

**So erstellen Sie eine benutzerdefinierte Proxykonfiguration**

1.  Erstellen Sie über die Befehlszeile lync Server-Verwaltungsshell eine neue Proxykonfiguration für jeden lync Server 2013 mit kumulierten Updates: 2013. Juli-Edge-Pool, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen: folgenden Befehle aus:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Stellen Sie sicher, dass alle anderen Proxy Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

