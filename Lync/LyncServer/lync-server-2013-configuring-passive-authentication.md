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
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="3812e-102">Konfigurieren der passiven Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3812e-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3812e-103">_**Letztes Änderungsdatum des Themas:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="3812e-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="3812e-104">Im folgenden Abschnitt wird beschrieben, wie Sie lync Server 2013 mit kumulativen Updates konfigurieren: Juli 2013, um die passive Authentifizierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3812e-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="3812e-105">Nach der Aktivierung müssen lync-Benutzer, die für die zweistufige Authentifizierung aktiviert sind, eine physische oder virtuelle Smartcard sowie eine gültige PIN verwenden, um sich mit dem lync 2013 mit kumulativen Updates zu anmelden: Juli 2013-Client.</span><span class="sxs-lookup"><span data-stu-id="3812e-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="3812e-106">Kunden wird dringend empfohlen, die passive Authentifizierung für Registrierungsstellen und Webdienste auf Dienstebene zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3812e-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="3812e-107">Wenn die passive Authentifizierung für Registrierungsstellen und Webdienste auf globaler Ebene aktiviert ist, führt dies wahrscheinlich zu organisationsweiten Authentifizierungsfehlern für Benutzer, die sich nicht mit der lync-2013 mit kumulativen Updates anmelden: Juli 2013 Client-Desktop Client.</span><span class="sxs-lookup"><span data-stu-id="3812e-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="3812e-108">Webdienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3812e-108">Web Service Configuration</span></span>

<span data-ttu-id="3812e-109">In den folgenden Schritten wird die Erstellung einer angepassten Webdienstkonfiguration für Directorserver, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3812e-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="3812e-110">**So erstellen Sie eine benutzerdefinierte Webdienstkonfiguration**</span><span class="sxs-lookup"><span data-stu-id="3812e-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="3812e-111">Melden Sie sich bei Ihrem lync Server 2013 mit kumulativen Updates an: Juli 2013-Front-End-Server mit einem lync-Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="3812e-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="3812e-112">Starten Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="3812e-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="3812e-113">Erstellen Sie über die Befehlszeile der lync Server-Verwaltungsshell eine neue Webdienstkonfiguration für jeden Director-, Enterprise-Pool-und Standard Edition-Server, der für die passive Authentifizierung aktiviert ist, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="3812e-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="3812e-p103">Der Wert für den vollqualifizierten Domänennamen in „WsFedPassiveMetadataUri“ ist der Name des Partnerverbunddiensts Ihres AD FS 2.0-Servers. Sie können den Wert des Namens des Partnerverbunddiensts in der AD FS 2.0-Verwaltungskonsole abrufen, indem Sie im Navigationsbereich auf <STRONG>Dienst</STRONG> klicken und dann <STRONG>Eigenschaften des Verbunddiensts bearbeiten</STRONG> auswählen.</span><span class="sxs-lookup"><span data-stu-id="3812e-p103">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="3812e-116">Überprüfen Sie, ob die Werte von „UseWsFedPassiveAuth“ und „WsFedPassiveMetadataUri“ richtig festgelegt wurden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="3812e-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="3812e-117">Für Clients stellt die passive Authentifizierung die am wenigsten vorzuziehende Authentifizierungsmethode für die Authentifizierung mithilfe von Webtickets dar.</span><span class="sxs-lookup"><span data-stu-id="3812e-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="3812e-118">Für alle Directors, Enterprise-Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, müssen alle anderen Authentifizierungstypen in lync-Webdiensten deaktiviert werden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="3812e-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="3812e-119">Überprüfen Sie, ob alle anderen Authentifizierungstypen erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="3812e-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="3812e-120">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="3812e-120">Proxy Configuration</span></span>

<span data-ttu-id="3812e-121">Wenn die Zertifikatauthentifizierung für lync-Webdienste deaktiviert ist, verwendet der lync-Client einen abzüglich bevorzugten Authentifizierungstyp wie Kerberos oder NTLM, um sich beim Registrierungsstellendienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="3812e-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="3812e-122">Die Zertifikatauthentifizierung wird weiterhin benötigt, um dem lync-Client das Abrufen eines webtickets zu ermöglichen, aber Kerberos und NTLM müssen für den Registrierungsdienst deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="3812e-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="3812e-123">In den folgenden Schritten wird die Erstellung einer angepassten Proxykonfiguration für Edge Pools, Enterprise Pools und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden sollen, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3812e-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="3812e-124">**So erstellen Sie eine benutzerdefinierte Proxykonfiguration**</span><span class="sxs-lookup"><span data-stu-id="3812e-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="3812e-125">Erstellen Sie über die Befehlszeile der lync Server-Verwaltungsshell eine neue Proxykonfiguration für jeden lync Server 2013 mit kumulativen Updates: Juli 2013 Edge-Pool, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="3812e-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="3812e-126">Überprüfen Sie, ob alle anderen Proxyauthentifizierungsarten erfolgreich deaktiviert wurden, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="3812e-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

