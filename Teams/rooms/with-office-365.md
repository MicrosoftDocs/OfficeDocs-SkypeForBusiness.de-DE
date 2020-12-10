---
title: Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365, in denen Teams oder Skype for Business und Exchange Online sind.
ms.openlocfilehash: 4b5bd3967d3a1fcc8859cf4da8b039418819cb4e
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616889"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="32485-103">Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="32485-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="32485-104">In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365, in denen Microsoft Teams oder Skype for Business und Exchange Online sind.</span><span class="sxs-lookup"><span data-stu-id="32485-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="32485-105">Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht darin, Sie mithilfe der Windows PowerShell-Remotekonfiguration zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32485-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="32485-106">Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)zur Verfügung, ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können.</span><span class="sxs-lookup"><span data-stu-id="32485-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="32485-107">Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32485-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="32485-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="32485-108">Requirements</span></span>

<span data-ttu-id="32485-109">Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Microsoft 365 oder Office 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="32485-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="32485-110">Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32485-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="32485-111">Damit Sie Skype for Business aktivieren können, müssen Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="32485-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="32485-112">Skype for Business Online (Plan 2 oder ein Unternehmens basierter Plan) oder höher in Ihrem Microsoft 365-oder Office 365-Plan.</span><span class="sxs-lookup"><span data-stu-id="32485-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="32485-113">Der Plan muss Funktionen für Einwahlkonferenzen zulassen.</span><span class="sxs-lookup"><span data-stu-id="32485-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="32485-114">Wenn Sie in einer Besprechung Einwahl Funktionen benötigen, benötigen Sie eine Audiokonferenz-und Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="32485-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="32485-115">Wenn Sie aus einer Besprechung heraus Wählfunktionen benötigen, benötigen Sie eine Audiokonferenz-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="32485-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="32485-116">Ihre Mandanten Benutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="32485-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="32485-117">Für Ihr Microsoft Teams rooms-Konto ist mindestens eine Lizenz für Skype for Business Online (Plan 2) erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32485-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="32485-118">Weitere Informationen finden Sie unter [Microsoft Teams rooms-Lizenzen](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="32485-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="32485-119">Einzelheiten zu den Skype for Business Online-Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="32485-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="32485-120">Hinzufügen eines Gerätekontos</span><span class="sxs-lookup"><span data-stu-id="32485-120">Add a device account</span></span>

