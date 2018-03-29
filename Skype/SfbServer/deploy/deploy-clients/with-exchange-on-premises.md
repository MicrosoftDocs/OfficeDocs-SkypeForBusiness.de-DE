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
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 in einer hybridumgebung mit Exchange lokal.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="cb262-103">Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung (Hybrid)</span><span class="sxs-lookup"><span data-stu-id="cb262-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="cb262-104">Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 in einer hybridumgebung mit Exchange lokal.</span><span class="sxs-lookup"><span data-stu-id="cb262-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises.</span></span>
  
<span data-ttu-id="cb262-105">Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="cb262-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="cb262-106">In diesem Thema werden für Skype Raum Systemen v2 hybridbereitstellungen mit Exchange lokal gehostet.</span><span class="sxs-lookup"><span data-stu-id="cb262-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="cb262-107">Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cb262-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="cb262-108">Der folgende Prozess wird für viele Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb262-108">The following process will work for many configurations.</span></span> <span data-ttu-id="cb262-109">Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="cb262-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="cb262-110">Sie sollten klicken Sie dann das bereitgestellte Windows PowerShell-Skript verwenden, überprüfen Sie das Skype Raum Systemen v2 Setup.</span><span class="sxs-lookup"><span data-stu-id="cb262-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="cb262-111">(Siehe Konto Überprüfungsskript).</span><span class="sxs-lookup"><span data-stu-id="cb262-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="cb262-112">Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cb262-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="cb262-113">Bevor Sie Skype Raum Systemen v2 mit Exchange lokal bereitstellen, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="cb262-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="cb262-114">Weitere Informationen finden Sie unter [Skype Raum Systemen v2 Requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb262-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="cb262-115">Wenn Sie Skype Raum Systemen v2 mit Exchange lokal bereitstellen, werden Sie Active Directory-Verwaltungstools verwenden, um eine e-Mail-Adresse für Ihr Konto der lokalen Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cb262-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="cb262-116">Dieses Konto wird mit Office 365 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb262-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="cb262-117">Sie müssen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cb262-117">You will need to:</span></span>
  
- <span data-ttu-id="cb262-118">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb262-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="cb262-119">Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="cb262-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="cb262-120">Zuweisen einer Office 365-Lizenzvertrags.</span><span class="sxs-lookup"><span data-stu-id="cb262-120">Assign an Office 365 license.</span></span>
    
- <span data-ttu-id="cb262-121">Aktivieren Sie das Gerät Konto mit Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="cb262-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="cb262-122">Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="cb262-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="cb262-123">Sie müssen Ihre Office 365-Plan Skype für Business Online (Plan 2) oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="cb262-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="cb262-124">Der Plan muss die Konferenzfunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cb262-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="cb262-125">Wenn Sie Enterprise-VoIP (PSTN-Telefonie) benötigen benötigen Telefoniedienstanbieter für Skype Raum Systemen v2 verwenden Sie Skype für Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="cb262-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="cb262-126">Die Mandanten-Benutzer müssen Exchange-Postfächer haben.</span><span class="sxs-lookup"><span data-stu-id="cb262-126">Your tenant users must have Exchange mailboxes.</span></span>
    
  - <span data-ttu-id="cb262-127">Ihr Skype Raum Systemen v2 Konto erfordert einen Skype für Business Online (Plan 2) oder Skype für Business Online (Plan 3)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb262-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="cb262-128">Ihr Skype Raum Systemen v2 Konto einen Skype für Business Server-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cb262-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="cb262-129">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb262-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="cb262-130">Im **Active Directory-Benutzer und-Computer AD** -Tool mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, dass die Skype Raum Systeme v2-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="cb262-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="cb262-p106">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cb262-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="cb262-p107">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb262-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb262-136">Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="cb262-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="cb262-137">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="cb262-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="cb262-138">In diesem Fall müssen Sie eine Ausnahme für jedes Skype Raum Systemen v2 Gerät Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb262-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="cb262-139">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="cb262-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="cb262-140">Wenn es abgeschlossen ist, wechseln Sie zu der Benutzerseite in Ihrer Office 365 Administrationscenter, und stellen Sie sicher, dass das Konto in den vorherigen Schritten erstellten online zu zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb262-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="cb262-141">Aktivieren des Remotepostfachs und Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb262-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="cb262-142">Aktivieren Sie das Remotepostfach, indem Ihre lokale Exchange-Verwaltungsshell mit Administratorberechtigungen öffnen, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="cb262-142">Enable the remote mailbox by opening your on-premises Exchange management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="cb262-143">Eine remote Windows PowerShell-Sitzung starten und eine Verbindung mit Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="cb262-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="cb262-144">Führen Sie von Ihrem Office 365-Mandanten die folgenden Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="cb262-144">From your Office 365 tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="cb262-145">Um der Besprechung zu optimieren, benötigen Sie die Exchange-Eigenschaften für das Gerät-Konto wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="cb262-145">To improve the meeting experience, you'll need to set the Exchange properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="cb262-146">Weitere Informationen über welche Eigenschaften Sie festlegen müssen, finden Sie unter Exchange-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="cb262-146">For more information about which properties you need to set, see Exchange properties.</span></span>
    
4. <span data-ttu-id="cb262-147">Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure AD herstellen.</span><span class="sxs-lookup"><span data-stu-id="cb262-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="cb262-148">Sie können diesen Befehl ausführen, um die Verbindung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="cb262-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="cb262-149">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="cb262-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="cb262-150">Das Gerät Konto muss eine gültige Office 365-Lizenz, um sicherzustellen, dass Exchange und Skype für Business Server funktioniert haben.</span><span class="sxs-lookup"><span data-stu-id="cb262-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="cb262-151">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="cb262-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="cb262-152">Im nächsten Schritt verwenden Sie Get-MsolAccountSku, um eine Liste der verfügbaren SKUs für Office 365-Mandanten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cb262-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="cb262-p113">Wenn Sie die SKUs aufgelistet haben, können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="cb262-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="cb262-155">Aktivieren des Gerätekontos in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cb262-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="cb262-156">Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cb262-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="cb262-157">Führen Sie diesen Befehl, um Ihr Skype Raum Systemen v2-Konto für Skype für Business Server zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="cb262-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="cb262-158">Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einer vorhandenen Skype für Business Server-Benutzer, die mit diesem Befehl abrufen.</span><span class="sxs-lookup"><span data-stu-id="cb262-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="cb262-159">Zuweisen einer Skype for Business-Lizenz zu Ihrem Skype Room Systems v2-Konto</span><span class="sxs-lookup"><span data-stu-id="cb262-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="cb262-160">Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="cb262-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="cb262-161">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="cb262-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="cb262-162">Klicken Sie auf das Konto Skype Raum Systemen v2, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb262-162">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="cb262-163">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="cb262-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="cb262-164">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="cb262-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="cb262-165">Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP für Ihre Skype Raum Systemen v2 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cb262-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="cb262-166">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cb262-166">Click **Save**.</span></span>
    
<span data-ttu-id="cb262-167">Für die Validierung sollten Sie alle Skype für Business-Client verwenden Sie dieses Konto anzumelden sein.</span><span class="sxs-lookup"><span data-stu-id="cb262-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb262-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb262-168">See also</span></span>

#### 

[<span data-ttu-id="cb262-169">Planen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="cb262-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="cb262-170">Bereitstellen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="cb262-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="cb262-171">Konfigurieren einer Skype Raum Systemen v2-Konsole</span><span class="sxs-lookup"><span data-stu-id="cb262-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="cb262-172">Verwalten von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="cb262-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

