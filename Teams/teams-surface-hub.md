---
title: Bereitstellen von Microsoft-Teams für die Fläche Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren von Admin-Einstellungen für Microsoft-Teams für Fläche Hub.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192180"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="7ac32-103">Bereitstellen von Microsoft-Teams für die Fläche Hub</span><span class="sxs-lookup"><span data-stu-id="7ac32-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="7ac32-104">Vor der Bereitstellung von Microsoft-Teams für Microsoft Surface Hub Achten Sie darauf, dass Sie die Hardware, Betriebssystem und andere Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="7ac32-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="7ac32-105">Weitere Informationen finden Sie im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="7ac32-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="7ac32-106">Einrichten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="7ac32-106">Set up user accounts</span></span>
 
<span data-ttu-id="7ac32-107">Erstellen Sie zum Einrichten von Benutzerkonten, die mit den Teams für Fläche Hub verwendet werden kann das Gerät Konto wie für die Unterstützung bei Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="7ac32-108">Das Gerät Konto benötigt mehrstufige Authentifizierung deaktiviert (um die automatische Anmeldung zulassen) für die folgenden Dienste in Office 365-Teams:</span><span class="sxs-lookup"><span data-stu-id="7ac32-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="7ac32-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="7ac32-109">Exchange</span></span> 
- <span data-ttu-id="7ac32-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ac32-110">SharePoint</span></span> 
- <span data-ttu-id="7ac32-111">Office-Apps</span><span class="sxs-lookup"><span data-stu-id="7ac32-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="7ac32-112">Hinzufügen eines Gerätekontos</span><span class="sxs-lookup"><span data-stu-id="7ac32-112">Add a device account</span></span> 

<span data-ttu-id="7ac32-113">1\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-113">1\.</span></span> <span data-ttu-id="7ac32-114">Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange herstellen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="7ac32-115">Stellen Sie sicher, dass Sie die richtigen Berechtigungen die zugeordneten Cmdlets ausführen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="7ac32-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="7ac32-116">Es folgen einige Beispiele für Cmdlets, die in Ihrer Umgebung verwendet und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="7ac32-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="7ac32-117">2\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-117">2\.</span></span> <span data-ttu-id="7ac32-118">Wenn Sie die Sitzung eingerichtet haben, erstellen Sie entweder ein neues Postfach und aktivieren es als „RoomMailboxAccount“, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="7ac32-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7ac32-119">Dadurch wird das Konto zum Teams authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="7ac32-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="7ac32-120">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="7ac32-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="7ac32-121">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="7ac32-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="7ac32-122">3\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-122">3\.</span></span> <span data-ttu-id="7ac32-123">Sie müssen verschiedene Exchange-Eigenschaften für das Gerätekonto festlegen, um die Besprechungsumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7ac32-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="7ac32-124">Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="7ac32-125">4\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-125">4\.</span></span> <span data-ttu-id="7ac32-126">Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure Active Directory herstellen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="7ac32-127">Führen Sie das folgende Cmdlet aus, um die Verbindung mit Azure AD herzustellen:</span><span class="sxs-lookup"><span data-stu-id="7ac32-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="7ac32-128">5\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-128">5\.</span></span> <span data-ttu-id="7ac32-129">	Wenn das Kennwort nicht ablaufen soll, führen Sie das Cmdlet „Set-MsolUser“ mit der Option „PasswordNeverExpires“ wie folgt aus:  </span><span class="sxs-lookup"><span data-stu-id="7ac32-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="7ac32-130">Sie können auch wie folgt eine Telefonnummer für den Raum festlegen:</span><span class="sxs-lookup"><span data-stu-id="7ac32-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="7ac32-131">6\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-131">6\.</span></span> <span data-ttu-id="7ac32-132">Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Skype für Unternehmen funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="7ac32-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="7ac32-133">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7ac32-134">Get-MsolAccountSku können Sie wie folgt eine Liste der verfügbaren SKUs für Ihre Office 365-Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="7ac32-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="7ac32-p109">Als Nächstes können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="7ac32-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="7ac32-137">7\.</span><span class="sxs-lookup"><span data-stu-id="7ac32-137">7\.</span></span> <span data-ttu-id="7ac32-138">Im nächsten Schritt müssen Sie das Gerät Konto mit Teams für Hub-Oberfläche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ac32-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="7ac32-139">Stellen Sie sicher, dass die Umgebung die Anforderungen im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/)definierten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="7ac32-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="7ac32-140">Starten Sie wie folgt eine remote Windows PowerShell-Sitzung (unbedingt Skype für Business Online-PowerShell-Komponenten zu installieren):</span><span class="sxs-lookup"><span data-stu-id="7ac32-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="7ac32-141">Im nächsten Schritt aktivieren Sie Ihren Teams für Fläche Hub Konto durch Ausführen des folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7ac32-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="7ac32-142">Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7ac32-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="7ac32-143">Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7ac32-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="7ac32-144">Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation.</span><span class="sxs-lookup"><span data-stu-id="7ac32-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="7ac32-145">Nachdem Sie die vorhergehenden Schritte zum Aktivieren des Teams für Fläche Hub Konto abgeschlossen haben, müssen Sie die Fläche Hub v2 Gerät eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="7ac32-146">Verwenden das administrative Office 365-Portal, das Gerät eine Oberfläche Hub-Lizenz-Teams zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="7ac32-147">Weisen Sie eine Lizenz für das Konto</span><span class="sxs-lookup"><span data-stu-id="7ac32-147">Assign a license to the account</span></span>

