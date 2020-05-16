---
title: Erstellen von Microsoft Teams-Ressourcenkonten für Zusammenarbeits leisten für Microsoft Teams mithilfe von PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Zusammenarbeits leisten für Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268052"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="75a11-103">Erstellen eines Microsoft 365-Ressourcenkontos mithilfe der PowerShell</span><span class="sxs-lookup"><span data-stu-id="75a11-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="75a11-104">In diesem Thema finden Sie Informationen zum Erstellen von Ressourcenkonten für Zusammenarbeits Balken für Microsoft Teams mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75a11-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="75a11-105">Die einfachste Möglichkeit zum Erstellen eines Ressourcenkontos ist die Verwendung des Microsoft 365 admin Centers.</span><span class="sxs-lookup"><span data-stu-id="75a11-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="75a11-106">[Weitere Informationen hierzu finden Sie in diesem Artikel](resource-account-ui.md).</span><span class="sxs-lookup"><span data-stu-id="75a11-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="75a11-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="75a11-107">Requirements</span></span>

<span data-ttu-id="75a11-108">Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Office 365 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75a11-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="75a11-109">Weitere Informationen finden Sie unter [Bereitstellen von Zusammenarbeits leisten für Microsoft Teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="75a11-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="75a11-110">Wenn Sie für die Zusammenarbeits Leiste PSTN-Funktionen benötigen, benötigen Sie eine Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="75a11-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="75a11-111">Ihre Ressourcenkonten müssen Exchange-Postfächer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75a11-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="75a11-112">Da es sich hierbei um Ressourcenkonten handelt, ist keine Exchange-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75a11-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="75a11-113">Wir empfehlen die Verwendung der Lizenz für Besprechungsräume für Ressourcenkonten.</span><span class="sxs-lookup"><span data-stu-id="75a11-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="75a11-114">Hinzufügen eines Ressourcenkontos</span><span class="sxs-lookup"><span data-stu-id="75a11-114">Add a resource account</span></span>

1. <span data-ttu-id="75a11-115">Stellen Sie eine Verbindung mit Exchange Online PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="75a11-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="75a11-116">Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="75a11-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="75a11-117">Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="75a11-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="75a11-118">Verwenden Sie die folgende Syntax, um ein neues Raumpostfach zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="75a11-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="75a11-119">In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="75a11-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="75a11-120">Name: drängen-Room-01</span><span class="sxs-lookup"><span data-stu-id="75a11-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="75a11-121">Alias: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="75a11-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="75a11-122">Konto: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75a11-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="75a11-123">Kontokennwort: P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="75a11-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="75a11-124">Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:</span><span class="sxs-lookup"><span data-stu-id="75a11-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="75a11-125">In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Alias Wert HuddleRoom02 aktiviert, und das Kennwort wird auf 808P@ $ $W 0rd festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75a11-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="75a11-126">Beachten Sie, dass das Konto aufgrund des vorhandenen Alias Werts HuddleRoom02@contoso.onmicrosoft.com wird.</span><span class="sxs-lookup"><span data-stu-id="75a11-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="75a11-127">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [festgelegtes Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="75a11-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="75a11-128">Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="75a11-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="75a11-129">AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)</span><span class="sxs-lookup"><span data-stu-id="75a11-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="75a11-130">AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="75a11-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="75a11-131">DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)</span><span class="sxs-lookup"><span data-stu-id="75a11-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="75a11-132">Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)</span><span class="sxs-lookup"><span data-stu-id="75a11-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="75a11-133">RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)</span><span class="sxs-lookup"><span data-stu-id="75a11-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="75a11-134">AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="75a11-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="75a11-135">AdditionalResponse: "dieser Raum verfügt über eine Kollaborations Leiste für Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="75a11-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="75a11-136">(Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)</span><span class="sxs-lookup"><span data-stu-id="75a11-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="75a11-137">In diesem Beispiel werden diese Einstellungen für das Room-Postfach mit dem Namen "Zusammendrängen-Raum-01" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="75a11-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="75a11-138">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="75a11-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="75a11-139">Stellen Sie eine Verbindung mit MS Online PowerShell her, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` PowerShell-Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75a11-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="75a11-140">Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="75a11-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="75a11-141">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75a11-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="75a11-142">Verwenden Sie die folgende Syntax, um das Kennwort für huddleroom01@contoso.onmicrosoft.com so zu ändern, dass es nicht abläuft:</span><span class="sxs-lookup"><span data-stu-id="75a11-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="75a11-143">Das Ressourcenkonto muss über eine gültige Office 365-Lizenz verfügen, vorzugsweise über die SKU des Besprechungsraums.</span><span class="sxs-lookup"><span data-stu-id="75a11-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="75a11-144">Sie müssen Ihrem Geräte Konto auch einen Verwendungsstandort zuweisen, der bestimmt, welche Lizenz SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="75a11-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="75a11-145">Sie können verwenden `Get-MsolAccountSku` , um eine Liste der verfügbaren SKUs für Ihren Office 365-Mandanten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="75a11-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="75a11-146">Sie können die Lizenz mithilfe von "Satz-MsolUserLicense" zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75a11-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="75a11-147">Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="75a11-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="75a11-148">Konfigurieren von Konten für Zusammenarbeits leisten für Microsoft Teams mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="75a11-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="75a11-149">Bereitstellen von Zusammenarbeits leisten für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75a11-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="75a11-150">Kollaborations leisten für Microsoft Teams-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="75a11-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


