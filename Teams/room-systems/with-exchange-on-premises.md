---
title: Bereitstellen von Microsoft-Teams Chatrooms mit Exchange lokal
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms in einer hybridumgebung mit Exchange lokal.
ms.openlocfilehash: 6975d64de9353cb17817c96d18a0bc0c8440602c
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362852"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="2e361-103">Bereitstellen von Microsoft-Teams Chatrooms mit Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="2e361-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="2e361-104">Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms in einer hybridumgebung mit Exchange auf lokale und Microsoft-Teams oder Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="2e361-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="2e361-105">Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2e361-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="2e361-106">In diesem Thema werden die hybridbereitstellungen für Microsoft-Teams Chatrooms mit Exchange lokal gehostet.</span><span class="sxs-lookup"><span data-stu-id="2e361-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="2e361-107">Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2e361-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="2e361-108">Der folgende Prozess wird für viele Konfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e361-108">The following process will work for many configurations.</span></span> <span data-ttu-id="2e361-109">Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="2e361-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="2e361-110">Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Microsoft Teams Räume-Benutzerkonten aktivieren überprüfen helfen.</span><span class="sxs-lookup"><span data-stu-id="2e361-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="2e361-111">Auf Wunsch können Sie die Schritte unten, um das Konfigurieren von Konten, mit Ihrem Microsoft-Teams Chatrooms Gerät.</span><span class="sxs-lookup"><span data-stu-id="2e361-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2e361-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2e361-112">Requirements</span></span>

<span data-ttu-id="2e361-113">Vor der Bereitstellung von Microsoft-Teams Chatrooms mit Exchange lokal, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="2e361-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="2e361-114">Weitere Informationen finden Sie unter [Microsoft Teams Chatrooms Requirements](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e361-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="2e361-115">Wenn Sie Microsoft-Teams Chatrooms mit Exchange lokal bereitgestellt werden, werden Sie Active Directory-Verwaltungstools verwenden, um eine e-Mail-Adresse für Ihr Konto der lokalen Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e361-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="2e361-116">Dieses Konto wird mit Office 365 synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e361-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="2e361-117">Sie müssen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2e361-117">You will need to:</span></span>
  
