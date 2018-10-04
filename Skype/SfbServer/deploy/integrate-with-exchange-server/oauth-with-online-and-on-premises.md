---
title: OAuth-Konfiguration zwischen Skype for Business Online und einer lokalen Bereitstellung von Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Konfigurieren von OAuth aktiviert-Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Exchange-Integration in featureunterstützung beschriebenen Features.
ms.openlocfilehash: d4c7e491b43b457c96a69ebba1ea808054346d98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373871"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="ba8be-103">OAuth-Konfiguration zwischen Skype for Business Online und einer lokalen Bereitstellung von Exchange</span><span class="sxs-lookup"><span data-stu-id="ba8be-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>

<span data-ttu-id="ba8be-104">Konfigurieren von OAuth ermöglicht die Authentifizierung zwischen Exchange lokal und Skype für Business Online die Skype für Geschäfts- und Integration von Exchange-Features beschrieben in [Feature zu unterstützen](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="ba8be-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="ba8be-105">Dieses Thema bezieht sich auf Exchange Server 2016 und Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba8be-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ba8be-106">Was Sie wissen müssen, bevor Sie anfangen</span><span class="sxs-lookup"><span data-stu-id="ba8be-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ba8be-107">Geschätzte Dauer bis zum Abschluss dieser Aufgabe: 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="ba8be-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="ba8be-108">Sie sind auf die Zuweisung bestimmter Berechtigungen angewiesen, damit Sie diesen Vorgang bzw. diese Verfahren durchführen können.</span><span class="sxs-lookup"><span data-stu-id="ba8be-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="ba8be-109">Welche Berechtigungen Sie müssen finden Sie im Thema [Exchange and Shell Infrastructure Permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="ba8be-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="ba8be-110">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="ba8be-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="ba8be-111">Konfigurieren Sie OAuth-Authentifizierung zwischen Ihren lokalen Exchange- und Skype for Business-Organisationen.</span><span class="sxs-lookup"><span data-stu-id="ba8be-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="ba8be-112">Schritt 1: Erstellen eines Autorisierungsserverobjekts für Ihre Skype for Business Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="ba8be-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="ba8be-113">Geben Sie eine überprüfte Domäne für Ihre Skype für Business Online-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="ba8be-114">Diese Domäne sollte dieselbe sein, die auch als primäre SIP-Domäne für die Cloud-basierte Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba8be-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="ba8be-115">Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="ba8be-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

<span data-ttu-id="ba8be-116">Führen Sie den folgenden Befehl in der Exchange-Verwaltungsshell (Exchange PowerShell) in Ihrer lokalen Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="ba8be-117">Schritt 2: Aktivieren der Partneranwendung für Ihre Skype for Business Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="ba8be-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="ba8be-118">Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="ba8be-119">Schritt 3: Erstellen eines neuen E-Mail-Benutzerkontos für die Skype for Business Online-Partneranwendung</span><span class="sxs-lookup"><span data-stu-id="ba8be-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="ba8be-p103">Dieser Schritt wird lokal erledigt. Ein E-Mail-Benutzer wird angelegt und bekommt die entsprechenden Berechtigungen für die Verwaltungsrolle zugewiesen. Dieses Konto wird anschließend im nächsten Schritt gebraucht.</span><span class="sxs-lookup"><span data-stu-id="ba8be-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>

<span data-ttu-id="ba8be-123">Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="ba8be-124">Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba8be-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="ba8be-125">Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="ba8be-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="ba8be-126">Darüber hinaus die \<DomainControllerFQDN\> sollte der FQDN eines Domänencontrollers sein.</span><span class="sxs-lookup"><span data-stu-id="ba8be-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="ba8be-127">Dieser Befehl blendet den neuen E-Mail-Benutzer aus der Adressliste aus.</span><span class="sxs-lookup"><span data-stu-id="ba8be-127">This command will hide the new mail user from address lists.</span></span>

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="ba8be-128">Die nächsten beiden Befehle weisen diesem neuen Konto die „UserApplication“- und die „ArchiveApplication“-Verwaltungsrolle zu.</span><span class="sxs-lookup"><span data-stu-id="ba8be-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="ba8be-129">Schritt 4: Erstellen und Aktivieren der Partneranwendung für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ba8be-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="ba8be-130">Erstellen Sie eine neue Partneranwendung, die das Konto verwendet, das Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba8be-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="ba8be-131">Führen Sie den folgenden Befehl in der Exchange PowerShell in Ihrer lokalen Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="ba8be-132">Schritt 5: Exportieren des lokalen Autorisierungszertifikats</span><span class="sxs-lookup"><span data-stu-id="ba8be-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="ba8be-133">Führen Sie ein PowerShell-Skript zum Exportieren des lokalen autorisierungszertifikats, die Sie an Ihre Skype für Business Online-Organisation im nächsten Schritt importieren werden.</span><span class="sxs-lookup"><span data-stu-id="ba8be-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="ba8be-134">Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „ExportAuthCert.ps1“ nennen können.</span><span class="sxs-lookup"><span data-stu-id="ba8be-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```
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

<span data-ttu-id="ba8be-135">In Exchange PowerShell in Ihrer lokalen Exchange-Organisation führen die PowerShell-Skripts, die Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba8be-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="ba8be-136">Beispiel:.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="ba8be-136">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="ba8be-137">Schritt 6: Hochladen des lokalen Autorisierungszertifikats nach Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="ba8be-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="ba8be-138">Verwenden Sie im nächsten Schritt Windows PowerShell, um das im vorigen Schritt exportierte Autorisierungszertifikat auf Azure Active Directory Access Control Services (ACS) hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="ba8be-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="ba8be-139">Dafür muss das Azure Active Directory-Modul für Windows PowerShell-Cmdlets bereits installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ba8be-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="ba8be-140">Wenn dies nicht der Fall ist, fahren Sie mit [https://aka.ms/aadposh](https://aka.ms/aadposh) So installieren Sie die Azure Active Directory-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba8be-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="ba8be-141">Schließen Sie die folgenden Schritte ab, nachdem das Azure Active Directory-Modul für Windows PowerShell installiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="ba8be-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="ba8be-p108">Klicken Sie auf die **Azure Active Directory-Modul für Windows PowerShell**-Verknüpfung, um einen Windows PowerShell-Arbeitsbereich mit den installierten Azure AD-Cmdlets zu öffnen. Alle Befehle in diesem Schritt werden mithilfe der Windows PowerShell für Azure Active Directory ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba8be-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="ba8be-144">Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, z. B. `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="ba8be-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="ba8be-145">Führen Sie das PowerShell-Skript aus, das Sie im vorigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba8be-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="ba8be-146">Zum Beispiel:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="ba8be-146">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="ba8be-p110">Nach dem Start des Skripts wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie die Anmeldeinformationen für das Mandantenadministratorkonto Ihrer Microsoft Online Azure AD-Organisation ein. Nachdem das Skript ausgeführt worden ist, lassen Sie die Windows PowerShell für die Azure AD-Sitzung offen. Sie brauchen sie, um im nächsten Schritt ein PowerShell-Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba8be-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="ba8be-151">Schritt 7: Registrieren der Hostname-Zertifizierungsstellen für die SMTP-Domäne</span><span class="sxs-lookup"><span data-stu-id="ba8be-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="ba8be-152">Geben Sie eine überprüfte Domäne für Ihre Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba8be-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="ba8be-153">Diese Domäne sollte der gleichen Domäne wie die primäre SMTP-Domäne für den lokalen Exchange-Konten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba8be-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="ba8be-154">Wird diese Domäne als bezeichnet \<Ihrer Domäne überprüft\> in das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="ba8be-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="ba8be-155">Die erfolgreiche Ausführung des folgenden Skripts setzt voraus, dass die Windows PowerShell für Azure Active Directory mit Ihrem Microsoft Online Azure AD-Mandanten verbunden ist, wie unter Schritt 4 im vorigen Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="ba8be-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span>

1. <span data-ttu-id="ba8be-156">Speichern Sie den folgenden Text in einer PowerShell-Skriptdatei, die Sie zum Beispiel „RegisterEndpoints.ps1“ nennen können.</span><span class="sxs-lookup"><span data-stu-id="ba8be-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="ba8be-157">In diesem Beispiel wird ein Platzhalter verwendet, um alle Endpunkte für „contoso.com“ zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ba8be-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="ba8be-158">Ersetzen Sie "contoso.com" durch eine Hostname Autorität für Ihre lokale Exchange-Organisation</span><span class="sxs-lookup"><span data-stu-id="ba8be-158">Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. <span data-ttu-id="ba8be-159">Führen Sie in Windows PowerShell für Azure Active Directory das Windows PowerShell-Skript aus, das Sie im vorigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba8be-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="ba8be-160">Beispiel: `.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="ba8be-160">For example: `.\RegisterEndpoints.ps1`</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="ba8be-161">Überprüfen Ihres Erfolgs</span><span class="sxs-lookup"><span data-stu-id="ba8be-161">Verify your success</span></span>

<span data-ttu-id="ba8be-162">Stellen Sie sicher, dass die OAuth-Konfiguration korrekt ist, indem Sie überprüfen, ob einige der Funktionen erfolgreich ausgeführt werden können, zum Beispiel, ob die aufgezeichneten Unterhaltungen für Mobilgeräte-Clients im Ordner der aufgezeichneten Outlook-Unterhaltungen sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="ba8be-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>

1. <span data-ttu-id="ba8be-163">Starten Sie die Skype für mobile Geschäfts-app auf dem Windows Phone oder iOS-Gerät, und melden Sie sich als ein Skype für Business Online-Benutzer mit einem Exchange-2016 oder Exchange 2013 lokales Postfach.</span><span class="sxs-lookup"><span data-stu-id="ba8be-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>

2. <span data-ttu-id="ba8be-164">Haben Sie eine Sofortnachrichtenunterhaltung mit einer anderen Skype für Business Online-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ba8be-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>

3. <span data-ttu-id="ba8be-165">Schließen Sie das Chatunterhaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="ba8be-165">Close the IM conversation window.</span></span>

4. <span data-ttu-id="ba8be-166">Starten Sie Outlook für diesen Nutzer und überprüfen Sie, ob die Unterhaltung im Ordner der aufgezeichneten Outlook-Unterhaltungen sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ba8be-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>

<span data-ttu-id="ba8be-167">Betrachten Sie alternativ den Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="ba8be-167">Alternately, look at your traffic.</span></span> <span data-ttu-id="ba8be-168">Des Datenverkehrs in einem OAuth-Handshake ist wirklich charakteristischen (und nicht sehen, wie die Standardauthentifizierung), insbesondere zur Umgehung von Bereichen, wobei Sie Aussteller-Datenverkehr angezeigt, die folgendermaßen aussieht beginnen: 00000004-0000-0ff1-ce00-000000000000 @ (manchmal mit einem / vor das @-Zeichen), in der Token, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ba8be-168">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="ba8be-169">Benutzernamen und Kennwort an, das die Punkt OAuth wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba8be-169">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="ba8be-170">Aber sehen Sie den Aussteller 'Office' – in diesem Fall ist "4" Skype für Unternehmen – und dem Bereich Ihres Abonnements.</span><span class="sxs-lookup"><span data-stu-id="ba8be-170">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="ba8be-171">Wenn Sie sicherstellen möchten, dass Sie erfolgreich OAuth verwenden, stellen Sie sicher, dass Sie wissen, was zu erwarten und wissen, wie der Datenverkehr aussehen sollte.</span><span class="sxs-lookup"><span data-stu-id="ba8be-171">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="ba8be-172">[Hier ist zu erwarten, dass](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)dies der Fall ist, hier ist ein ziemlich standard [Beispiel OAuth-Verkehr in einer Microsoft-Anwendung](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (sehr nützlich zu lesen, obwohl es nicht Aktualisierungstoken verwendet), und es sind Fiddler-Erweiterungen, die Sie in Ihre OAuth JWT (JSON suchen können Web Token).</span><span class="sxs-lookup"><span data-stu-id="ba8be-172">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="ba8be-173">Es folgt ein [Beispiel für eine einrichten](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), jedoch können Sie diesen Prozess verpflichten sich gerne Netzwerk Tracing-Tools.</span><span class="sxs-lookup"><span data-stu-id="ba8be-173">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>