1. <span data-ttu-id="7ac32-148">Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365 Administrationscenter, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="7ac32-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="7ac32-149">Klicken Sie auf **Benutzer und Gruppen**, und klicken Sie dann auf **Benutzer hinzufügen, Zurücksetzen von Kennwörtern, und vieles mehr**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="7ac32-150">Wählen Sie die Teams für Fläche Hub-Konto, und klicken Sie oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ac32-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="7ac32-151">Klicken Sie auf die Option **Lizenzen** .</span><span class="sxs-lookup"><span data-stu-id="7ac32-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="7ac32-152">Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie planen, je nach Ihrer Lizenzierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="7ac32-153">Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="7ac32-154">Installieren von Teams für Fläche Hub aus dem Microsoft-Speicher</span><span class="sxs-lookup"><span data-stu-id="7ac32-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="7ac32-155">Dabei werden die aktuellen problemumgehungen für die Installation von Teams für Fläche Hub aus dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7ac32-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="7ac32-156">Starten Sie den Windows Store:</span><span class="sxs-lookup"><span data-stu-id="7ac32-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="7ac32-157">a.</span><span class="sxs-lookup"><span data-stu-id="7ac32-157">a.</span></span> <span data-ttu-id="7ac32-158">Tippen Sie auf **Start** > **Alle Apps** > **Settings**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="7ac32-159">b.</span><span class="sxs-lookup"><span data-stu-id="7ac32-159">b.</span></span> <span data-ttu-id="7ac32-160">Tippen Sie auf **Konto Fläche Hub-Gerät, Management**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="7ac32-161">c.</span><span class="sxs-lookup"><span data-stu-id="7ac32-161">c.</span></span> <span data-ttu-id="7ac32-162">Tippen Sie auf der linken Seite auf der Registerkarte **Apps und -Features** .</span><span class="sxs-lookup"><span data-stu-id="7ac32-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="7ac32-163">d.</span><span class="sxs-lookup"><span data-stu-id="7ac32-163">d.</span></span> <span data-ttu-id="7ac32-164">Tippen Sie auf der rechten Seite auf die Schaltfläche **Öffnen Store** .</span><span class="sxs-lookup"><span data-stu-id="7ac32-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="7ac32-165">Suchen Sie nach *Microsoft-Teams*, aus dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7ac32-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="7ac32-166">Die **Microsoft-Teams Fläche Hub (Preview)** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ac32-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="7ac32-167">Tippen Sie auf die Schaltfläche **rufen Sie die app** zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7ac32-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="7ac32-168">Wenn die Installation abgeschlossen ist, starten Sie Fläche Hub neu.</span><span class="sxs-lookup"><span data-stu-id="7ac32-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="7ac32-169">Nach dem Neustart die Fläche Hub wird, werden Sie können die Teams app im Menü **Start** starten und teilnehmen an einer Besprechung aus dem Kalender.</span><span class="sxs-lookup"><span data-stu-id="7ac32-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="7ac32-170">Stellen Sie die standardanwendung VTC Teams</span><span class="sxs-lookup"><span data-stu-id="7ac32-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="7ac32-171">Teams können die standardmäßige VTC-Anwendung anstelle von Skype für Unternehmen werden bis zu festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7ac32-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="7ac32-172">Eine Richtlinie für Mobile Geräte Management (MDM) muss auf dem Gerät Fläche Hub angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ac32-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="7ac32-173">Es gibt zwei Optionen zum Konfigurieren von MDM Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="7ac32-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="7ac32-174">Wenn Sie eine Richtlinie konfiguriert haben, fügen sie über die Geräte Management app hinzu.</span><span class="sxs-lookup"><span data-stu-id="7ac32-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="7ac32-175">Wenn Sie keine remote-Richtlinie konfiguriert haben, haben wir eine bereitgestellten Package-Datei, die auf einem USB-Schlüssel geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7ac32-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="7ac32-176">Verwaltung der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="7ac32-176">Device management configuration</span></span>

