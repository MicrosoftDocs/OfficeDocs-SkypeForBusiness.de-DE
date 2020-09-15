---
title: Bereitstellen von Microsoft Teams-Räumen mit Exchange lokal
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen in einer Hybridumgebung mit Exchange lokal.
ms.openlocfilehash: 71b1ab2ba641b25764f5c546343a3c7a597f121a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814534"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="ddb3e-103">Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort</span><span class="sxs-lookup"><span data-stu-id="ddb3e-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="ddb3e-104">In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen in einer Hybridumgebung mit Exchange lokal und Microsoft Teams oder Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="ddb3e-105">Wenn Ihre Organisation über eine Kombination von Diensten verfügt, bei denen einige lokal gehostet werden und einige Online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="ddb3e-106">In diesem Thema werden hybridbereitstellungen für Microsoft Teams-Räume mit Exchange gehostet, die lokal gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="ddb3e-107">Da es so viele unterschiedliche Variationen bei dieser Art der Bereitstellung gibt, ist es nicht möglich, detaillierte Anweisungen für alle zu liefern.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="ddb3e-108">Das folgende Verfahren funktioniert für viele Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-108">The following process will work for many configurations.</span></span> <span data-ttu-id="ddb3e-109">Wenn der Prozess für Ihr Setup nicht richtig ist, empfehlen wir, dass Sie Windows PowerShell verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="ddb3e-110">Microsoft stellt [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)zur Verfügung, ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="ddb3e-111">Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ddb3e-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ddb3e-112">Requirements</span></span>

<span data-ttu-id="ddb3e-113">Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Exchange lokal bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="ddb3e-114">Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="ddb3e-115">Wenn Sie Microsoft Teams-Räume mit Exchange lokal bereitstellen, verwenden Sie die Active Directory-Verwaltungstools, um eine e-Mail-Adresse für Ihr lokales Domänenkonto hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="ddb3e-116">Dieses Konto wird mit Microsoft 365 oder Office 365 synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ddb3e-117">Sie müssen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-117">You will need to:</span></span>
  
