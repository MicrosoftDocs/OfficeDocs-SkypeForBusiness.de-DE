---
title: Bereitstellen von Microsoft-Teams für die Fläche Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren von Admin-Einstellungen für Microsoft-Teams für Fläche Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 251cc2d12dfdab2e9bc4c9bcc928e80a9c43e2c2
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938000"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="4a0b4-103">Bereitstellen von Microsoft-Teams für die Fläche Hub</span><span class="sxs-lookup"><span data-stu-id="4a0b4-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="4a0b4-104">Vor der Bereitstellung von Microsoft-Teams für Microsoft Surface Hub Achten Sie darauf, dass Sie die Hardware, Betriebssystem und andere Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="4a0b4-105">Weitere Informationen finden Sie im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="4a0b4-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="4a0b4-106">Einrichten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="4a0b4-106">Set up user accounts</span></span>
 
<span data-ttu-id="4a0b4-107">Erstellen Sie zum Einrichten von Benutzerkonten, die mit den Teams für Fläche Hub verwendet werden kann das Gerät Konto wie für die Unterstützung bei Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="4a0b4-108">Das Gerät Konto benötigt mehrstufige Authentifizierung deaktiviert (um die automatische Anmeldung zulassen) für die folgenden Dienste in Office 365-Teams:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="4a0b4-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="4a0b4-109">Exchange</span></span> 
- <span data-ttu-id="4a0b4-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4a0b4-110">SharePoint</span></span> 
- <span data-ttu-id="4a0b4-111">Office-Apps</span><span class="sxs-lookup"><span data-stu-id="4a0b4-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="4a0b4-112">Hinzufügen eines Gerätekontos</span><span class="sxs-lookup"><span data-stu-id="4a0b4-112">Add a device account</span></span> 

<span data-ttu-id="4a0b4-113">1\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-113">1\.</span></span> <span data-ttu-id="4a0b4-114">Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange herstellen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="4a0b4-115">Stellen Sie sicher, dass Sie die richtigen Berechtigungen die zugeordneten Cmdlets ausführen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="4a0b4-116">Es folgen einige Beispiele für Cmdlets, die in Ihrer Umgebung verwendet und geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="4a0b4-117">2\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-117">2\.</span></span> <span data-ttu-id="4a0b4-118">Wenn Sie die Sitzung eingerichtet haben, erstellen Sie entweder ein neues Postfach und aktivieren es als „RoomMailboxAccount“, oder Sie ändern die Einstellungen für ein vorhandenes Raumpostfach.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="4a0b4-119">Dadurch wird das Konto zum Teams authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="4a0b4-120">Wenn Sie ein vorhandenes Ressourcenpostfach ändern:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="4a0b4-121">Wenn Sie ein neues Ressourcenpostfach erstellen:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="4a0b4-122">3\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-122">3\.</span></span> <span data-ttu-id="4a0b4-123">Sie müssen verschiedene Exchange-Eigenschaften für das Gerätekonto festlegen, um die Besprechungsumgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="4a0b4-124">Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="4a0b4-125">4\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-125">4\.</span></span> <span data-ttu-id="4a0b4-126">Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure Active Directory herstellen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="4a0b4-127">Führen Sie das folgende Cmdlet aus, um die Verbindung mit Azure AD herzustellen:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="4a0b4-128">5\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-128">5\.</span></span> <span data-ttu-id="4a0b4-129">	Wenn das Kennwort nicht ablaufen soll, führen Sie das Cmdlet „Set-MsolUser“ mit der Option „PasswordNeverExpires“ wie folgt aus:  </span><span class="sxs-lookup"><span data-stu-id="4a0b4-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="4a0b4-130">Sie können auch wie folgt eine Telefonnummer für den Raum festlegen:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="4a0b4-131">6\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-131">6\.</span></span> <span data-ttu-id="4a0b4-132">Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Skype für Unternehmen funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="4a0b4-133">Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4a0b4-134">Get-MsolAccountSku können Sie wie folgt eine Liste der verfügbaren SKUs für Ihre Office 365-Mandanten abzurufen:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="4a0b4-p109">Als Nächstes können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).</span><span class="sxs-lookup"><span data-stu-id="4a0b4-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="4a0b4-137">7\.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-137">7\.</span></span> <span data-ttu-id="4a0b4-138">Im nächsten Schritt müssen Sie das Gerät Konto mit Teams für Hub-Oberfläche aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="4a0b4-139">Stellen Sie sicher, dass die Umgebung die Anforderungen im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/)definierten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