1. <span data-ttu-id="32485-121">Stellen Sie eine Verbindung mit Exchange Online PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="32485-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="32485-122">Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="32485-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="32485-123">Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="32485-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="32485-124">Standardmäßig verfügen Raumpostfächer nicht über zugeordnete Konten, sodass Sie ein Konto hinzufügen müssen, wenn Sie ein Raumpostfach erstellen oder ändern, das es ermöglicht, sich bei Skype Room Systems v2 zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="32485-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="32485-125">Verwenden Sie die folgende Syntax, um ein neues Raumpostfach zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="32485-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="32485-126">In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="32485-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="32485-127">Name: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="32485-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="32485-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="32485-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="32485-129">Konto: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="32485-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="32485-130">Kontokennwort: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="32485-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="32485-131">Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:</span><span class="sxs-lookup"><span data-stu-id="32485-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="32485-132">In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Alias Wert Rigel2 aktiviert, und das Kennwort wird auf 9898P@ $ $W 0rd festgelegt.</span><span class="sxs-lookup"><span data-stu-id="32485-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="32485-133">Beachten Sie, dass das Konto aufgrund des vorhandenen Alias Werts Rigel2@contoso.onmicrosoft.com wird.</span><span class="sxs-lookup"><span data-stu-id="32485-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="32485-134">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [festgelegtes Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="32485-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="32485-135">Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="32485-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="32485-136">AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)</span><span class="sxs-lookup"><span data-stu-id="32485-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="32485-137">AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="32485-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="32485-138">DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)</span><span class="sxs-lookup"><span data-stu-id="32485-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="32485-139">Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)</span><span class="sxs-lookup"><span data-stu-id="32485-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="32485-140">RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)</span><span class="sxs-lookup"><span data-stu-id="32485-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="32485-141">AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="32485-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="32485-142">AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!"</span><span class="sxs-lookup"><span data-stu-id="32485-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="32485-143">(Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)</span><span class="sxs-lookup"><span data-stu-id="32485-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="32485-144">In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Rigel-01 konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="32485-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="32485-145">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="32485-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="32485-146">Stellen Sie eine Verbindung mit MS Online PowerShell her, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` PowerShell-Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="32485-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="32485-147">Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="32485-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="32485-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="32485-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="32485-149">Wenn Sie nicht möchten, dass das Kennwort abläuft, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="32485-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="32485-150">In diesem Beispiel wird das Kennwort für das Konto Rigel1@contoso.onmicrosoft.com so festgelegt, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="32485-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="32485-151">Sie können auch eine Telefonnummer für das Konto einrichten, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="32485-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="32485-152">Das Geräte Konto muss über eine gültige Microsoft 365-oder Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams oder Skype for Business funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="32485-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="32485-153">Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Geräte Konto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="32485-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="32485-154">Sie können `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="32485-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="32485-155">So rufen Sie eine Liste der verfügbaren SKUs für Ihre Microsoft 365-oder Office 365-Organisation wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="32485-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="32485-156">Als nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="32485-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="32485-157">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="32485-157">cmdlet.</span></span> <span data-ttu-id="32485-158">In diesem Beispiel wird die Besprechungsraum-Lizenz dem Konto hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="32485-158">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="32485-159">Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="32485-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="32485-160">Sie können diesem Konto auch Telefon System Funktionen hinzufügen, die Sie aber zuerst konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="32485-160">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="32485-161">Weitere Informationen finden Sie unter [Was ist Telefon System?](../what-is-phone-system-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="32485-161">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="32485-162">In diesem Beispiel wird der PSTN-Plan für Inlands-und Auslandsanrufe hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="32485-162">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="32485-163">Als nächstes müssen Sie das Geräte Konto in Skype for Business aktivieren.</span><span class="sxs-lookup"><span data-stu-id="32485-163">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="32485-164">Stellen Sie sicher, dass Ihre Umgebung die Anforderungen erfüllt, die in den [Microsoft Teams-Chatrooms](requirements.md)festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="32485-164">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="32485-165">Starten Sie eine [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) -Remotesitzung wie folgt (stellen Sie sicher, dass Sie die [Skype for Business Online PowerShell-Komponenten installieren](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="32485-165">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="32485-166">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="32485-166">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="32485-167">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="32485-167">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="32485-168">Beziehen Sie die RegistrarPool-Informationen aus dem neu eingerichteten Benutzerkonto, wie in diesem Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="32485-168">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="32485-169">Aktivieren Sie als nächstes das Microsoft Teams rooms-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="32485-169">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="32485-170">Neue Benutzerkonten werden möglicherweise nicht im gleichen Registrierungspool wie vorhandene Benutzerkonten im Mandanten erstellt.</span><span class="sxs-lookup"><span data-stu-id="32485-170">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="32485-171">Der obige Befehl verhindert aufgrund dieser Situation Fehler beim Einrichten des Kontos.</span><span class="sxs-lookup"><span data-stu-id="32485-171">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="32485-172">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="32485-172">Validate</span></span>

<span data-ttu-id="32485-173">Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei dem von Ihnen erstellten Konto anzumeldet.</span><span class="sxs-lookup"><span data-stu-id="32485-173">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="32485-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32485-174">See also</span></span>

[<span data-ttu-id="32485-175">Konfigurieren von Konten für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="32485-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="32485-176">Plan für Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="32485-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="32485-177">Bereitstellen von Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="32485-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="32485-178">Konfigurieren einer Konsole für Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="32485-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="32485-179">Microsoft Teams-Räume verwalten</span><span class="sxs-lookup"><span data-stu-id="32485-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="32485-180">Lizenzierung von Microsoft Teams rooms</span><span class="sxs-lookup"><span data-stu-id="32485-180">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
