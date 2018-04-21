---
title: Bereitstellen von Skype Room Systems v2 mit Exchange Online (Hybrid)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 mit Exchange Online.
ms.openlocfilehash: 4fea489c2ae8c3e2fbf8205936ad3ddbff52927a
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a><span data-ttu-id="d318b-103">Bereitstellen von Skype Room Systems v2 mit Exchange Online (Hybrid)</span><span class="sxs-lookup"><span data-stu-id="d318b-103">Deploy Skype Room Systems v2 with Exchange Online (Hybrid)</span></span>
 
<span data-ttu-id="d318b-104">Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d318b-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online.</span></span>
  
<span data-ttu-id="d318b-105">Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="d318b-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="d318b-106">In diesem Thema werden für Skype Raum Systemen v2 hybridbereitstellungen mit Exchange online gehostet.</span><span class="sxs-lookup"><span data-stu-id="d318b-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="d318b-107">Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d318b-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="d318b-108">Der folgende Prozess wird für viele Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d318b-108">The following process will work for many configurations.</span></span> <span data-ttu-id="d318b-109">Wenn der Vorgang nicht für die Installation die richtige ist, es wird empfohlen, dass Sie Windows PowerShell verwenden (finden Sie in Anhang: PowerShell) um die gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="d318b-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell (see Appendix: PowerShell) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="d318b-110">Sie sollten klicken Sie dann das bereitgestellte Windows PowerShell-Skript verwenden, überprüfen Sie das Skype Raum Systemen v2 Setup.</span><span class="sxs-lookup"><span data-stu-id="d318b-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="d318b-111">(Siehe Konto Überprüfungsskript).</span><span class="sxs-lookup"><span data-stu-id="d318b-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="d318b-112">Bereitstellen von Skype Room Systems v2 mit Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d318b-112">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="d318b-113">Vor der Bereitstellung von Skype Raum Systemen v2 mit Exchange Online, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="d318b-113">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="d318b-114">Weitere Informationen finden Sie unter [Skype Raum Systemen v2 Requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d318b-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="d318b-115">Zum Bereitstellen von Skype Raum Systemen v2 mit Exchange Online, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d318b-115">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="d318b-116">Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.</span><span class="sxs-lookup"><span data-stu-id="d318b-116">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="d318b-117">Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d318b-117">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="d318b-118">Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange Online wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d318b-118">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
  ```
  Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic 
-AllowRedirection

  ```

2. <span data-ttu-id="d318b-119">Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="d318b-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="d318b-120">Dadurch wird das Konto in Skype Raum Systemen v2 zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d318b-120">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="d318b-121">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="d318b-121">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="d318b-122">Wenn Sie eine neue Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="d318b-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="d318b-123">Um der Besprechung zu optimieren, benötigen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="d318b-123">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="d318b-p105">Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure AD herstellen. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d318b-p105">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="d318b-126">Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto</span><span class="sxs-lookup"><span data-stu-id="d318b-126">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="d318b-127">In **Active Directory-Benutzer und-Computer AD** -Tool mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, dass die Skype Raum Systeme v2-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d318b-127">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="d318b-p106">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d318b-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="d318b-p107">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d318b-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d318b-133">Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server 2015 auf Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="d318b-133">Selecting **Password never expires** is a requirement for Skype for Business Server 2015 on Skype Room Systems v2.</span></span> <span data-ttu-id="d318b-134">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="d318b-134">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="d318b-135">In diesem Fall müssen Sie eine Ausnahme für jedes Skype Raum Systemen v2-Benutzerkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d318b-135">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="d318b-136">Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d318b-136">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="d318b-p109">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss der Synchronisierung zur Benutzerseite, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d318b-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="d318b-139">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="d318b-139">Assign an Office 365 license</span></span>

1. <span data-ttu-id="d318b-140">Das Benutzerkonto muss eine gültige Office 365-Lizenz, um sicherzustellen, dass Exchange und Skype für Business Server 2015 funktioniert haben.</span><span class="sxs-lookup"><span data-stu-id="d318b-140">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server 2015 will work.</span></span> <span data-ttu-id="d318b-141">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort Ihres Benutzerkontos zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d318b-141">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="d318b-142">Im nächsten Schritt verwenden Sie Get-MsolAccountSku, um eine Liste der verfügbaren SKUs für Office 365-Mandanten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d318b-142">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="d318b-p111">Wenn Sie die SKUs aufgelistet haben, können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="d318b-p111">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a><span data-ttu-id="d318b-145">Aktivieren des Benutzerkontos in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d318b-145">Enable the user account with Skype for Business Server 2015</span></span>

1. <span data-ttu-id="d318b-146">Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d318b-146">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
  ```
  Import-Module LyncOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber

  ```

2. <span data-ttu-id="d318b-147">Führen Sie diesen Befehl, um Ihr Skype Raum Systemen v2-Konto für Skype für Business Server 2015 zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d318b-147">To enable your Skype Room Systems v2 account for Skype for Business Server 2015, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="d318b-148">Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einer vorhandenen Skype für Business Server 2015 Benutzer mit diesem Befehl abrufen.</span><span class="sxs-lookup"><span data-stu-id="d318b-148">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server 2015 user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="d318b-149">Zuweisen einer Skype for Business Server 2015-Lizenz zu Ihrem Skype Room Systems v2-Konto</span><span class="sxs-lookup"><span data-stu-id="d318b-149">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="d318b-150">Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="d318b-150">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="d318b-151">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="d318b-151">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="d318b-152">Klicken Sie auf das Konto Skype Raum Systemen v2, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d318b-152">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="d318b-153">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="d318b-153">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="d318b-154">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="d318b-154">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="d318b-155">Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP für Ihre Skype Raum Systemen v2 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d318b-155">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="d318b-156">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d318b-156">Click **Save**.</span></span>
    
<span data-ttu-id="d318b-157">Für die Validierung sollten Sie alle Skype für Business-Client verwenden Sie dieses Konto anzumelden sein.</span><span class="sxs-lookup"><span data-stu-id="d318b-157">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d318b-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d318b-158">See also</span></span>

#### 

[<span data-ttu-id="d318b-159">Planen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="d318b-159">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="d318b-160">Bereitstellen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="d318b-160">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="d318b-161">Konfigurieren einer Skype Raum Systemen v2-Konsole</span><span class="sxs-lookup"><span data-stu-id="d318b-161">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="d318b-162">Verwalten von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="d318b-162">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