<span data-ttu-id="4a0b4-140">Starten Sie wie folgt eine remote Windows PowerShell-Sitzung (unbedingt Skype für Business Online-PowerShell-Komponenten zu installieren):</span><span class="sxs-lookup"><span data-stu-id="4a0b4-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="4a0b4-141">Im nächsten Schritt aktivieren Sie Ihren Teams für Fläche Hub Konto durch Ausführen des folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="4a0b4-142">Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="4a0b4-143">Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="4a0b4-144">Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="4a0b4-145">Nachdem Sie die vorhergehenden Schritte zum Aktivieren des Teams für Fläche Hub Konto abgeschlossen haben, müssen Sie die Fläche Hub v2 Gerät eine Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="4a0b4-146">Verwenden das administrative Office 365-Portal, das Gerät eine Oberfläche Hub-Lizenz-Teams zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="4a0b4-147">Weisen Sie eine Lizenz für das Konto</span><span class="sxs-lookup"><span data-stu-id="4a0b4-147">Assign a license to the account</span></span>

1. <span data-ttu-id="4a0b4-148">Melden Sie sich als mandantenadministrator an, öffnen Sie das Office 365 Administrationscenter, und klicken Sie auf die Admin-app.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="4a0b4-149">Klicken Sie auf **Benutzer und Gruppen**, und klicken Sie dann auf **Benutzer hinzufügen, Zurücksetzen von Kennwörtern, und vieles mehr**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4a0b4-150">Wählen Sie die Teams für Fläche Hub-Konto, und klicken Sie oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="4a0b4-151">Klicken Sie auf die Option **Lizenzen** .</span><span class="sxs-lookup"><span data-stu-id="4a0b4-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="4a0b4-152">Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie planen, je nach Ihrer Lizenzierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="4a0b4-153">Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="4a0b4-154">Installieren von Teams für Fläche Hub aus dem Microsoft-Speicher</span><span class="sxs-lookup"><span data-stu-id="4a0b4-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="4a0b4-155">Diese Anweisungen sind für die Installation von Teams für Fläche Hub aus dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="4a0b4-156">Starten Sie den Microsoft-Speicher:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="4a0b4-157">a.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-157">a.</span></span> <span data-ttu-id="4a0b4-158">Tippen Sie auf **Start** > **Alle Apps** > **Settings**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="4a0b4-159">b.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-159">b.</span></span> <span data-ttu-id="4a0b4-160">Tippen Sie auf **Konto Fläche Hub-Gerät, Management**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="4a0b4-161">c.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-161">c.</span></span> <span data-ttu-id="4a0b4-162">Tippen Sie auf der linken Seite auf der Registerkarte **Apps und -Features** .</span><span class="sxs-lookup"><span data-stu-id="4a0b4-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="4a0b4-163">d.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-163">d.</span></span> <span data-ttu-id="4a0b4-164">Tippen Sie auf der rechten Seite auf die Schaltfläche **Öffnen Store** .</span><span class="sxs-lookup"><span data-stu-id="4a0b4-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="4a0b4-165">Suchen Sie nach *Microsoft-Teams*, aus dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="4a0b4-166">Die **Microsoft-Teams Fläche Hub** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="4a0b4-167">Tippen Sie auf die Schaltfläche **rufen Sie die app** zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="4a0b4-168">Wenn die Installation abgeschlossen ist, starten Sie Fläche Hub neu.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="4a0b4-169">Tippen Sie nicht auf aus dem Angebot Seite Speicher **zu starten** .</span><span class="sxs-lookup"><span data-stu-id="4a0b4-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="4a0b4-170">Stellen Sie die Standardeinstellung Anruf- und Besprechungen Anwendung Teams</span><span class="sxs-lookup"><span data-stu-id="4a0b4-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="4a0b4-171">Es gibt zwei Optionen für die Anruf- und Besprechungen Anwendung Standardrichtlinie konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="4a0b4-172">**Option 1**: Konfigurieren von über USB-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="4a0b4-173">**Option 2**: über MDM wie Intune konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-173">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="4a0b4-174">Option 1: Konfigurieren von über USB-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="4a0b4-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="4a0b4-175">Die Pakete finden Sie auf dieser [Seite herunterladen](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="4a0b4-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="4a0b4-176">Wählen Sie die entsprechenden für das Paket, das Sie planen, installieren und kopieren Sie ihn in einen USB-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="4a0b4-177">Die richtigen .ppkg-Datei verwenden, hängt die Standardrichtlinie für die Anwendung wie folgt anwenden möchten:</span><span class="sxs-lookup"><span data-stu-id="4a0b4-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="4a0b4-178">Number</span><span class="sxs-lookup"><span data-stu-id="4a0b4-178">Number</span></span>  |<span data-ttu-id="4a0b4-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a0b4-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4a0b4-180">0</span><span class="sxs-lookup"><span data-stu-id="4a0b4-180">0</span></span>     | <span data-ttu-id="4a0b4-181">Bevorzugter Skype-app auf der Startseite, Teams Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="4a0b4-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="4a0b4-182">1</span><span class="sxs-lookup"><span data-stu-id="4a0b4-182">1</span></span>     | <span data-ttu-id="4a0b4-183">Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="4a0b4-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="4a0b4-184">2</span><span class="sxs-lookup"><span data-stu-id="4a0b4-184">2</span></span>     | <span data-ttu-id="4a0b4-185">Teams exklusive app auf der Startseite (Skype-app nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="4a0b4-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="4a0b4-186">Fügen Sie den USB-Schlüssel an die Fläche Hub-Gerät.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="4a0b4-187">Öffnen Sie die **Einstellungen** app auf einem Gerät Fläche Hub.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="4a0b4-188">Öffnen Sie die **Fläche Hub Gerätemanagement Konto**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="4a0b4-189">Öffnen Sie die **Verwaltung von Geräten**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="4a0b4-190">Klicken Sie auf **Hinzufügen oder Entfernen einer Bereitstellung Paket**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="4a0b4-191">Klicken Sie auf **Paket hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="4a0b4-192">Wählen Sie aus dem Dropdown-Menü die Option **Wechselmedium** aus.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="4a0b4-193">Fügen Sie das entsprechende **TeamsRTMMode\*.ppkg** -Paket, das zuvor an den USB-Schlüssel kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="4a0b4-194">Starten Sie das Fläche Hub-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="4a0b4-195">Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="4a0b4-196">Option 2: Konfigurieren von über MDM wie Intune</span><span class="sxs-lookup"><span data-stu-id="4a0b4-196">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="4a0b4-197">Verwenden Sie Folgendes, um die Anruf- und Besprechungen Anwendung Standardrichtlinie über Intune konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-197">Use the following to configure the default calling and meetings application policy via Intune.</span></span>

