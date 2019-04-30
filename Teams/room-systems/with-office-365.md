---
title: Bereitstellen von Microsoft-Teams, Räume mit Office 365
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Office 365.
ms.openlocfilehash: 16d0fad14bd52a13fa6735ec0b786cb15f3ce8c1
ms.sourcegitcommit: 728507d34031d01f663d9b551cd4794867244854
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467534"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="e8b26-103">Bereitstellen von Microsoft-Teams, Räume mit Office 365</span><span class="sxs-lookup"><span data-stu-id="e8b26-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="e8b26-104">Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Office 365, auf dem Microsoft-Teams oder Skype für Unternehmen und Exchange online sind.</span><span class="sxs-lookup"><span data-stu-id="e8b26-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="e8b26-105">Die einfachste Möglichkeit zum Einrichten von Benutzerkonten ist von remote Windows PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e8b26-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="e8b26-106">Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Microsoft Teams Räume-Benutzerkonten aktivieren überprüfen helfen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="e8b26-107">Auf Wunsch können Sie die Schritte unten, um das Konfigurieren von Konten, mit Ihrem Microsoft-Teams Chatrooms Gerät.</span><span class="sxs-lookup"><span data-stu-id="e8b26-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8b26-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e8b26-108">Requirements</span></span>

<span data-ttu-id="e8b26-109">Vor der Bereitstellung von Microsoft-Teams Chatrooms mit Office 365, achten Sie darauf, dass Sie die Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="e8b26-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="e8b26-110">Weitere Informationen finden Sie unter [Microsoft Teams Chatrooms Requirements](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b26-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="e8b26-111">Um Skype für Unternehmen zu aktivieren, müssen Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="e8b26-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="e8b26-112">Skype für Business Online (Plan 2 oder eines Plans für Enterprise-basierte) oder höher in Ihrem Office 365-Plan.</span><span class="sxs-lookup"><span data-stu-id="e8b26-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="e8b26-113">Der Plan muss Funktionen von einwahlkonferenzen können.</span><span class="sxs-lookup"><span data-stu-id="e8b26-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="e8b26-114">Wenn Sie eine Zugriffsnummer für Einwahl-Funktionen aus einer Besprechung benötigen, benötigen Sie eine Audiokonferenz und Telefonsystem Lizenz.</span><span class="sxs-lookup"><span data-stu-id="e8b26-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="e8b26-115">Wenn Sie Dial-Out-Funktionen aus einer Besprechung benötigen, benötigen Sie eine nationalen oder nationalen und internationalen aufrufen planen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="e8b26-116">Die Mandanten-Benutzer müssen Exchange-Postfächer haben.</span><span class="sxs-lookup"><span data-stu-id="e8b26-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="e8b26-117">Ihr Microsoft-Teams Chatrooms Konto erfordert mindestens einen Skype für Business Online (Plan 2)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e8b26-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="e8b26-118">Einzelheiten finden Sie unter [Microsoft Teams Chatrooms Lizenzen](skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="e8b26-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="e8b26-119">Ausführliche Informationen zum Skype für Business Online-Pläne finden Sie unter der [Skype für Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8b26-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="e8b26-120">Hinzufügen eines Gerätekontos</span><span class="sxs-lookup"><span data-stu-id="e8b26-120">Add a device account</span></span>

1. <span data-ttu-id="e8b26-121">Herstellen einer Verbindung mit Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b26-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="e8b26-122">Anweisungen finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="e8b26-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="e8b26-123">Erstellen Sie in Exchange Online PowerShell eine neue Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="e8b26-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="e8b26-124">Standardmäßig haben nicht raumpostfächer zugeordnete Konten, müssen Sie ein Konto hinzufügen, wenn Sie erstellen oder ändern ein raumpostfachs, das zur Authentifizierung mit Skype Raum Systemen v2 ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e8b26-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="e8b26-125">Verwenden Sie die folgende Syntax, um eine neue Raumpostfach zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e8b26-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="e8b26-126">In diesem Beispiel wird eine neue Raumpostfach mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="e8b26-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="e8b26-127">Name: Project-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="e8b26-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="e8b26-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="e8b26-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="e8b26-129">Konto: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e8b26-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="e8b26-130">Kennwort: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="e8b26-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="e8b26-131">Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:</span><span class="sxs-lookup"><span data-stu-id="e8b26-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="e8b26-132">Dieses Beispiel aktiviert das Konto für den vorhandenen Raumpostfach, das den Alias-Wert ProjectRigel02 hat, und legt das Kennwort auf 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="e8b26-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="e8b26-133">Beachten Sie, dass das Konto ProjectRigel02@contoso.onmicrosoft.com aufgrund der vorhandenen Aliaswert.</span><span class="sxs-lookup"><span data-stu-id="e8b26-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="e8b26-134">Informationen zur Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="e8b26-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="e8b26-135">Konfigurieren Sie die folgenden Einstellungen in Exchange Online PowerShell klicken Sie auf das Raumpostfach, um die Besprechung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="e8b26-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="e8b26-136">AutomateProcessing: AutoAccept (Besprechungsorganisatoren empfangen die Raum Reservierung Entscheidung direkt und ohne Eingreifen: freien = akzeptieren; gebucht = ablehnen.)</span><span class="sxs-lookup"><span data-stu-id="e8b26-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="e8b26-137">AddOrganizerToSubject: $false (Organisator der Besprechung wird nicht auf den Betreff der Besprechungsanfrage hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="e8b26-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="e8b26-138">DeleteComments: $false (beibehalten im Textkörper Nachricht eingehender Besprechungsanfragen.)</span><span class="sxs-lookup"><span data-stu-id="e8b26-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="e8b26-139">DeleteSubject: $false (Keep den Betreff der eingehenden Besprechungsanfragen).</span><span class="sxs-lookup"><span data-stu-id="e8b26-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="e8b26-140">RemovePrivateProperty: $false (stellt sicher das Flag ' Privat ', die vom Organisator Besprechung in der ursprünglichen Besprechung gesendet wurde anfordern bleibt wie angegeben).</span><span class="sxs-lookup"><span data-stu-id="e8b26-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="e8b26-141">AddAdditionalResponse: $true (der Text, durch den Parameter AdditionalResponse angegeben wird auf Besprechungsanfragen hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="e8b26-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="e8b26-142">AdditionalResponse: "Dies ist eine Skype Besprechungsraum!"</span><span class="sxs-lookup"><span data-stu-id="e8b26-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="e8b26-143">(Der zusätzliche Text, der auf die Besprechungsanfrage hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="e8b26-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="e8b26-144">In diesem Beispiel wird konfiguriert diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="e8b26-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="e8b26-145">Informationen zur Syntax und Parametern finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="e8b26-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="e8b26-146">Verbinden mit MS-Online-PowerShell zu Active Directory-Einstellungen durch Ausführen der `Connect-MsolService -Credential $cred` Powershell-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b26-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="e8b26-147">Ausführliche Informationen zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e8b26-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="e8b26-148">Wenn Sie nicht das Kennwort an, die ablaufen soll, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e8b26-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="e8b26-149">Dieses Beispiel legt das Kennwort für das Konto ProjectRigel01@contoso.onmicrosoft.com läuft nie ab.</span><span class="sxs-lookup"><span data-stu-id="e8b26-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="e8b26-150">Sie können auch eine Telefonnummer für das Konto festlegen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="e8b26-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="e8b26-151">Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Microsoft-Teams oder Skype für Unternehmen funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="e8b26-151">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="e8b26-152">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e8b26-153">Sie können`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="e8b26-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="e8b26-154">Um eine Liste der verfügbaren SKUs wie folgt für Ihre Office 365-Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="e8b26-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="e8b26-155">Sie können im nächsten Schritt fügen Sie eine Lizenz using der`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="e8b26-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="e8b26-156">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8b26-156">cmdlet.</span></span> <span data-ttu-id="e8b26-157">In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="e8b26-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="e8b26-158">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen, um die Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8b26-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="e8b26-159">Als Nächstes müssen Sie das Gerät Konto mit Skype für Unternehmen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e8b26-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="e8b26-160">Stellen Sie sicher, dass Ihre Umgebung die definiert in [Microsoft Teams Chatrooms Anforderungen](requirements.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e8b26-160">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="e8b26-161">Starten Sie einen remote [Windows PowerShell-Sitzung](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) wie folgt (unbedingt [Skype für Business Online-PowerShell-Komponenten zu installieren](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="e8b26-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="e8b26-162">Aktivieren Sie im nächsten Schritt Ihr Microsoft-Teams Chatrooms Konto für Skype für Business Server durch Ausführen des folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e8b26-162">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="e8b26-163">Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e8b26-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="e8b26-164">Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e8b26-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="e8b26-165">Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation.</span><span class="sxs-lookup"><span data-stu-id="e8b26-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="e8b26-166">Nachdem Sie Ihr Konto Microsoft Teams Chatrooms in Microsoft-Teams oder Skype für Business Online zu aktivieren, um die vorhergehenden Schritte abgeschlossen haben, müssen Sie Microsoft Teams Chatrooms Gerät eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-166">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="e8b26-167">Verwenden das administrative Office 365-Portal, weisen Sie entweder einen Skype für Business Online (Plan 2) oder eine Skype für Business Online (Plan 3)-Lizenz auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="e8b26-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="e8b26-168">Zuweisen einer Lizenz zu Ihrem Konto</span><span class="sxs-lookup"><span data-stu-id="e8b26-168">Assign a license to your account</span></span>

1. <span data-ttu-id="e8b26-169">Anmeldung als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="e8b26-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="e8b26-170">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="e8b26-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="e8b26-171">Wählen Sie das Microsoft-Teams Räume-Konto, und klicken Sie auf oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e8b26-171">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="e8b26-172">Klicken Sie auf die Option **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="e8b26-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="e8b26-173">Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie Skype für Business Online (Plan 2) oder Skype auswählen, für Business Online (Plan 3), je nach Ihrer Lizenzierung und was Sie entschieden haben, im Hinblick auf Enterprise-VoIP benötigen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="e8b26-174">Sie müssen eine Lizenz planen 3 verwenden, wenn Sie auf der Microsoft-Teams Chatrooms Cloud Nebenstellenanlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e8b26-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="e8b26-175">Minimal benötigen Sie CloudPBX für VoIP-Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="e8b26-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="e8b26-176">Konfigurieren Sie anschließend Hybrid-VoIP oder PSTN-Basis für die PSTN-Konnektivität-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="e8b26-177">Einzelheiten finden Sie unter [Microsoft Teams Chatrooms Lizenzen](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="e8b26-177">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="e8b26-178">Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="e8b26-179">Beispiel: Raum setup im Exchange Online und Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="e8b26-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="e8b26-180">Exchange Online PowerShell-Befehle:</span><span class="sxs-lookup"><span data-stu-id="e8b26-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="e8b26-181">Azure Active Directory-PowerShell-Befehle:</span><span class="sxs-lookup"><span data-stu-id="e8b26-181">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="e8b26-182">Skype für Business-PowerShell-Befehl:</span><span class="sxs-lookup"><span data-stu-id="e8b26-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="e8b26-183">Dadurch werden CloudPBX und PSTNCallingDomesticAndInternational hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e8b26-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="e8b26-184">Darüber hinaus müssen Sie die Admin-Benutzeroberfläche verwenden, um eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e8b26-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="e8b26-185">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="e8b26-185">Validate</span></span>

<span data-ttu-id="e8b26-186">Für die Validierung sollten Sie möglicherweise Skype für Business-Client verwenden, das Konto anmelden, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e8b26-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b26-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8b26-187">See also</span></span>

[<span data-ttu-id="e8b26-188">Konfigurieren von Konten für Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="e8b26-188">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="e8b26-189">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="e8b26-189">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="e8b26-190">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="e8b26-190">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="e8b26-191">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="e8b26-191">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="e8b26-192">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="e8b26-192">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="e8b26-193">Lizenzierung von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="e8b26-193">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
