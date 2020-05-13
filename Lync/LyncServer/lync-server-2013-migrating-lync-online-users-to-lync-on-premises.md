---
title: 'Lync Server 2013: Migrieren von lync Online Benutzern lokal zu lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efc642ea326765df138f19fde4e691aa94d6b3b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="a630b-102">Migrieren von lync Online Benutzern lokal zu lync in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a630b-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a630b-103">_**Letztes Änderungsstand des Themas:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="a630b-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="a630b-104">Diese Schritte sind nur für die Migration von Benutzerkonten erforderlich, die ursprünglich für lync in lync Online aktiviert waren, bevor Sie lync lokal bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="a630b-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="a630b-105">Informationen zum Verschieben von Benutzern, die ursprünglich für lync lokal aktiviert waren und dann später in lync Online verschoben wurden, finden Sie unter <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung</A>.</span><span class="sxs-lookup"><span data-stu-id="a630b-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="a630b-106">Darüber hinaus müssen alle Benutzer, die verschoben werden, über Konten im lokalen Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="a630b-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="a630b-107">Migrieren von Benutzerkonten, die ursprünglich in lync Online für lync lokal aktiviert wurden</span><span class="sxs-lookup"><span data-stu-id="a630b-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="a630b-108">Stellen Sie zunächst sicher, dass Ihre Organisation für Hybrid konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a630b-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="a630b-109">Installieren Sie das Azure Active Directory-Synchronisierungs Tool.</span><span class="sxs-lookup"><span data-stu-id="a630b-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="a630b-110">Weitere Informationen finden Sie unter <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a630b-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="a630b-111">Um Ihren Benutzern die Verwendung von einmaligem Anmelden für lync online zu ermöglichen, installieren Sie Active Directory Verbunddienste <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .</span><span class="sxs-lookup"><span data-stu-id="a630b-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="a630b-112">Geben Sie in Ihrer lokalen Bereitstellung in lync Server-Verwaltungsshell die folgenden Cmdlets ein, um den Hostinganbieter für lync online zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a630b-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="a630b-113">Stellen Sie sicher, dass Sie auf Ihren lokalen Edgeserver die Zertifikatkette haben, die die Verbindung mit lync Online ermöglicht, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a630b-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="a630b-114">Sie können diese Kette hier herunterladen:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="a630b-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a630b-115">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="a630b-115">Certificate</span></span></th>
    <th><span data-ttu-id="a630b-116">Zertifikatspeicher</span><span class="sxs-lookup"><span data-stu-id="a630b-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a630b-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="a630b-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="a630b-118">Vertrauenswürdige Stammzertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="a630b-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a630b-119">Microsoft Internet Authority (neues Zertifizierungsstellenzertifikat)</span><span class="sxs-lookup"><span data-stu-id="a630b-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="a630b-120">Intermediate-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="a630b-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a630b-121">MSIT Machine auth Ca2 (New emissioning Ca2)</span><span class="sxs-lookup"><span data-stu-id="a630b-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="a630b-122">Intermediate-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="a630b-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="a630b-123">Aktivieren Sie in Ihrer lokalen Active Directory die betroffenen Benutzerkonten für lync lokal.</span><span class="sxs-lookup"><span data-stu-id="a630b-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="a630b-124">Sie können dies für einen einzelnen Benutzer tun, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="a630b-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="a630b-125">Sie können auch ein Skript erstellen, das Benutzernamen aus einer Datei liest und diese als Eingabe für das Cmdlet Enable-CsUser bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="a630b-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="a630b-126">Führen Sie Dirsync aus, um die lync Online Benutzer mit den aktualisierten lokalen lync-Benutzern zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="a630b-127">Aktualisieren Sie einige DNS-Einträge, um den gesamten SIP-Datenverkehr lokal an lync weiterzuleiten:</span><span class="sxs-lookup"><span data-stu-id="a630b-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="a630b-128">Aktualisieren Sie den **lyncdiscover.contoso.com** -Eintrag, sodass ein Datensatz auf den FQDN des lokalen Reverse-Proxyservers verweist.</span><span class="sxs-lookup"><span data-stu-id="a630b-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="a630b-129">Aktualisieren Sie das \*\*\* \_ SIP *. \_ TLS.contoso.com*\* -SRV-Eintrag, der in die öffentliche IP-oder VIP-Adresse des Zugriffs-Edgedienst von lync lokal aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a630b-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="a630b-130">Aktualisieren Sie das \*\*\* \_ sipfederationtls *. \_ TCP.contoso.com*\* -SRV-Eintrag, der in die öffentliche IP-oder VIP-Adresse des Zugriffs-Edgedienst von lync lokal aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a630b-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="a630b-131">Wenn Ihre Organisation Split-DNS verwendet (manchmal auch "Split-Brain-DNS" genannt), stellen Sie sicher, dass Benutzer, die Namen über die interne DNS-Zone auflösen, an den Front-End-Pool weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="a630b-132">Geben `Get-CsUser` Sie das Cmdlet ein, um einige Eigenschaften zu den Benutzern zu überprüfen, die Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="a630b-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="a630b-133">Sie möchten sicherstellen, dass das HostingProviderProxyFQDN auf festgelegt ist `"sipfed.online.lync.com"` und dass die SIP-Adressen richtig festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a630b-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="a630b-134">Migrieren Sie lync Online Benutzer lokal zu lync.</span><span class="sxs-lookup"><span data-stu-id="a630b-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="a630b-135">Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verlagern:</span><span class="sxs-lookup"><span data-stu-id="a630b-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="a630b-136">Sie können mehrere Benutzer mithilfe des Cmdlets **Get-CsUSer** mit dem Parameter – Filter migrieren, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a630b-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="a630b-137">Sie können beispielsweise alle lync Online Benutzer auswählen, indem Sie nach {Hosting Provider – EQ "sipfed.online.lync.om"} filtern.</span><span class="sxs-lookup"><span data-stu-id="a630b-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="a630b-138">Anschließend können Sie die zurückgegebenen Benutzer an das Cmdlet " **CsUSer** " weiterleiten, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a630b-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="a630b-139">Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format: *https:// \< Pool FQDN \> /HostedMigration/hostedmigrationService.svc*.</span><span class="sxs-lookup"><span data-stu-id="a630b-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="a630b-140">Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Microsoft 365-oder Office 365-organisationskonto anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a630b-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="a630b-141">So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre bereiten</span><span class="sxs-lookup"><span data-stu-id="a630b-141">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="a630b-142">Melden Sie sich bei Ihrer Microsoft 365-oder Office 365-Organisation als Administrator an.</span><span class="sxs-lookup"><span data-stu-id="a630b-142">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="a630b-143">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="a630b-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="a630b-144">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="a630b-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="a630b-145">Eine Beispiel-URL sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a630b-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="a630b-146">Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:</span><span class="sxs-lookup"><span data-stu-id="a630b-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="a630b-147">Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="a630b-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="a630b-148">Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="a630b-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="a630b-149">Die standardmäßige maximale Größe für Transaktionsprotokolldateien der "rtcxds"-Datenbank beträgt 16 GB.</span><span class="sxs-lookup"><span data-stu-id="a630b-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="a630b-150">Dies ist möglicherweise nicht groß genug, wenn Sie eine große Anzahl von Benutzern gleichzeitig verschieben, insbesondere dann, wenn die Spiegelung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a630b-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="a630b-151">Um dies zu umgehen, können Sie die Dateigröße vergrößern oder die Protokolldateien regelmäßig sichern.</span><span class="sxs-lookup"><span data-stu-id="a630b-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="a630b-152">Weitere Informationen finden Sie unter <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .</span><span class="sxs-lookup"><span data-stu-id="a630b-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="a630b-153">Dies ist ein optionaler Schritt.</span><span class="sxs-lookup"><span data-stu-id="a630b-153">This is an optional step.</span></span> <span data-ttu-id="a630b-154">Wenn Sie eine Integration mit Exchange 2013 online durchführen müssen, müssen Sie einen zusätzlichen Hosting-Anbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a630b-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="a630b-155">Ausführliche Informationen finden Sie unter [Configuring on-premises lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="a630b-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="a630b-156">Die Benutzer werden nun verschoben.</span><span class="sxs-lookup"><span data-stu-id="a630b-156">The users are now moved.</span></span> <span data-ttu-id="a630b-157">Geben Sie dieses Cmdlet ein, um zu überprüfen, ob ein Benutzer die richtigen Werte für die in der folgenden Tabelle aufgeführten Attribute aufweist:</span><span class="sxs-lookup"><span data-stu-id="a630b-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a630b-158">Active Directory-Attribut</span><span class="sxs-lookup"><span data-stu-id="a630b-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="a630b-159">Attributname</span><span class="sxs-lookup"><span data-stu-id="a630b-159">Attribute name</span></span></th>
    <th><span data-ttu-id="a630b-160">Korrekter Wert für lync Online Benutzer</span><span class="sxs-lookup"><span data-stu-id="a630b-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="a630b-161">Korrekter Wert für lync-lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="a630b-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a630b-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a630b-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="a630b-163">Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="a630b-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="a630b-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a630b-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="a630b-165">SRV</span><span class="sxs-lookup"><span data-stu-id="a630b-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a630b-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a630b-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="a630b-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="a630b-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="a630b-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a630b-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="a630b-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a630b-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a630b-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a630b-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="a630b-171">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a630b-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="a630b-172">True</span><span class="sxs-lookup"><span data-stu-id="a630b-172">True</span></span></p></td>
    <td><p><span data-ttu-id="a630b-173">True</span><span class="sxs-lookup"><span data-stu-id="a630b-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="a630b-174">Jeder Benutzer, der verschoben wurde, muss sich von lync abmelden und sich dann wieder anmelden.</span><span class="sxs-lookup"><span data-stu-id="a630b-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="a630b-175">Wenn Sie sich anmelden, sollten Sie ihre Kontaktlisten überprüfen und bei Bedarf Kontakte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a630b-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="a630b-176">Beachten Sie, dass geplante Besprechungen nicht von lync online zu lync lokal migriert werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="a630b-177">Benutzer müssen diese Besprechungen nach dem Verschieben neu planen.</span><span class="sxs-lookup"><span data-stu-id="a630b-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="a630b-178">Nachdem die DNS-Einträge aktualisiert wurden und alle Benutzer an die Prämisse weitergeleitet wurden, weist das Hostinganbieter-Attribut den lync-Benutzer an, entweder SRV-Einträge zu verwenden oder Sie an den Online Anbieter "sipfed.online.lync.com" zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="a630b-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