- <span data-ttu-id="2e361-118">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e361-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="2e361-119">Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="2e361-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="2e361-120">Zuweisen einer Office 365-Lizenzvertrags.</span><span class="sxs-lookup"><span data-stu-id="2e361-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="2e361-121">Aktivieren Sie das Gerät Konto mit Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="2e361-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="2e361-122">Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2e361-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="2e361-123">Sie müssen Ihre Office 365-Plan Skype für Business Online (Plan 2) oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="2e361-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="2e361-124">Der Plan muss die Konferenzfunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2e361-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="2e361-125">Wenn Sie Enterprise-VoIP (PSTN-Telefonie) benötigen benötigen Telefoniedienstanbieter für Microsoft-Teams Chatrooms verwenden Sie Skype für Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="2e361-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="2e361-126">Die Mandanten-Benutzer müssen Exchange-Postfächer haben.</span><span class="sxs-lookup"><span data-stu-id="2e361-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="2e361-127">Ihr Microsoft-Teams Chatrooms Konto erfordert einen Skype für Business Online (Plan 2) oder Skype für Business Online (Plan 3)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e361-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="2e361-128">Weisen Sie Ihr Konto Microsoft Teams Chatrooms einen Skype für Business Server-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="2e361-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="2e361-129">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e361-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="2e361-130">Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, dass Ihre Microsoft Teams Räume-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2e361-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="2e361-p107">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2e361-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="2e361-p108">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2e361-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e361-136">Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Microsoft Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="2e361-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="2e361-137">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="2e361-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="2e361-138">In diesem Fall müssen Sie eine Ausnahme für jedes Microsoft Teams Chatrooms Gerät Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e361-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="2e361-139">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="2e361-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="2e361-140">Wenn es abgeschlossen ist, wechseln Sie zu der Benutzerseite in Ihrer Office 365 Administrationscenter, und stellen Sie sicher, dass das Konto in den vorherigen Schritten erstellten online zu zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2e361-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="2e361-141">Aktivieren des Remotepostfachs und Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e361-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="2e361-142">[Öffnen Sie die Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder [eine Verbindung mit Exchange-Server mit remote-PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e361-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="2e361-143">Erstellen Sie ein Postfach für das Konto (postfachaktivierung das Konto) in Exchange PowerShell mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="2e361-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="2e361-144">Informationen zur Syntax und Parametern finden Sie unter [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="2e361-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="2e361-145">Konfigurieren Sie die folgenden Einstellungen in der Exchange PowerShell klicken Sie auf das Raumpostfach, um die Besprechung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="2e361-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="2e361-146">AutomateProcessing: AutoAccept (Besprechungsorganisatoren empfangen die Raum Reservierung Entscheidung direkt und ohne Eingreifen: freien = akzeptieren; gebucht = ablehnen.)</span><span class="sxs-lookup"><span data-stu-id="2e361-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="2e361-147">AddOrganizerToSubject: $false (Organisator der Besprechung wird nicht auf den Betreff der Besprechungsanfrage hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="2e361-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="2e361-148">DeleteComments: $false (beibehalten im Textkörper Nachricht eingehender Besprechungsanfragen.)</span><span class="sxs-lookup"><span data-stu-id="2e361-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2e361-149">DeleteSubject: $false (Keep den Betreff der eingehenden Besprechungsanfragen).</span><span class="sxs-lookup"><span data-stu-id="2e361-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2e361-150">RemovePrivateProperty: $false (stellt sicher das Flag ' Privat ', die vom Organisator Besprechung in der ursprünglichen Besprechung gesendet wurde anfordern bleibt wie angegeben).</span><span class="sxs-lookup"><span data-stu-id="2e361-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="2e361-151">AddAdditionalResponse: $true (der Text, durch den Parameter AdditionalResponse angegeben wird auf Besprechungsanfragen hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="2e361-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="2e361-152">AdditionalResponse: "Dies ist eine Skype Besprechungsraum!"</span><span class="sxs-lookup"><span data-stu-id="2e361-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="2e361-153">(Der zusätzliche Text, der auf die Besprechungsanfrage hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="2e361-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="2e361-154">In diesem Beispiel wird konfiguriert diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="2e361-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="2e361-155">Informationen zur Syntax und Parametern finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="2e361-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="2e361-156">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="2e361-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="2e361-157">Verbinden Sie mit Azure Active Directory-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e361-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="2e361-158">Anweisungen finden Sie unter [Verbindung herstellen mit Azure Active Directory PowerShell Graph-Modul](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="2e361-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="2e361-159">Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Microsoft-Teams, funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="2e361-159">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="2e361-160">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2e361-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="2e361-161">Sie können`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="2e361-161">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="2e361-162">Um eine Liste der verfügbaren SKUs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2e361-162">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="2e361-163">Sie können im nächsten Schritt fügen Sie eine Lizenz using der`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="2e361-163">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="2e361-164">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2e361-164">cmdlet.</span></span> <span data-ttu-id="2e361-165">In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="2e361-165">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="2e361-166">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen, um die Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e361-166">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="2e361-167">Aktivieren Sie das Gerät-Konto</span><span class="sxs-lookup"><span data-stu-id="2e361-167">Enable the device account</span></span>

<span data-ttu-id="2e361-168">Skype für Business Online PowerShell wird verwendet, um die Dienste für Microsoft-Teams und Skype für Business Online zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2e361-168">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="2e361-169">Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e361-169">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="2e361-170">Um Ihr Konto Microsoft Teams Räume zu aktivieren, führen Sie diesen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2e361-170">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="2e361-171">Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einen vorhandenen Benutzer mit diesem Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="2e361-171">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="2e361-172">Weisen Sie eine Lizenz mit Ihrem Microsoft-Teams Räume-Konto</span><span class="sxs-lookup"><span data-stu-id="2e361-172">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="2e361-173">Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="2e361-173">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="2e361-174">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="2e361-174">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="2e361-175">Klicken Sie auf der Microsoft-Teams Räume-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e361-175">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="2e361-176">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="2e361-176">Click **Licenses**.</span></span>
5. <span data-ttu-id="2e361-177">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="2e361-177">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="2e361-178">Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP auf Ihrem Microsoft-Teams Chatrooms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2e361-178">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="2e361-179">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e361-179">Click **Save**.</span></span>

<span data-ttu-id="2e361-180">Für die Validierung sollten Sie alle Clients verwenden Sie dieses Konto anzumelden sein.</span><span class="sxs-lookup"><span data-stu-id="2e361-180">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e361-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e361-181">See also</span></span>

[<span data-ttu-id="2e361-182">Konfigurieren von Konten für Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="2e361-182">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="2e361-183">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="2e361-183">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="2e361-184">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="2e361-184">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="2e361-185">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="2e361-185">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="2e361-186">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="2e361-186">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