<span data-ttu-id="7ac32-177">Es folgt ein Beispiel für eine von einer zentralen MDM Zertifizierungsstelle konfigurierte MDM Richtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="7ac32-178">Wenn Sie sich im Unternehmensnetzwerk sind, können Sie die folgenden Anweisungen, einschließlich Benutzerkonto wortwörtlich.</span><span class="sxs-lookup"><span data-stu-id="7ac32-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="7ac32-179">Klicken Sie im Abschnitt **Verwaltung von Geräten** Tippen Sie auf **+**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="7ac32-180">Das Dialogfeld **Verbindung mit arbeiten oder Schule herstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7ac32-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="7ac32-181">Geben Sie die Richtlinie e-Mail-Adresse und das Kennwort bei entsprechender Aufforderung.</span><span class="sxs-lookup"><span data-stu-id="7ac32-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="7ac32-182">**Hinweis:**  Es ist ein Fehler in das Betriebssystem, das automatisch die Benutzeroberfläche nicht aktualisiert wird, nachdem Sie Ihr Gerät Management-Konto eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7ac32-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="7ac32-183">Sie müssen zu schließen und erneut öffnen Einstellungen, um die angegebene Konto zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="7ac32-184">Es werde ein paar Minuten für die MDM Benutzerrichtlinien synchronisieren. Wenn Sie eine Synchronisierung erzwingen möchten, tippen Sie auf die Schaltfläche **MDM-Konto** ein, und tippen Sie dann auf die Schaltfläche **Info** .</span><span class="sxs-lookup"><span data-stu-id="7ac32-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="7ac32-185">Dadurch wird das Fenster Info angezeigt, in dem Sie **Sync**tippen können.</span><span class="sxs-lookup"><span data-stu-id="7ac32-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="7ac32-186">Zum bestätigen, dass Sie verfügen, was Sie benötigen, können Sie die Registrierung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="7ac32-187">Zwei Schlüssel unter **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7ac32-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="7ac32-188">Der **VtcAppMeetingHandlingMode** DWORD-Wert gibt an, dass Teams ist der Standard-app.</span><span class="sxs-lookup"><span data-stu-id="7ac32-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="7ac32-189">Die folgenden Werte werden erkannt.</span><span class="sxs-lookup"><span data-stu-id="7ac32-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="7ac32-190">Number</span><span class="sxs-lookup"><span data-stu-id="7ac32-190">Number</span></span> | <span data-ttu-id="7ac32-191">Wert</span><span class="sxs-lookup"><span data-stu-id="7ac32-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="7ac32-192">0</span><span class="sxs-lookup"><span data-stu-id="7ac32-192">0</span></span>      | <span data-ttu-id="7ac32-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="7ac32-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="7ac32-194">1</span><span class="sxs-lookup"><span data-stu-id="7ac32-194">1</span></span>      | <span data-ttu-id="7ac32-195">VtcPreferred (Teams)</span><span class="sxs-lookup"><span data-stu-id="7ac32-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="7ac32-196">2</span><span class="sxs-lookup"><span data-stu-id="7ac32-196">2</span></span>      | <span data-ttu-id="7ac32-197">VtcExclusive (nur Teams)</span><span class="sxs-lookup"><span data-stu-id="7ac32-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="7ac32-198">Die **VtcCallAppPackageId** ist der Name des installierten Teams-Pakets.</span><span class="sxs-lookup"><span data-stu-id="7ac32-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="7ac32-199">Wenn dies nicht angezeigt, stellen Sie sicher, dass Sie das Paket Teams installiert haben und erneut synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="7ac32-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="7ac32-200">Konfigurieren von MDM über USB-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7ac32-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="7ac32-201">Die Pakete finden Sie auf dieser [Seite herunterladen](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="7ac32-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="7ac32-202">Wählen Sie die entsprechenden für das Paket, das Sie planen, installieren und kopieren Sie ihn in einen USB-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="7ac32-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="7ac32-203">Die richtigen .ppkg zu verwendende Datei hängt davon ab, das Teams-Paket, das aus dem Speicher installiert wurde, und die Richtlinie (Skype exklusive, bevorzugter Skype, Teams bevorzugt, Teams Exclusive) gelten soll.</span><span class="sxs-lookup"><span data-stu-id="7ac32-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="7ac32-204">Fügen Sie den USB-Schlüssel an die Fläche Hub-Gerät.</span><span class="sxs-lookup"><span data-stu-id="7ac32-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="7ac32-205">Öffnen Sie die **Einstellungen** app auf einem Gerät Fläche Hub.</span><span class="sxs-lookup"><span data-stu-id="7ac32-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="7ac32-206">Öffnen Sie die **Fläche Hub Gerätemanagement Konto**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="7ac32-207">Öffnen Sie die **Verwaltung von Geräten**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="7ac32-208">Klicken Sie auf **Hinzufügen oder Entfernen einer Bereitstellung Paket**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="7ac32-209">Klicken Sie auf **Paket hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7ac32-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="7ac32-210">Wählen Sie aus dem Dropdown-Menü die Option **Wechselmedium** aus.</span><span class="sxs-lookup"><span data-stu-id="7ac32-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="7ac32-211">Fügen Sie die **Allowbuildspreview.ppkg**, und wählen Sie dann das Fläche Hub-Paket, den, das Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ac32-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="7ac32-212">Starten Sie das Fläche Hub-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="7ac32-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="7ac32-213">Wenn das Gerät oder die Geräte Ihrer Organisation nicht aktuell Teil der Windows-Insider-Anwendung sind, und Sie befinden sich in Ländern behandelt durch allgemeine Data Protection Regulierung (GDPR) (oder Einstelllungen Telemetrie Basisdatenträger manuell geändert haben), müssen Sie erneut überprüfen dass Sie vollständige Telemetrie zulässig haben, bevor Sie die Insider Programm teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="7ac32-214">GDPR geändert, das Standardverhalten des Fläche Hub-Geräte in der EU für grundlegende Telemetrie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7ac32-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>