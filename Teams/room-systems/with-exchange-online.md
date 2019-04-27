---
title: Bereitstellen von Microsoft-Teams, Räume mit Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Exchange Online.
ms.openlocfilehash: 1dc4e73fea7376033d8914cd1814e1edeb68e7d5
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362843"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="9e368-103">Bereitstellen von Microsoft-Teams, Räume mit Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e368-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="9e368-104">Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Exchange Online und Skype für Business Server lokal.</span><span class="sxs-lookup"><span data-stu-id="9e368-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="9e368-105">Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9e368-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="9e368-106">In diesem Thema werden die hybridbereitstellungen für Microsoft-Teams Chatrooms mit Exchange online gehostet.</span><span class="sxs-lookup"><span data-stu-id="9e368-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="9e368-107">Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9e368-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="9e368-108">Der folgende Prozess wird für viele Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e368-108">The following process will work for many configurations.</span></span> <span data-ttu-id="9e368-109">Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="9e368-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="9e368-110">Die einfachste Möglichkeit zum Einrichten von Benutzerkonten ist von remote Windows PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e368-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9e368-111">Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Microsoft Teams Räume-Benutzerkonten aktivieren überprüfen helfen.</span><span class="sxs-lookup"><span data-stu-id="9e368-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="9e368-112">Auf Wunsch können Sie die Schritte unten, um das Konfigurieren von Konten, mit Ihrem Microsoft-Teams Chatrooms Gerät.</span><span class="sxs-lookup"><span data-stu-id="9e368-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e368-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9e368-113">Requirements</span></span>

<span data-ttu-id="9e368-114">Vor der Bereitstellung von Microsoft-Teams Chatrooms mit Exchange Online, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="9e368-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="9e368-115">Weitere Informationen finden Sie unter [Microsoft Teams Chatrooms Requirements](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e368-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="9e368-116">Führen Sie die folgenden Schritte aus, für die Bereitstellung von Microsoft-Teams Chatrooms mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9e368-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="9e368-117">Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e368-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="9e368-118">Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e368-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="9e368-119">Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange Online wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9e368-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="9e368-120">Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="9e368-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="9e368-121">Dadurch wird das Konto in Microsoft Teams Räume zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="9e368-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="9e368-122">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="9e368-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="9e368-123">Wenn Sie eine neue Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="9e368-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="9e368-124">Um der Besprechung zu optimieren, benötigen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="9e368-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="9e368-125">Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto</span><span class="sxs-lookup"><span data-stu-id="9e368-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="9e368-126">In **Active Directory-Benutzer und-Computer AD** -Tool mit der rechten Maustaste auf den Container oder Organisationseinheit, dass Ihre Microsoft Teams Räume-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="9e368-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="9e368-127">Geben Sie den Anzeigenamen (-Identity) aus dem vorherigen Cmdlet (Set-Mailbox oder New-Mailbox) in das Feld **Vollständiger Name** und der Alias in das Feld **Benutzeranmeldename** ein.</span><span class="sxs-lookup"><span data-stu-id="9e368-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="9e368-128">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9e368-128">Click **Next**.</span></span>
3. <span data-ttu-id="9e368-p107">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9e368-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e368-132">Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Microsoft Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="9e368-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="9e368-133">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="9e368-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="9e368-134">In diesem Fall müssen Sie eine Ausnahme für jedes Benutzerkonto Microsoft Teams Chatrooms zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e368-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="9e368-135">Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e368-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="9e368-p109">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss der Synchronisierung zur Benutzerseite, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="9e368-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="9e368-138">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="9e368-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="9e368-139">Schließen Sie zuerst Azure AD einige kontoeinstellungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="9e368-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="9e368-140">Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9e368-140">You can run this cmdlet to connect.</span></span>

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="9e368-141">Das Benutzerkonto muss eine gültige Office 365-Lizenz, um sicherzustellen, dass Exchange und Skype für Business Server funktioniert haben.</span><span class="sxs-lookup"><span data-stu-id="9e368-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="9e368-142">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort Ihres Benutzerkontos zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="9e368-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9e368-143">Die Zuordnung stellen Sie in einem der folgenden Schritt.</span><span class="sxs-lookup"><span data-stu-id="9e368-143">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="9e368-144">Im nächsten Schritt verwenden.`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="9e368-144">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="9e368-145">zum Abrufen einer Liste der verfügbaren SKUs für Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="9e368-145">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="9e368-146">Nachdem Sie sich die SKUs anbieten, können Sie hinzufügen, eine Lizenz mit der`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="9e368-146">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="9e368-147">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e368-147">cmdlet.</span></span> <span data-ttu-id="9e368-148">In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="9e368-148">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="9e368-149">Aktivieren des Benutzerkontos mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="9e368-149">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="9e368-150">Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9e368-150">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="9e368-151">Führen Sie diesen Befehl, um Ihr Konto Microsoft Teams Chatrooms für Skype für Business Server zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9e368-151">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="9e368-152">Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einer vorhandenen Skype für Business Server-Benutzer, die mit diesem Befehl abrufen.</span><span class="sxs-lookup"><span data-stu-id="9e368-152">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="9e368-153">Weisen Sie Ihr Konto Microsoft Teams Chatrooms einen Skype für Business Server-Lizenz</span><span class="sxs-lookup"><span data-stu-id="9e368-153">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="9e368-154">Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="9e368-154">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="9e368-155">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="9e368-155">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="9e368-156">Klicken Sie auf der Microsoft-Teams Räume-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9e368-156">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="9e368-157">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="9e368-157">Click **Licenses**.</span></span>
5. <span data-ttu-id="9e368-158">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="9e368-158">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="9e368-159">Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP auf Microsoft Teams Chatrooms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9e368-159">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="9e368-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9e368-160">Click **Save**.</span></span>

<span data-ttu-id="9e368-161">Für die Validierung sollten Sie alle Skype für Business-Client verwenden Sie dieses Konto anzumelden sein.</span><span class="sxs-lookup"><span data-stu-id="9e368-161">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e368-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e368-162">See also</span></span>

[<span data-ttu-id="9e368-163">Konfigurieren von Konten für Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="9e368-163">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9e368-164">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="9e368-164">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="9e368-165">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="9e368-165">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="9e368-166">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="9e368-166">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="9e368-167">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="9e368-167">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
