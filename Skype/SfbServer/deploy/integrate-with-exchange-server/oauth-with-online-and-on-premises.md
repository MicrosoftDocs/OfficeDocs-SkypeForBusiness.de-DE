---
title: Integration von Skype for Business Online und Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Wenn Sie die OAuth-Authentifizierung zwischen Exchange lokal und Skype for Business Online konfigurieren, werden die unter Funktionsunterstützung beschriebenen Funktionen für Skype for Business und die Exchange-Integration aktiviert.
ms.openlocfilehash: 1d64f8fe7b2d6dcf276ae34e74c84faf5c93f65a
ms.sourcegitcommit: 2b4fcf2561134b9f1b9a1b49401d97da1286e89d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37979778"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="5d307-103">Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5d307-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="5d307-104">Durch die Konfiguration der Integration zwischen Exchange Server und Skype for Business Online werden die unter [Funktionsunterstützung](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)beschriebenen Funktionen für Skype for Business und Exchange integriert.</span><span class="sxs-lookup"><span data-stu-id="5d307-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="5d307-105">Dieses Thema bezieht sich auf die Integration in Exchange Server 2013 bis 2019.</span><span class="sxs-lookup"><span data-stu-id="5d307-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5d307-106">Was Sie wissen müssen, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="5d307-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5d307-107">Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="5d307-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="5d307-108">Sie müssen Berechtigungen zugewiesen sein, bevor Sie diese Schritte ausführen können.</span><span class="sxs-lookup"><span data-stu-id="5d307-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="5d307-109">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie im Thema zu den [Berechtigungen für Exchange-und Shell-Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="5d307-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="5d307-110">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten können, finden Sie unter [Tastenkombinationen im Exchange Admin Center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="5d307-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="5d307-111">Informationen zur Kompatibilität finden Sie unter [Skype for Business-Kompatibilität mit Office-Apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="5d307-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="5d307-112">Konfigurieren der Integration zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="5d307-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="5d307-113">Schritt 1: Konfigurieren der OAuth-Authentifizierung zwischen Exchange Server und Office 365</span><span class="sxs-lookup"><span data-stu-id="5d307-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="5d307-114">Führen Sie die im folgenden Artikel aufgeführten Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5d307-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="5d307-115">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="5d307-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="5d307-116">Schritt 2: Erstellen eines neuen e-Mail-Benutzerkontos für die Skype for Business Online-Partner Anwendung</span><span class="sxs-lookup"><span data-stu-id="5d307-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="5d307-117">Dieser Schritt erfolgt auf dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="5d307-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="5d307-118">Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5d307-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="5d307-119">Dieses Konto wird anschließend im nächsten Schritt gebraucht.</span><span class="sxs-lookup"><span data-stu-id="5d307-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="5d307-120">Geben Sie eine verifizierte Domäne für Ihre Exchange-Organisation an.</span><span class="sxs-lookup"><span data-stu-id="5d307-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="5d307-121">Diese Domäne sollte dieselbe Domäne sein wie die primäre SMTP-Domäne, die für die lokalen Exchange-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d307-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="5d307-122">Diese Domäne wird im folgenden \<Verfahren als Ihre\> überprüfte Domäne bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5d307-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="5d307-123">Außerdem sollte der \<DomainControllerFQDN\> der FQDN eines Domänencontrollers sein.</span><span class="sxs-lookup"><span data-stu-id="5d307-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="5d307-124">Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.</span><span class="sxs-lookup"><span data-stu-id="5d307-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="5d307-125">Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.</span><span class="sxs-lookup"><span data-stu-id="5d307-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="5d307-126">Schritt 3: Erstellen und Aktivieren einer Partner Anwendung für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5d307-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="5d307-127">Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5d307-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="5d307-128">Führen Sie den folgenden Befehl in der Exchange-PowerShell in Ihrer lokalen Exchange-Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="5d307-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="5d307-129">Schritt 4: Exportieren des lokalen Autorisierungs Zertifikats</span><span class="sxs-lookup"><span data-stu-id="5d307-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="5d307-130">Führen Sie ein PowerShell-Skript aus, um das lokale Autorisierungszertifikat zu exportieren, das Sie im nächsten Schritt in Ihre Skype for Business Online-Organisation importieren werden.</span><span class="sxs-lookup"><span data-stu-id="5d307-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="5d307-131">Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „ExportAuthCert.ps1“ nennen können.</span><span class="sxs-lookup"><span data-stu-id="5d307-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="5d307-132">Führen Sie in Exchange PowerShell in Ihrer lokalen Exchange-Organisation das soeben erstellte PowerShell-Skript aus.</span><span class="sxs-lookup"><span data-stu-id="5d307-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="5d307-133">Beispiel: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="5d307-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="5d307-134">Schritt 5: Hochladen des lokalen Autorisierungs Zertifikats in Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="5d307-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="5d307-135">Verwenden Sie im nächsten Schritt Windows PowerShell, um das im vorigen Schritt exportierte Autorisierungszertifikat auf Azure Active Directory Access Control Services (ACS) hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="5d307-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="5d307-136">Dafür muss das Azure Active Directory-Modul für Windows PowerShell-Cmdlets bereits installiert sein.</span><span class="sxs-lookup"><span data-stu-id="5d307-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="5d307-137">Wenn Sie nicht installiert ist, wechseln [https://aka.ms/aadposh](https://aka.ms/aadposh) Sie zu installieren des Azure Active Directory-Moduls für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d307-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="5d307-138">Schließen Sie die folgenden Schritte ab, nachdem das Azure Active Directory-Modul für Windows PowerShell installiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="5d307-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="5d307-p107">Klicken Sie auf die **Azure Active Directory-Modul für Windows PowerShell**-Verknüpfung, um einen Windows PowerShell-Arbeitsbereich mit den installierten Azure AD-Cmdlets zu öffnen. Alle Befehle in diesem Schritt werden mithilfe der Windows PowerShell für Azure Active Directory ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5d307-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="5d307-141">Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei mit dem Namen `UploadAuthCert.ps1`, beispielsweise.</span><span class="sxs-lookup"><span data-stu-id="5d307-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="5d307-142">Führen Sie das PowerShell-Skript aus, das Sie im vorigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5d307-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="5d307-143">Zum Beispiel:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="5d307-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="5d307-p109">Nach dem Start des Skripts wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie die Anmeldeinformationen für das Mandantenadministratorkonto Ihrer Microsoft Online Azure AD-Organisation ein. Nachdem das Skript ausgeführt worden ist, lassen Sie die Windows PowerShell für die Azure AD-Sitzung offen. Sie brauchen sie, um im nächsten Schritt ein PowerShell-Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5d307-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="5d307-148">Schritt 6: überprüfen, ob das Zertifikat in den Skype for Business-Dienstprinzipal hochgeladen wurde</span><span class="sxs-lookup"><span data-stu-id="5d307-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="5d307-149">Führen Sie in der PowerShell, die in Azure Active Directory geöffnet und authentifiziert wurde, die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5d307-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="5d307-150">Drücken Sie die EINGABETASTE, wenn Sie zur ReturnKeyValues aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="5d307-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="5d307-151">Bestätigen, dass ein Schlüssel mit Anfangsdatum und Enddaten angezeigt wird, die dem Start-und Enddatum Ihres Exchange OAuth-Zertifikats entsprechen</span><span class="sxs-lookup"><span data-stu-id="5d307-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="5d307-152">Überprüfen Ihres Erfolgs</span><span class="sxs-lookup"><span data-stu-id="5d307-152">Verify your success</span></span>

<span data-ttu-id="5d307-153">Überprüfen Sie, ob die Konfiguration korrekt ist, indem Sie sicherstellen, dass einige Features erfolgreich funktionieren.</span><span class="sxs-lookup"><span data-stu-id="5d307-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="5d307-154">Bestätigen Sie, dass Skype for Business-Benutzer mit Cloud-Voicemaildienst in einer Organisation mit einer Exchange Server-Hybrid Konfiguration Ihre Voicemail-Grußformeln erfolgreich ändern können.</span><span class="sxs-lookup"><span data-stu-id="5d307-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="5d307-155">Der Konversations Verlauf für mobile Clients bestätigen ist im Outlook-Ordner "Konversations Verlauf" sichtbar.</span><span class="sxs-lookup"><span data-stu-id="5d307-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="5d307-156">Vergewissern Sie sich, dass archivierte Chatnachrichten im lokalen Postfach des Benutzers im Ordner "Säuberungen" unter Verwendung von [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)hinterlegt sind.</span><span class="sxs-lookup"><span data-stu-id="5d307-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="5d307-157">Schauen Sie sich alternativ Ihren Traffic an.</span><span class="sxs-lookup"><span data-stu-id="5d307-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="5d307-158">Der Datenverkehr in einem OAuth-Handshake ist wirklich charakteristisch (und sieht nicht wie die Standardauthentifizierung aus), insbesondere im Bereich der Realms, wo Sie beginnen, den Emittenten-Traffic zu sehen, der wie folgt aussieht: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit a/before das @-Zeichen) in den Token, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5d307-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="5d307-159">Sie sehen keinen Benutzernamen oder kein Kennwort, was der OAuth-Punkt ist.</span><span class="sxs-lookup"><span data-stu-id="5d307-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="5d307-160">Sie sehen aber den Aussteller "Office" – in diesem Fall "4" ist Skype for Business – und das Reich Ihres Abonnements.</span><span class="sxs-lookup"><span data-stu-id="5d307-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="5d307-161">Wenn Sie sicher sein möchten, dass Sie OAuth erfolgreich verwenden, stellen Sie sicher, dass Sie wissen, was Sie erwarten und wissen, wie der Datenverkehr aussehen soll.</span><span class="sxs-lookup"><span data-stu-id="5d307-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="5d307-162">Hier [sehen Sie also ein](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)ziemlich Standard [Beispiel für OAuth-Datenverkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (wirklich hilfreich zum Lesen, obwohl es keine Aktualisierungs Tokens verwendet), und es gibt Fiddler-Erweiterungen, mit denen Sie Ihre OAuth-JWT (JSON Web-Token).</span><span class="sxs-lookup"><span data-stu-id="5d307-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="5d307-163">Hier ist ein [Beispiel für die Einrichtung](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), aber Sie können jedes Netzwerk-Tracing-Tool verwenden, mit dem Sie diesen Prozess durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d307-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d307-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5d307-164">Related topics</span></span>

[<span data-ttu-id="5d307-165">Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen</span><span class="sxs-lookup"><span data-stu-id="5d307-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
