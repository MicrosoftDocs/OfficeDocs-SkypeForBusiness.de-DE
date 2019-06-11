---
title: 'Lync Server 2013: Konfigurieren der passiven Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c85bd20222a5fa70d052b21f62d0c19c76eea46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Konfigurieren der passiven Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-11_

Im folgenden Abschnitt wird beschrieben, wie Sie lync Server 2013 mit kumulativen Updates konfigurieren: Juli 2013, um die passive Authentifizierung zu unterstützen. Nach der Aktivierung müssen lync-Benutzer, die für die zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle Smartcard sowie eine gültige PIN verwenden, um sich mit dem lync 2013 mit kumulativen Updates zu anmelden: Juli 2013-Client.

<div class="">


> [!NOTE]  
> Kunden wird dringend empfohlen, die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene zu aktivieren. Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf globaler Ebene aktiviert ist, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit der lync-2013 mit kumulativen Updates anmelden: Juli 2013 Client-Desktop Client.



</div>

<div>

## <a name="web-service-configuration"></a>Webdienstkonfiguration

In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.

**So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration**

1.  Melden Sie sich bei Ihrem lync Server 2013 mit kumulativen Updates an: Juli 2013-Front-End-Server mit einem lync-Administratorkonto.

2.  Starten Sie die lync Server 2013-Verwaltungsshell.

3.  Erstellen Sie über die Befehlszeile der lync Server-Verwaltungsshell eine neue Webdienstkonfiguration für jeden Director-, Enterprise-Pool-und Standard Edition-Server, der für die passive Authentifizierung aktiviert ist, indem Sie den folgenden Befehl ausführen:
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    <div class="">
    

    > [!WARNING]  
    > Der Wert für den vollqualifizierten Domänennamen in „WsFedPassiveMetadataUri“ ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf <STRONG>Dienst</STRONG> klicken und dann <STRONG>Eigenschaften des Verbunddiensts bearbeiten</STRONG> auswählen.

    
    </div>

4.  Überprüfen Sie, ob die Werte von „UseWsFedPassiveAuth“ und „WsFedPassiveMetadataUri“ richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar. Für alle Directors, Enterprise-Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, müssen alle anderen Authentifizierungstypen in lync-Webdiensten deaktiviert werden, indem Sie den folgenden Befehl ausführen:
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Überprüfen Sie, ob alle anderen Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

</div>

<div>

## <a name="proxy-configuration"></a>Proxykonfiguration

Wenn die Zertifikatauthentifizierung für lync-Webdienste deaktiviert ist, verwendet der lync-Client einen abzüglich bevorzugten Authentifizierungstyp wie Kerberos oder NTLM, um sich beim Registrierungsstellendienst zu authentifizieren. Die Zertifikatauthentifizierung wird weiterhin benötigt, um dem lync-Client das Abrufen eines webtickets zu ermöglichen, aber Kerberos und NTLM müssen für den Registrierungsdienst deaktiviert sein.

In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.

**So erstellen Sie eine benutzerdefinierte Proxykonfiguration**

1.  Erstellen Sie über die Befehlszeile der lync Server-Verwaltungsshell eine neue Proxykonfiguration für jeden lync Server 2013 mit kumulativen Updates: Juli 2013 Edge-Pool, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie die folgenden Befehle:
    
       ```
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

</div>

</div>

<span> </span>

</div>

</div>

</div>

