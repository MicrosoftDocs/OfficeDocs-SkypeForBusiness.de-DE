---
title: Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung (Hybrid)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: In diesem Thema erfahren Sie, wie Sie  in einer Hybridumgebung mit einer lokalen -Bereitstellung bereitstellen.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="8a6a4-103">Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung (Hybrid)</span><span class="sxs-lookup"><span data-stu-id="8a6a4-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="8a6a4-104">In diesem Thema erfahren Sie, wie Sie  in einer Hybridumgebung mit einer lokalen -Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-104">Read this topic for information on how to deploy  in a hybrid environment with  on premises.</span></span>
  
<span data-ttu-id="8a6a4-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="8a6a4-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="8a6a4-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="8a6a4-108">The following process will work for many configurations.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-108">The following process will work for many configurations.</span></span> <span data-ttu-id="8a6a4-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="8a6a4-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="8a6a4-111">(See Account Verification Script.)</span><span class="sxs-lookup"><span data-stu-id="8a6a4-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="8a6a4-112">Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8a6a4-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="8a6a4-113">Vergewissern Sie sich vor der Bereitstellung von  mit lokaler -Bereitstellung, dass die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-113">Before you deploy  with  on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="8a6a4-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a6a4-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="8a6a4-115">Wenn Sie  mit lokaler -Bereitstellung bereitstellen, fügen Sie mit den Active Directory-Verwaltungstools eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-115">If you are deploying  with  on premises,  you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="8a6a4-116">Dieses Konto wird mit  synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-116">This account will be synced to .</span></span> <span data-ttu-id="8a6a4-117">Sie müssen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-117">You will need to:</span></span>
  
- <span data-ttu-id="8a6a4-118">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="8a6a4-119">Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="8a6a4-120">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="8a6a4-120">Assign an Office 365 license</span></span>
    
- <span data-ttu-id="8a6a4-121">Aktivieren des Gerätekontos in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8a6a4-121">Enable the device account with Skype for Business</span></span> <span data-ttu-id="8a6a4-122">Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="8a6a4-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="8a6a4-124">Der Plan muss die Konferenzfunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="8a6a4-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="8a6a4-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="8a6a4-126">Ihre Mandantenbenutzer müssen über -Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-126">Your tenant users must have  mailboxes.</span></span>
    
  - <span data-ttu-id="8a6a4-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="8a6a4-128">Zuweisen einer Skype for Business Server 2015-Lizenz zu Ihrem Skype Room Systems v2-Konto</span><span class="sxs-lookup"><span data-stu-id="8a6a4-128">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="8a6a4-129">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="8a6a4-130">Klicken Sie im Tool Active Directory-Benutzer und -Computer mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre -Konten erstellt werden sollen. Klicken Sie auf Neu und dann auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-130">In the Active Directory Users and Computers AD tool, right-click on the folder or Organizational Unit that your  accounts will be created in, click New, and then click User.</span></span>
    
2. <span data-ttu-id="8a6a4-p106">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="8a6a4-p107">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a6a4-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="8a6a4-137">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="8a6a4-138">In diesem Fall müssen Sie für jedes einzelne -Gerätekonto eine Ausnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-138">If so, you'll need to create an exception for each  device account.</span></span>
  
4. <span data-ttu-id="8a6a4-139">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="8a6a4-140">Wechseln Sie nach Abschluss der Synchronisierung zur Benutzerseite im  Admin Center, und vergewissern Sie sich, dass das in den vorherigen Schritten erstellte Konto mit der Onlineversion zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-140">When it's complete, go to the users page in your  admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="8a6a4-141">Aktivieren des Remotepostfachs und Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8a6a4-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="8a6a4-142">Aktivieren Sie das Remotepostfach, indem Sie Ihre lokale -Verwaltungsshell mit Administratorberechtigungen öffnen und folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-142">Enable the remote mailbox by opening your on-premises  management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="8a6a4-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="8a6a4-144">Führen Sie auf Ihrem -Mandanten die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-144">From your  tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="8a6a4-145">Um die Besprechungsumgebung zu verbessern, müssen Sie die -Eigenschaften für das Gerätekonto wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-145">To improve the meeting experience, you'll need to set the  properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="8a6a4-146">Weitere Informationen zu den Eigenschaften, die Sie festlegen müssen, finden Sie unter „-Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-146">For more information about which properties you need to set, see  properties.</span></span>
    
4. <span data-ttu-id="8a6a4-147">Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure AD herstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="8a6a4-148">Sie können diesen Befehl ausführen, um die Verbindung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="8a6a4-149">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="8a6a4-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="8a6a4-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="8a6a4-151">Das Gerätekonto muss über eine gültige -Lizenz verfügen, damit  und  funktionieren. Wenn Sie die Lizenz haben, müssen Sie dem Gerätekonto einen Verwendungsstandort zuweisen. Von diesem hängt ab, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-151">The device account needs to have a valid  license to ensure that   and  will work. If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="8a6a4-152">Rufen Sie als Nächstes mit „Get-MsolAccountSku“ eine Liste der verfügbaren SKUs für Ihren -Mandanten ab.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your  tenant.</span></span>
    
3. <span data-ttu-id="8a6a4-p113">Wenn Sie die SKUs aufgelistet haben, können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="8a6a4-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="8a6a4-155">Aktivieren des Gerätekontos in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8a6a4-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="8a6a4-156">Erstellen Sie wie folgt auf einem PC eine -Remotesitzung:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-156">Create a remote  session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="8a6a4-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="8a6a4-158">Wenn Sie nicht sicher sind, welchen Wert Sie für den Parameter „RegistrarPool“ in Ihrer Umgebung verwenden sollen, können Sie mit dem folgenden Befehl den Wert eines vorhandenen -Benutzers abrufen:</span><span class="sxs-lookup"><span data-stu-id="8a6a4-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing  user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="8a6a4-159">Zuweisen einer Skype for Business-Lizenz zu Ihrem Skype Room Systems v2-Konto</span><span class="sxs-lookup"><span data-stu-id="8a6a4-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="8a6a4-160">Melden Sie sich als Mandantenadministrator an, öffnen Sie das -Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-160">Log in as a tenant administrator, open the  Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="8a6a4-161">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="8a6a4-162">Klicken Sie auf das -Konto und dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-162">Click the  account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="8a6a4-163">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="8a6a4-164">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="8a6a4-165">Wenn Sie Enterprise-VoIP mit  verwenden möchten, müssen Sie eine Plan 3-Lizenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your .</span></span>
    
6. <span data-ttu-id="8a6a4-166">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-166">Click **Save**.</span></span>
    
<span data-ttu-id="8a6a4-167">Zur Überprüfung können Sie sich mit einem beliebigen -Client bei diesem Konto anmelden.</span><span class="sxs-lookup"><span data-stu-id="8a6a4-167">For validation, you should be able to use any  client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a6a4-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a6a4-168">See also</span></span>

#### 

[<span data-ttu-id="8a6a4-169">Planung für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="8a6a4-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="8a6a4-170">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="8a6a4-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="8a6a4-171">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="8a6a4-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="8a6a4-172">Verwalten von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="8a6a4-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

