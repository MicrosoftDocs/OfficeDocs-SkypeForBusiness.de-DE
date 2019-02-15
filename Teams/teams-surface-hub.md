---
title: Bereitstellen von Microsoft Teams für Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren Sie die Administratoreinstellungen für Microsoft Teams für Surface Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132003"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="780d8-103">Bereitstellen von Microsoft Teams für Surface Hub</span><span class="sxs-lookup"><span data-stu-id="780d8-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="780d8-104">Bevor Sie Microsoft Teams für Microsoft Surface Hub bereitstellen, vergewissern Sie sich, dass die Hardware-, Betriebssystem- und anderen Anforderungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="780d8-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="780d8-105">Weitere Informationen finden Sie im [Microsoft Surface Hub-Administratorhandbuch](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="780d8-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="780d8-106">Wenn Sie von Skype for Business Online wechseln, müssen Sie bestätigen, dass dem Benutzer eine Microsoft Teams-Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="780d8-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="780d8-107">Installieren von Teams für Surface Hub aus dem Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="780d8-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="780d8-108">Diese Anleitung bezieht sich auf die Installation von Teams für Surface Hub aus dem Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="780d8-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="780d8-109">Öffnen Sie den Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="780d8-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="780d8-110">a.</span><span class="sxs-lookup"><span data-stu-id="780d8-110">a.</span></span> <span data-ttu-id="780d8-111">Tippen Sie auf **Start** > **Alle Anwendungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="780d8-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="780d8-112">b.</span><span class="sxs-lookup"><span data-stu-id="780d8-112">b.</span></span> <span data-ttu-id="780d8-113">Tippen Sie auf **Surface Hub-Gerätekonto, Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="780d8-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="780d8-114">c.</span><span class="sxs-lookup"><span data-stu-id="780d8-114">c.</span></span> <span data-ttu-id="780d8-115">Tippen Sie auf der linken Seite auf die Registerkarte **Apps und Features**.</span><span class="sxs-lookup"><span data-stu-id="780d8-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="780d8-116">d.</span><span class="sxs-lookup"><span data-stu-id="780d8-116">d.</span></span> <span data-ttu-id="780d8-117">Tippen Sie auf der rechten Seite auf die Schaltfläche **Store öffnen**.</span><span class="sxs-lookup"><span data-stu-id="780d8-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="780d8-118">Suchen Sie *Microsoft Teams* im Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="780d8-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="780d8-119">**Microsoft Teams für Surface Hub** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="780d8-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="780d8-120">Tippen Sie zum Installieren auf die Schaltfläche **App abrufen**.</span><span class="sxs-lookup"><span data-stu-id="780d8-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="780d8-121">Wenn die Installation abgeschlossen ist, starten Sie den Surface Hub neu.</span><span class="sxs-lookup"><span data-stu-id="780d8-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="780d8-122">Tippen Sie nicht auf der Seite des Store-Eintrags auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="780d8-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="780d8-123">Festlegen von Teams als Standardanwendung für Anrufe und Besprechungen</span><span class="sxs-lookup"><span data-stu-id="780d8-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="780d8-124">Es gibt zwei Möglichkeiten der Konfiguration der Standardanwendungsrichtlinie für Anrufe und Besprechungen:</span><span class="sxs-lookup"><span data-stu-id="780d8-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="780d8-125">**Option 1**: Konfigurieren über USB-Stick.</span><span class="sxs-lookup"><span data-stu-id="780d8-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="780d8-126">**Option 2**: Konfigurieren über MDM z. B. Intune.</span><span class="sxs-lookup"><span data-stu-id="780d8-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="780d8-127">Option 1: Konfigurieren über USB-Stick</span><span class="sxs-lookup"><span data-stu-id="780d8-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="780d8-128">Die Pakete befinden sich auf dieser [Downloadseite](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="780d8-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="780d8-129">Wählen Sie das passende Paket, das Sie installieren möchten, und kopieren Sie es auf einen USB-Stick.</span><span class="sxs-lookup"><span data-stu-id="780d8-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="780d8-130">Welche PPKG-Datei die richtige ist, hängt von der zu verwendenden Standardanwendungsrichtlinie ab:</span><span class="sxs-lookup"><span data-stu-id="780d8-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="780d8-131">Nummer</span><span class="sxs-lookup"><span data-stu-id="780d8-131">Number</span></span>  |<span data-ttu-id="780d8-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780d8-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="780d8-133">0</span><span class="sxs-lookup"><span data-stu-id="780d8-133">^0$</span></span>     | <span data-ttu-id="780d8-134">Skype als bevorzugte App auf dem Startbildschirm, Teams-Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="780d8-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="780d8-135">1</span><span class="sxs-lookup"><span data-stu-id="780d8-135">1</span></span>     | <span data-ttu-id="780d8-136">Teams als bevorzugte App auf dem Startbildschirm, Skype-Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="780d8-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="780d8-137">2</span><span class="sxs-lookup"><span data-stu-id="780d8-137">2</span></span>     | <span data-ttu-id="780d8-138">Teams als exklusive App auf dem Startbildschirm (Skype-App nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="780d8-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="780d8-139">Schließen Sie den USB-Stick an das Surface Hub-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="780d8-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="780d8-140">Öffnen Sie die **Einstellungen**-App auf einem Surface Hub-Gerät.</span><span class="sxs-lookup"><span data-stu-id="780d8-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="780d8-141">Öffnen Sie **Surface Hub-Gerätekonto, Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="780d8-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="780d8-142">Öffnen Sie **Geräteverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="780d8-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="780d8-143">Klicken Sie auf **Bereitstellungspaket hinzufügen oder entfernen**.</span><span class="sxs-lookup"><span data-stu-id="780d8-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="780d8-144">Klicken Sie auf **Paket hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="780d8-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="780d8-145">Wählen Sie die Option **Wechselmedien** aus dem Dropdown-Menü aus.</span><span class="sxs-lookup"><span data-stu-id="780d8-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="780d8-146">Fügen Sie das entsprechende <strong>TeamsRTMMode\*.ppkg</strong>-Paket hinzu, das zuvor auf den USB-Stick kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="780d8-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="780d8-147">Starten Sie das Surface Hub-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="780d8-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="780d8-148">Nach dem Neustart des Geräts sollten Sie die Teams-App über den Startbildschirm starten und über den Kalender an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="780d8-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="780d8-149">Option 2: Konfigurieren über MDM z. B. Intune</span><span class="sxs-lookup"><span data-stu-id="780d8-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="780d8-150">Verwenden Sie die folgenden Schritte, um die Standardanwendungsrichtlinie für Anrufe und Besprechungen über Intune zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="780d8-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="780d8-151">Außerdem finden Sie weitere Informationen im Blogbeitrag [Bereitstellen der Microsoft Teams für Surface Hub-App mit Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="780d8-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="780d8-152">Einstellung</span><span class="sxs-lookup"><span data-stu-id="780d8-152">Setting</span></span>   |<span data-ttu-id="780d8-153">Wert</span><span class="sxs-lookup"><span data-stu-id="780d8-153">Value</span></span>    |<span data-ttu-id="780d8-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="780d8-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="780d8-155">Pfad</span><span class="sxs-lookup"><span data-stu-id="780d8-155">Path</span></span>      | <span data-ttu-id="780d8-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="780d8-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="780d8-157">Datentyp</span><span class="sxs-lookup"><span data-stu-id="780d8-157">Data Type</span></span> | <span data-ttu-id="780d8-158">Ganze Zahl (0-2)</span><span class="sxs-lookup"><span data-stu-id="780d8-158">integer (0-2)</span></span>   |<span data-ttu-id="780d8-159">0: Skype als bevorzugte App auf dem Startbildschirm, Teams-Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="780d8-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="780d8-160">1: Teams als bevorzugte App auf dem Startbildschirm, Skype-Besprechungen verfügbar</span><span class="sxs-lookup"><span data-stu-id="780d8-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="780d8-161">2: Teams als exklusive App auf dem Startbildschirm (Skype-App nicht verfügbar)</span><span class="sxs-lookup"><span data-stu-id="780d8-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="780d8-162">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="780d8-162">Operations</span></span>| <span data-ttu-id="780d8-163">Abrufen, Einrichten</span><span class="sxs-lookup"><span data-stu-id="780d8-163">Get, Set</span></span>        |

|<span data-ttu-id="780d8-164">Einstellung</span><span class="sxs-lookup"><span data-stu-id="780d8-164">Setting</span></span>   |<span data-ttu-id="780d8-165">Wert</span><span class="sxs-lookup"><span data-stu-id="780d8-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="780d8-166">Pfad</span><span class="sxs-lookup"><span data-stu-id="780d8-166">Path</span></span>      | <span data-ttu-id="780d8-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="780d8-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="780d8-168">Datentyp</span><span class="sxs-lookup"><span data-stu-id="780d8-168">Data Type</span></span> | <span data-ttu-id="780d8-169">String: Teams-Anwendungspaket-ID wird auf **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** festgelegt</span><span class="sxs-lookup"><span data-stu-id="780d8-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="780d8-170">Vorgänge</span><span class="sxs-lookup"><span data-stu-id="780d8-170">Operations</span></span>| <span data-ttu-id="780d8-171">Abrufen, Einrichten</span><span class="sxs-lookup"><span data-stu-id="780d8-171">Get, Set</span></span>        |

<span data-ttu-id="780d8-172">Starten Sie das Surface Hub-Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="780d8-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="780d8-173">Nach dem Neustart des Geräts sollten Sie die Teams-App über den Startbildschirm starten und über den Kalender an einer Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="780d8-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

