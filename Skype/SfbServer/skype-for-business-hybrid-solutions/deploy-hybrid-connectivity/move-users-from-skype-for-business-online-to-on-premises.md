---
title: Verschieben von Benutzern von Skype für Business Online auf lokal
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Zusammenfassung: Erfahren Sie, wie Benutzerkonten für Business Server lokal in Skype von online zu verschieben.'
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="c474e-103">Verschieben von Benutzern von Skype für Business Online auf lokal</span><span class="sxs-lookup"><span data-stu-id="c474e-103">Move users from Skype for Business Online to on premises</span></span>
 
<span data-ttu-id="c474e-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzerkonten für Business Server lokal in Skype von online zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="c474e-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>
  
<span data-ttu-id="c474e-105">Sie müssen möglicherweise Verschieben von Benutzerkonten von online zu lokal, um sicherzustellen, dass Benutzer online verwaltet und lokal untereinander sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="c474e-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="c474e-106">Um untereinander erkannt werden, müssen alle Benutzer im lokalen Active Directory Anwesenheitsstatus haben.</span><span class="sxs-lookup"><span data-stu-id="c474e-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="c474e-107">Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c474e-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="c474e-108">Sie sollten online Benutzer lokal, beispielsweise verschieben wenn:</span><span class="sxs-lookup"><span data-stu-id="c474e-108">You might want to move online users to on premises, for example, if:</span></span> 
  
- <span data-ttu-id="c474e-109">Sie müssen neue Benutzer, die lokal erstellt und dann in der Cloud verschoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c474e-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>
    
- <span data-ttu-id="c474e-110">Ihrer Organisation bereitgestellt Skype für Business Online, bevor es Skype für Business Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c474e-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="c474e-111">Aus diesem Grund haben Benutzer, die zuerst in der Cloud erstellt wurden und an dieser Stelle müssen lokal in verschoben werden soll, bevor sie ans Skype für Business Online sind.</span><span class="sxs-lookup"><span data-stu-id="c474e-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span> 
    
<span data-ttu-id="c474e-112">In diesem Thema werden zwei Szenarien beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c474e-112">This topic describes two scenarios:</span></span>
  