- <span data-ttu-id="ddb3e-118">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="ddb3e-119">Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="ddb3e-120">Weisen Sie eine Microsoft 365-oder Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="ddb3e-121">Aktivieren Sie das Geräte Konto in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="ddb3e-122">Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="ddb3e-123">Sie müssen Skype for Business Online (Plan 2) oder höher in Ihrem Microsoft 365-oder Office 365-Plan haben.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="ddb3e-124">Der Plan muss die Konferenzfunktion unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="ddb3e-125">Wenn Sie Enterprise-VoIP (PSTN-Telefonie) mit Telefoniedienst-Anbietern für Microsoft Teams-Räume benötigen, benötigen Sie Skype for Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="ddb3e-126">Ihre Mandanten Benutzer müssen über Exchange-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="ddb3e-127">Für Ihr Microsoft Teams rooms-Konto ist eine Lizenz für Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) erforderlich, es ist jedoch keine Exchange Online-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="ddb3e-128">Weisen Sie Ihrem Microsoft Teams rooms-Konto eine Skype for Business Server-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="ddb3e-129">Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="ddb3e-130">Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in dem Ihre Microsoft Teams-Chatrooms-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="ddb3e-p107">Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="ddb3e-p108">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddb3e-136">Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business Server in Microsoft Teams-Räumen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="ddb3e-137">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ddb3e-138">Wenn dies der Fall ist, müssen Sie für jedes Microsoft Teams rooms-Geräte Konto eine Ausnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="ddb3e-139">Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ddb3e-140">Wenn Sie fertig sind, wechseln Sie zur Seite "Benutzer" im Microsoft 365 Admin Center, und überprüfen Sie, ob das in den vorherigen Schritten erstellte Konto mit Online verbunden wurde.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="ddb3e-141">Aktivieren des Remotepostfachs und Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ddb3e-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="ddb3e-142">[Öffnen Sie die Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) , oder stellen [Sie mithilfe von Remote-PowerShell eine Verbindung mit Ihrem Exchange-Server her](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="ddb3e-143">Erstellen Sie in Exchange PowerShell ein Postfach für das Konto (Postfach aktivieren Sie das Konto), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="ddb3e-144">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [aktivieren-Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="ddb3e-145">Konfigurieren Sie in Exchange PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="ddb3e-146">AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="ddb3e-147">AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="ddb3e-148">DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ddb3e-149">Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ddb3e-150">RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="ddb3e-151">AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="ddb3e-152">AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!"</span><span class="sxs-lookup"><span data-stu-id="ddb3e-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="ddb3e-153">(Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)</span><span class="sxs-lookup"><span data-stu-id="ddb3e-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="ddb3e-154">In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01 konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="ddb3e-155">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="ddb3e-156">Zuweisen einer Microsoft 365-oder Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="ddb3e-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="ddb3e-157">Stellen Sie eine Verbindung mit Azure Active Directory her.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="ddb3e-158">Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ddb3e-159">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="ddb3e-160">Das Geräte Konto muss über eine gültige Microsoft 365-oder Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="ddb3e-161">Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Geräte Konto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="ddb3e-162">Sie können `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="ddb3e-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="ddb3e-163">, um eine Liste der verfügbaren SKUs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="ddb3e-164">Als nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="ddb3e-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="ddb3e-165">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-165">cmdlet.</span></span> <span data-ttu-id="ddb3e-166">In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="ddb3e-167">Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddb3e-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="ddb3e-168">Aktivieren des Geräte Kontos</span><span class="sxs-lookup"><span data-stu-id="ddb3e-168">Enable the device account</span></span>

<span data-ttu-id="ddb3e-169">Skype for Business Online PowerShell wird verwendet, um Dienste für Microsoft Teams und Skype for Business Online zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="ddb3e-170">Erstellen Sie eine Windows PowerShell-Remotesitzung wie folgt von einem PC:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="ddb3e-171">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-171">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="ddb3e-172">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-172">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="ddb3e-173">SIP-Adresse des Kontos abrufen:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-173">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="ddb3e-174">Führen Sie den folgenden Befehl aus, um Ihr Microsoft Teams rooms-Konto zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-174">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="ddb3e-175">Wenn Sie nicht sicher sind, welchen Wert Sie für den RegistrarPool-Parameter in Ihrer Umgebung verwenden möchten, können Sie den Wert eines vorhandenen Benutzers mit diesem Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="ddb3e-175">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="ddb3e-176">Zuweisen einer Lizenz zu Ihrem Microsoft Teams rooms-Konto</span><span class="sxs-lookup"><span data-stu-id="ddb3e-176">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="ddb3e-177">Melden Sie sich als mandantenadministrator an, öffnen Sie das Microsoft 365 Admin Center, und klicken Sie auf die Administrator-app.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-177">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="ddb3e-178">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-178">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="ddb3e-179">Klicken Sie auf das Microsoft Teams rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-179">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="ddb3e-180">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-180">Click **Licenses**.</span></span>
5. <span data-ttu-id="ddb3e-181">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-181">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ddb3e-182">Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP in Ihren Microsoft Teams-Räumen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-182">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="ddb3e-183">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-183">Click **Save**.</span></span>

<span data-ttu-id="ddb3e-184">Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Client bei diesem Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ddb3e-184">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ddb3e-185">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ddb3e-185">Related topics</span></span>

[<span data-ttu-id="ddb3e-186">Konfigurieren von Konten für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="ddb3e-186">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="ddb3e-187">Plan für Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="ddb3e-187">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="ddb3e-188">Bereitstellen von Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="ddb3e-188">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="ddb3e-189">Konfigurieren einer Konsole für Microsoft Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="ddb3e-189">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="ddb3e-190">Microsoft Teams-Räume verwalten</span><span class="sxs-lookup"><span data-stu-id="ddb3e-190">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
