---
title: Bereitstellen von Microsoft Teams-Raum mit Exchange online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online.
ms.openlocfilehash: e53fd2ebd25ef6b625ada84b60d58e42e8c13a28
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628421"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="beae3-103">Bereitstellen von Microsoft Teams-Raum mit Exchange online</span><span class="sxs-lookup"><span data-stu-id="beae3-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="beae3-104">In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online und Skype for Business Server lokal.</span><span class="sxs-lookup"><span data-stu-id="beae3-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="beae3-105">Wenn Ihre Organisation über eine Kombination von Diensten verfügt, bei denen einige lokal gehostet werden und einige Online gehostet werden, hängt Ihre Konfiguration davon ab, wo die einzelnen Dienste gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="beae3-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="beae3-106">In diesem Thema werden hybridbereitstellungen für Microsoft Teams-Räume mit Exchange Hosted Online behandelt.</span><span class="sxs-lookup"><span data-stu-id="beae3-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="beae3-107">Da es so viele unterschiedliche Variationen bei dieser Art der Bereitstellung gibt, ist es nicht möglich, detaillierte Anweisungen für alle zu liefern.</span><span class="sxs-lookup"><span data-stu-id="beae3-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="beae3-108">Das folgende Verfahren funktioniert für viele Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="beae3-108">The following process will work for many configurations.</span></span> <span data-ttu-id="beae3-109">Wenn der Prozess für Ihr Setup nicht richtig ist, empfehlen wir, dass Sie Windows PowerShell verwenden, um dasselbe Endergebnis wie hier dokumentiert zu erzielen, und für andere Bereitstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="beae3-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="beae3-110">Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht darin, Sie mithilfe der Windows PowerShell-Remotekonfiguration zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="beae3-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="beae3-111">Microsoft bietet [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, mit dem Sie neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten überprüfen können, damit Sie Sie zu kompatiblen Microsoft Teams rooms-Benutzerkonten machen können.</span><span class="sxs-lookup"><span data-stu-id="beae3-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="beae3-112">Wenn Sie möchten, können Sie die folgenden Schritte ausführen, um die Konten zu konfigurieren, die von Ihrem Microsoft Teams rooms-Gerät verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="beae3-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="beae3-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="beae3-113">Requirements</span></span>

<span data-ttu-id="beae3-114">Bevor Sie Microsoft Teams-Räume mit Exchange Online bereitstellen, müssen Sie sicherstellen, dass Sie die Anforderungen erfüllt haben.</span><span class="sxs-lookup"><span data-stu-id="beae3-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="beae3-115">Weitere Informationen finden Sie unter [Anforderungen für Microsoft Teams-Chatrooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beae3-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="beae3-116">Zum Bereitstellen von Microsoft Teams-Räumen mit Exchange Online führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="beae3-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="beae3-117">Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.</span><span class="sxs-lookup"><span data-stu-id="beae3-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="beae3-118">Das [Azure Active Directory-Modul für Windows PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in diesem Abschnitt (beispielsweise "MsolUser") wurden beim Einrichten von Konten für Microsoft Teams rooms-Geräte getestet.</span><span class="sxs-lookup"><span data-stu-id="beae3-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="beae3-119">Es ist möglich, dass andere Cmdlets funktionieren, jedoch in diesem speziellen Szenario nicht getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="beae3-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="beae3-120">Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="beae3-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="beae3-121">Starten Sie eine Windows PowerShell-Remotesitzung auf einem PC, und stellen Sie eine Verbindung mit Exchange Online wie folgt her:</span><span class="sxs-lookup"><span data-stu-id="beae3-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="beae3-122">Nach dem Einrichten einer Sitzung erstellen Sie entweder ein neues Postfach und aktivieren es als RoomMailboxAccount, oder Sie können die Einstellungen für ein vorhandenes Raumpostfach ändern.</span><span class="sxs-lookup"><span data-stu-id="beae3-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="beae3-123">Dadurch kann sich das Konto bei Microsoft Teams-Räumen authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="beae3-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="beae3-124">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="beae3-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="beae3-125">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="beae3-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="beae3-126">Um die Besprechungs Erfahrung zu verbessern, müssen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festzulegen:</span><span class="sxs-lookup"><span data-stu-id="beae3-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="beae3-127">Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto</span><span class="sxs-lookup"><span data-stu-id="beae3-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="beae3-128">Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Container oder die Organisationseinheit, in dem Ihre Microsoft Teams-Chatrooms-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="beae3-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="beae3-129">Geben Sie den Anzeigenamen (-Identity) aus dem vorherigen Cmdlet (Satz-Postfach oder neues Postfach) im Feld **Vollständiger Name** und dem Alias in das Feld **Benutzeranmeldename** ein.</span><span class="sxs-lookup"><span data-stu-id="beae3-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="beae3-130">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="beae3-130">Click **Next**.</span></span>
3. <span data-ttu-id="beae3-p108">Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="beae3-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="beae3-134">Die Auswahl von " **Kennwort läuft nie ab** " ist eine Voraussetzung für Skype for Business Server in Microsoft Teams-Räumen.</span><span class="sxs-lookup"><span data-stu-id="beae3-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="beae3-135">Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="beae3-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="beae3-136">In diesem Fall müssen Sie für jedes Microsoft Teams rooms-Benutzerkonto eine Ausnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="beae3-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="beae3-137">Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="beae3-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="beae3-138">Nachdem Sie das Konto erstellt haben, führen Sie eine Verzeichnissynchronisierung aus.</span><span class="sxs-lookup"><span data-stu-id="beae3-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="beae3-139">Dies kann mithilfe von " [MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) " in PowerShell erfolgen.</span><span class="sxs-lookup"><span data-stu-id="beae3-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="beae3-140">Wenn dies abgeschlossen ist, wechseln Sie zur Seite "Benutzer", und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="beae3-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="beae3-141">Zuweisen einer Office 365-Lizenz</span><span class="sxs-lookup"><span data-stu-id="beae3-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="beae3-142">Stellen Sie zunächst eine Verbindung mit Azure AD her, um einige Kontoeinstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="beae3-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="beae3-143">Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="beae3-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="beae3-144">Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="beae3-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="beae3-145">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="beae3-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="beae3-146">Das Benutzerkonto muss über eine gültige Office 365-Lizenz verfügen, um sicherzustellen, dass Exchange und Skype for Business Server funktionieren.</span><span class="sxs-lookup"><span data-stu-id="beae3-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="beae3-147">Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Benutzerkonto einen Verwendungsstandort zuweisen, um festzustellen, welche Lizenz-SKUs für Ihr Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="beae3-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="beae3-148">Sie führen die Aufgabe in einem der folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="beae3-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="beae3-149">Verwenden Sie als nächstes`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="beae3-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="beae3-150">, um eine Liste der verfügbaren SKUs für Ihren Office 365-Mandanten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="beae3-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="beae3-151">Nachdem Sie die SKUs aufgelistet haben, können Sie eine Lizenz mit dem`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="beae3-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="beae3-152">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="beae3-152">cmdlet.</span></span> <span data-ttu-id="beae3-153">In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="beae3-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
      Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="beae3-154">Aktivieren des Benutzerkontos mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="beae3-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="beae3-155">Erstellen Sie eine Windows PowerShell-Remotesitzung wie folgt von einem PC:</span><span class="sxs-lookup"><span data-stu-id="beae3-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="beae3-156">Führen Sie den folgenden Befehl aus, um Ihr Microsoft Teams rooms-Konto für Skype for Business Server zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="beae3-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="beae3-157">Wenn Sie nicht sicher sind, welchen Wert Sie für den RegistrarPool-Parameter in Ihrer Umgebung verwenden sollen, können Sie den Wert eines vorhandenen Skype for Business Server-Benutzers über diesen Befehl abrufen.</span><span class="sxs-lookup"><span data-stu-id="beae3-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="beae3-158">Zuweisen einer Skype for Business Server-Lizenz zum Microsoft Teams rooms-Konto</span><span class="sxs-lookup"><span data-stu-id="beae3-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="beae3-159">Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365-Verwaltungs Portal, und klicken Sie auf die Administrator-app.</span><span class="sxs-lookup"><span data-stu-id="beae3-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="beae3-160">Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.</span><span class="sxs-lookup"><span data-stu-id="beae3-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="beae3-161">Klicken Sie auf das Microsoft Teams rooms-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="beae3-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="beae3-162">Klicken Sie auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="beae3-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="beae3-163">Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus.</span><span class="sxs-lookup"><span data-stu-id="beae3-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="beae3-164">Sie müssen eine Plan 3-Lizenz verwenden, wenn Sie Enterprise-VoIP in Microsoft Teams-Räumen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="beae3-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="beae3-165">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="beae3-165">Click **Save**.</span></span>

<span data-ttu-id="beae3-166">Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei diesem Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="beae3-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="beae3-167">Wenn Sie derzeit E1-, E3-, E4-oder E5-SKUs mit Skype for Business Plan 2 mit Audiokonferenzen oder mit dem Office 365-Telefon System und einem Anrufplan verwenden, werden diese weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="beae3-167">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Office 365 Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="beae3-168">Sie sollten jedoch in der Lage sein, ein einfacheres Lizenzierungsmodell zu verwenden, wie es in Teams für die [Lizenzierung von Besprechungsräumen](rooms-licensing.md)beschrieben wird, nachdem aktuelle Lizenzen abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="beae3-168">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beae3-169">Wenn Sie Skype for Business Plan 2 verwenden, können Sie die Microsoft Teams-Räume nur im Skype for Business-Modus verwenden, was bedeutet, dass alle Ihre Besprechungen Skype for Business-Besprechungen sind.</span><span class="sxs-lookup"><span data-stu-id="beae3-169">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="beae3-170">Um Ihren Besprechungsraum für Microsoft Teams-Besprechungen zu aktivieren, empfehlen wir, die Lizenz für den Besprechungsraum zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="beae3-170">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="beae3-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beae3-171">See also</span></span>

[<span data-ttu-id="beae3-172">Konfigurieren von Konten für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="beae3-172">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="beae3-173">Planen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="beae3-173">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="beae3-174">Bereitstellen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="beae3-174">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="beae3-175">Konfigurieren einer Microsoft Teams rooms-Konsole</span><span class="sxs-lookup"><span data-stu-id="beae3-175">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="beae3-176">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="beae3-176">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