- [<span data-ttu-id="c474e-113">Verschieben Sie Benutzer online – wurden, die ursprünglich online – zu lokale</span><span class="sxs-lookup"><span data-stu-id="c474e-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [<span data-ttu-id="c474e-114">Verschieben Sie online Benutzer (die ursprünglich lokal wurden) in lokal</span><span class="sxs-lookup"><span data-stu-id="c474e-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="c474e-115">Verschieben Sie Benutzer online – wurden, die ursprünglich online – zu lokale</span><span class="sxs-lookup"><span data-stu-id="c474e-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="c474e-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="c474e-116"></span></span>

<span data-ttu-id="c474e-117">Dieser Abschnitt gilt nur für Benutzer, die erstellt und online aktiviert wurden, aber wer verfügen nicht über ein Konto in die lokale Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c474e-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span> 
  
<span data-ttu-id="c474e-118">Bevor Sie beginnen, Online-Benutzer zu Ihrer lokalen Umgebung zu verschieben, überprüfen Sie, ob alle folgenden Punkte zutreffen:</span><span class="sxs-lookup"><span data-stu-id="c474e-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>
  
- <span data-ttu-id="c474e-119">Ihre lokale Umgebung muss vollständig bereitgestellt und validiert.</span><span class="sxs-lookup"><span data-stu-id="c474e-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="c474e-120">Weitere Informationen finden Sie unter [Bereitstellen von Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) oder [Bereitstellen von Skype für Business Server 2015](../../deploy/deploy.md), abhängig davon, welche Version Sie lokal verwenden.</span><span class="sxs-lookup"><span data-stu-id="c474e-120">For more information, see [Deploying Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span> 
    
- <span data-ttu-id="c474e-121">Online-Mandanten muss für den Remotezugriff PowerShell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c474e-121">Your online tenant must be configured for remote PowerShell access.</span></span>
    
    <span data-ttu-id="c474e-122">Dazu installieren Sie zunächst die Skype für Business Online Connector-Modul für Windows PowerShell, erhalten Sie hier: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="c474e-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
    
    <span data-ttu-id="c474e-123">Nachdem Sie das Modul installieren, können Sie eine Remotesitzung herstellen, indem Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell eingeben:</span><span class="sxs-lookup"><span data-stu-id="c474e-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    <span data-ttu-id="c474e-124">Weitere Informationen dazu, wie Sie eine remote-PowerShell-Sitzung mit Skype für Business Online herstellen finden Sie unter [Connecting to Lync Online durch Verwenden von Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="c474e-124">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
    
    <span data-ttu-id="c474e-125">Weitere Informationen zur Verwendung der Skype für Business Online Connector PowerShell-Modul finden Sie unter [Using Windows PowerShell zum Verwalten von Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="c474e-125">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
    
- <span data-ttu-id="c474e-126">Online-Mandanten muss für einen freigegebenen SIP-Adressraum konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c474e-126">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="c474e-127">Zu diesem Zweck, starten Sie zuerst eine remote-Powershell-Sitzung mit Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="c474e-127">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="c474e-128">Führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="c474e-128">Then run the following cmdlet:</span></span>
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="c474e-129">Das SharedSipAddressSpace-Attribut muss "True", bis verschieben in online abgeschlossen ist und keine Benutzer bleiben weiterhin lokal.</span><span class="sxs-lookup"><span data-stu-id="c474e-129">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span> 
  
<span data-ttu-id="c474e-130">Nachdem Sie diese Schritte abgeschlossen haben, können Sie Benutzerkonten migrieren, wie im folgenden Verfahren beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c474e-130">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="c474e-131">Verschieben von Benutzerkonten, die ursprünglich online mit einer lokalen Bereitstellung aktiviert</span><span class="sxs-lookup"><span data-stu-id="c474e-131">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="c474e-132">Stellen Sie zuerst sicher, dass Ihre Organisation für die Hybridbereitstellung konfiguriert ist, einschließlich für Azure Active Directory-Verbindungs- und Synchronisierungstools.</span><span class="sxs-lookup"><span data-stu-id="c474e-132">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="c474e-133">Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c474e-133">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
    
  - <span data-ttu-id="c474e-134">Geben Sie in der lokalen Bereitstellung der Skype für Business Server-Verwaltungsshell die folgenden Cmdlets zum Erstellen der Hostinganbieter für Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="c474e-134">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="c474e-135">Für die Parameter Identität und Name können Sie jeden beliebigen Wert wählen.</span><span class="sxs-lookup"><span data-stu-id="c474e-135">You can use whatever value you want for the Identity and Name parameters.</span></span>
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="c474e-136">Vergewissern Sie sich, dass auf Ihrem lokalen Edge-Servern Sie die Zertifikatkette, die Verbindung mit Skype für Online Business ermöglicht haben wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c474e-136">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="c474e-137">Sie können diese Kette hier herunterladen: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="c474e-137">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>
    
|<span data-ttu-id="c474e-138">**Zertifikat**</span><span class="sxs-lookup"><span data-stu-id="c474e-138">**Certificate**</span></span>|<span data-ttu-id="c474e-139">**Zertifikatspeicher**</span><span class="sxs-lookup"><span data-stu-id="c474e-139">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c474e-140">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="c474e-140">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="c474e-141">Vertrauenswürdige Stammzertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c474e-141">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="c474e-142">Microsoft Internet Authority (Zertifikat einer neuen Zertifizierungsstelle)</span><span class="sxs-lookup"><span data-stu-id="c474e-142">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="c474e-143">Zwischenzertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c474e-143">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="c474e-144">MSIT Machine Auth CA2 (neue ausstellende CA2)</span><span class="sxs-lookup"><span data-stu-id="c474e-144">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="c474e-145">Zwischenzertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="c474e-145">Intermediate CA</span></span>  <br/> |
   
3. <span data-ttu-id="c474e-146">Aktivieren Sie im lokalen Active Directory die betroffenen Benutzerkonten für Skype für Business Server 2015 lokal.</span><span class="sxs-lookup"><span data-stu-id="c474e-146">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="c474e-147">Geben Sie dafür für einen einzelnen Benutzer das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="c474e-147">You can do this for an individual user by typing the following cmdlet:</span></span> 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="c474e-148">Oder erstellen Sie ein Skript, das Benutzernamen aus einer Datei liest und sie als Eingabe für das Cmdlet „Enable-CsUser“ bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="c474e-148">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="c474e-149">Synchronisieren Sie die online-Benutzer mit den aktualisierten lokalen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="c474e-149">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="c474e-150">Weitere Informationen finden Sie unter [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="c474e-150">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>
    
5. <span data-ttu-id="c474e-151">Aktualisieren Sie die folgenden DNS-Einträge, um alle SIP-Datenverkehr an Ihre lokale Bereitstellung leiten:</span><span class="sxs-lookup"><span data-stu-id="c474e-151">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>
    
  - <span data-ttu-id="c474e-152">Aktualisieren Sie den Eintrag **lyncdiscover.contoso.com** so, dass er auf den FQDN des lokalen Reverseproxyservers verweist.</span><span class="sxs-lookup"><span data-stu-id="c474e-152">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
  - <span data-ttu-id="c474e-153">Update der ** *_sip* . _tls.contoso.com** SRV aufzeichnen, um die öffentliche IP-Adresse oder die VIP-Adresse des Zugriffs-edgedienst der lokalen Lync zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c474e-153">Update the ** *_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
  - <span data-ttu-id="c474e-154">Update der ** *_sipfederationtls* . _tcp.contoso.com** SRV aufzeichnen, um die öffentliche IP-Adresse oder die VIP-Adresse des Zugriffs-edgedienst von Skype zu beheben für Business Server 2015 lokale-.</span><span class="sxs-lookup"><span data-stu-id="c474e-154">Update the ** *_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>
    
  - <span data-ttu-id="c474e-155">Wenn Ihre Organisation verwendet DNS (manchmal als "Split-Brain-DNS" bezeichnet) geteilt, stellen Sie sicher, dass Benutzer, die zum Auflösen von Namen durch die internen DNS-Zone auf den Front-End-Pool weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c474e-155">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>
    
6. <span data-ttu-id="c474e-156">Typ der `Get-CsUser` Cmdlet einige Eigenschaften über die Benutzer überprüfen, die verschoben werden können.</span><span class="sxs-lookup"><span data-stu-id="c474e-156">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="c474e-157">Sie sollten sicherstellen, dass HostingProviderProxyFQDN auf `"sipfed.online.lync.com"` festgelegt ist und die SIP-Adressen ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="c474e-157">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>
    
7. <span data-ttu-id="c474e-158">Verschieben Sie Benutzer online lokal.</span><span class="sxs-lookup"><span data-stu-id="c474e-158">Move online users to on premises.</span></span>
    
    <span data-ttu-id="c474e-159">Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="c474e-159">To move a single user, type this:</span></span>
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="c474e-160">Verschieben mehrerer Benutzer können mit dem Cmdlet **Get-CsUSer** mit dem Parameter Filter, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c474e-160">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="c474e-161">Beispielsweise können Sie alle Online-Benutzer auswählen, durch das Filtern nach {Hostinganbieter - Eq "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="c474e-161">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="c474e-162">Sie können dann die zurückgegebenen Benutzer an das Cmdlet **Move-CsUSer** leiten, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c474e-162">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="c474e-163">Das Format der URL für der **HostedMigrationOverrideUrl** -Parameter die URL auf den Pool sein muss, auf dem der Migration gehosteten Dienst wird, im folgenden Format ausgeführt, angegeben: _Https://\<Pool-FQDN\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="c474e-163">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
    
    <span data-ttu-id="c474e-164">Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c474e-164">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="c474e-165">So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="c474e-165">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="c474e-166">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="c474e-166">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="c474e-167">Öffnen Sie das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="c474e-167">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="c474e-168">Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="c474e-168">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="c474e-169">Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="c474e-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="c474e-170">Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c474e-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="c474e-171">Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c474e-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > <span data-ttu-id="c474e-172">Standardmäßig beträgt die maximale Größe für Transaktionsprotokolldateien der rtcxds-Datenbank 16 GB.</span><span class="sxs-lookup"><span data-stu-id="c474e-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="c474e-173">Dies ist möglicherweise nicht groß genug ist, wenn Sie eine große Anzahl von Benutzern auf einmal verschieben, insbesondere dann, wenn Sie die Spiegelung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c474e-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="c474e-174">Sie können dieses Problem umgehen, indem Sie die Dateigröße erhöhen oder die Protokolldateien regelmäßig sichern.</span><span class="sxs-lookup"><span data-stu-id="c474e-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="c474e-175">Weitere Informationen finden Sie unter [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="c474e-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span> 
  
8. <span data-ttu-id="c474e-176">Dies ist ein optionaler Schritt.</span><span class="sxs-lookup"><span data-stu-id="c474e-176">This is an optional step.</span></span> <span data-ttu-id="c474e-177">Wenn Sie eine Integration in Exchange 2013 Online benötigen, müssen Sie einen zusätzlichen Hostinganbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c474e-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="c474e-178">Weitere Informationen hierzu finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="c474e-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>
    
9. <span data-ttu-id="c474e-p114">Die Benutzer sind jetzt verschoben. Geben Sie das folgende Cmdlet ein, um zu überprüfen, ob ein Benutzer korrekte Werte für die in der folgenden Tabelle gezeigten Attribute hat:</span><span class="sxs-lookup"><span data-stu-id="c474e-p114">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span> 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="c474e-181">**Active Directory-Attribut**</span><span class="sxs-lookup"><span data-stu-id="c474e-181">**Active Directory attribute**</span></span>|<span data-ttu-id="c474e-182">**Name des Attributs**</span><span class="sxs-lookup"><span data-stu-id="c474e-182">**Attribute name**</span></span>|<span data-ttu-id="c474e-183">**Richtigen Wert für Online-Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c474e-183">**Correct value for Online user**</span></span>|<span data-ttu-id="c474e-184">**Richtigen Wert für lokale Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c474e-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c474e-185">MsRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="c474e-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="c474e-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="c474e-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="c474e-187">sipfed.Online.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c474e-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="c474e-188">SRV:</span><span class="sxs-lookup"><span data-stu-id="c474e-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="c474e-189">MsRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c474e-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="c474e-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="c474e-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="c474e-191">SIP:UserName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c474e-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="c474e-192">SIP:UserName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c474e-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="c474e-193">sRTCSIP UserEnabled</span><span class="sxs-lookup"><span data-stu-id="c474e-193">sRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="c474e-194">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="c474e-194">Enabled</span></span>  <br/> |<span data-ttu-id="c474e-195">True</span><span class="sxs-lookup"><span data-stu-id="c474e-195">True</span></span>  <br/> |<span data-ttu-id="c474e-196">True</span><span class="sxs-lookup"><span data-stu-id="c474e-196">True</span></span>  <br/> |
   
10. <span data-ttu-id="c474e-p115">Jeder verschobene Benutzer muss sich ab- und dann erneut anmelden. Nach der Anmeldung sollte jeder Benutzer seine Kontaktlisten überprüfen und ggf. Kontakte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c474e-p115">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="c474e-p116">Beachten Sie, dass geplante Besprechungen nicht von der Online- zur lokalen Bereitstellung migriert werden. Benutzer müssen diese Besprechungen erneut planen, nachdem sie verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="c474e-p116">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="c474e-201">Nachdem die DNS-Einträge aktualisiert werden und alle Benutzer werden auf lokalen geleitet, leitet das Attribut HostingProvider den Benutzer zum SRV-Einträge verwenden, oder weisen sie dem Onlineanbieter "sipfed.online.lync.com."</span><span class="sxs-lookup"><span data-stu-id="c474e-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="c474e-202">Verschieben Sie online Benutzer (die ursprünglich lokal wurden) in lokal</span><span class="sxs-lookup"><span data-stu-id="c474e-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="c474e-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="c474e-203"></span></span>

<span data-ttu-id="c474e-204">Dieser Abschnitt gilt nur für Benutzer, die erstellt und aktiviert für eine lokale Bereitstellung und klicken Sie dann auf online aus einer lokalen Bereitstellung verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="c474e-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span> 
  
- <span data-ttu-id="c474e-205">Führen Sie die folgenden Cmdlets zum Verschieben eines Benutzers von Skype für Business Online wieder auf lokal, ersetzen den Wert für die **Identität** und **Ziel** -Parameter an den richtigen Werten für Ihre Umgebung:</span><span class="sxs-lookup"><span data-stu-id="c474e-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="c474e-206">Das Format der URL für den **HostedMigrationOverrideUrl** -Parameter angegebene muss die URL auf den Pool, in dem der Migration gehosteten Dienst, im folgenden Format ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="c474e-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>
  
 <span data-ttu-id="c474e-207">_Https://\<Pool-FQDN\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="c474e-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="c474e-208">Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c474e-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="c474e-209">So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="c474e-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="c474e-210">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="c474e-210">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="c474e-211">Öffnen Sie das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="c474e-211">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="c474e-212">Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="c474e-212">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="c474e-213">Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="c474e-213">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="c474e-214">Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c474e-214">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="c474e-215">Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c474e-215">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