|<span data-ttu-id="4a0b4-198">Einstellung</span><span class="sxs-lookup"><span data-stu-id="4a0b4-198">Setting</span></span>   |<span data-ttu-id="4a0b4-199">Wert</span><span class="sxs-lookup"><span data-stu-id="4a0b4-199">Value</span></span>    |<span data-ttu-id="4a0b4-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a0b4-200">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="4a0b4-201"> Path</span><span class="sxs-lookup"><span data-stu-id="4a0b4-201">Path</span></span>      | <span data-ttu-id="4a0b4-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="4a0b4-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="4a0b4-203">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4a0b4-203">Data Type</span></span> | <span data-ttu-id="4a0b4-204">Ganzzahl (0-2)</span><span class="sxs-lookup"><span data-stu-id="4a0b4-204">integer (0-2)</span></span>   |<span data-ttu-id="4a0b4-205">0 – bevorzugte Skype-app auf der Startseite, Teams Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="4a0b4-205">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="4a0b4-206">1 – Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="4a0b4-206">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="4a0b4-207">2 - Teams exklusive app auf der Startseite (Skype-app nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="4a0b4-207">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="4a0b4-208">Betrieb</span><span class="sxs-lookup"><span data-stu-id="4a0b4-208">Operations</span></span>| <span data-ttu-id="4a0b4-209">Abrufen, festlegen</span><span class="sxs-lookup"><span data-stu-id="4a0b4-209">Get, Set</span></span>        |

|<span data-ttu-id="4a0b4-210">Einstellung</span><span class="sxs-lookup"><span data-stu-id="4a0b4-210">Setting</span></span>   |<span data-ttu-id="4a0b4-211">Wert</span><span class="sxs-lookup"><span data-stu-id="4a0b4-211">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="4a0b4-212"> Path</span><span class="sxs-lookup"><span data-stu-id="4a0b4-212">Path</span></span>      | <span data-ttu-id="4a0b4-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="4a0b4-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="4a0b4-214">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4a0b4-214">Data Type</span></span> | <span data-ttu-id="4a0b4-215">String - Set-Zeichenfolge, die Teams Anwendungspaket-ID als **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams**</span><span class="sxs-lookup"><span data-stu-id="4a0b4-215">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="4a0b4-216">Betrieb</span><span class="sxs-lookup"><span data-stu-id="4a0b4-216">Operations</span></span>| <span data-ttu-id="4a0b4-217">Abrufen, festlegen</span><span class="sxs-lookup"><span data-stu-id="4a0b4-217">Get, Set</span></span>        |

<span data-ttu-id="4a0b4-218">Starten Sie das Fläche Hub-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-218">Restart the Surface Hub device.</span></span> <span data-ttu-id="4a0b4-219">Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-219">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

> [!NOTE]
> <span data-ttu-id="4a0b4-220">Wenn das Gerät oder die Geräte Ihrer Organisation nicht aktuell Teil der Windows-Insider-Anwendung sind, und Sie befinden sich in Ländern behandelt durch allgemeine Data Protection Regulierung (GDPR) (oder Einstelllungen Telemetrie Basisdatenträger manuell geändert haben), müssen Sie erneut überprüfen dass Sie vollständige Telemetrie zulässig haben, bevor Sie die Insider Programm teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-220">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="4a0b4-221">GDPR geändert, das Standardverhalten des Fläche Hub-Geräte in der EU für grundlegende Telemetrie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4a0b4-221">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>
