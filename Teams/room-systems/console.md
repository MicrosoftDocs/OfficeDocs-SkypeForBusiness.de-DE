---
title: Konfigurieren einer Microsoft Teams rooms-Konsole
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams rooms-Konsole und Ihre Peripheriegeräte einrichten.
ms.openlocfilehash: 6172e37b53934bc75ae7f5bdf848fd503ffe2e8a
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675773"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="4a107-103">Konfigurieren einer Microsoft Teams rooms-Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="4a107-104">In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams rooms-Konsole und Ihre Peripheriegeräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="4a107-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="4a107-105">Führen Sie diese Schritte nur aus, wenn die erforderlichen Microsoft Teams oder Skype for Business-und Exchange-Konten bereits erstellt und getestet wurden, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a107-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="4a107-106">Sie benötigen die in den [Microsoft Teams-Chatrooms](requirements.md)beschriebene Hardware und Software.</span><span class="sxs-lookup"><span data-stu-id="4a107-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="4a107-107">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="4a107-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="4a107-108">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="4a107-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="4a107-109">Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="4a107-110">Installieren von Windows 10 und der Microsoft Teams rooms-Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="4a107-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="4a107-111">Anfängliche Einrichtung der Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="4a107-112">Checkliste für Microsoft Teams rooms-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="4a107-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="4a107-113">Microsoft Teams-Räume funktionieren nur in einer ordnungsgemäß konfigurierten Microsoft Teams-oder Skype for Business-Umgebung, in der die Geräte Konten ordnungsgemäß eingerichtet sind, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4a107-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="4a107-114">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="4a107-114">Prepare the installation media</span></span>
<span data-ttu-id="4a107-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-115"></span></span>

<span data-ttu-id="4a107-116">Zum Installieren der Microsoft Teams rooms Console-APP ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4a107-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="4a107-117">Auf dem Gerät sollten keine weiteren Dateien vorhanden sein. alle vorhandenen Dateien auf dem USB-Speicher gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="4a107-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a107-118">Fehler beim Erstellen von Microsoft Teams rooms-Installationsmedien entsprechend diesen Anweisungen führen wahrscheinlich zu unerwartetem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="4a107-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="4a107-119">Nachfolgend wird beschrieben, wie Sie Installationsmedien für die Erstellung von neuen Microsoft Teams rooms-Geräten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a107-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="4a107-120">Vorhandene Geräte werden standardmäßig automatisch von Windows Update und dem Windows Store aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4a107-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="4a107-121">Laden Sie das [CreateSrsMedia. ps1-Skript](https://go.microsoft.com/fwlink/?linkid=867842)herunter.</span><span class="sxs-lookup"><span data-stu-id="4a107-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="4a107-122">Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="4a107-123">Befolgen Sie die Anweisungen des Skripts, um eine USB-Setupdiskette für Microsoft Teams Rooms zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a107-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="4a107-124">Jedes Mal, wenn das CreateSrsMedia. ps1-Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Protokoll Protokolls für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4a107-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="4a107-125">Wenn Probleme beim Ausführen des Skripts auftreten, stellen Sie sicher, dass eine Kopie dieser Aufzeichnung zur Verfügung steht, wenn Sie den Support anfordern.</span><span class="sxs-lookup"><span data-stu-id="4a107-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="4a107-126">Das CreateSrsMedia. ps1-Skript automatisiert die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="4a107-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="4a107-127">Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams-Räume herunter.</span><span class="sxs-lookup"><span data-stu-id="4a107-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="4a107-128">Ermitteln des Windows-Builds, den der Benutzer bereitstellen muss</span><span class="sxs-lookup"><span data-stu-id="4a107-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="4a107-129">Die zuletzt veröffentlichten Versionen können oder werden möglicherweise nicht getestet und für die Verwendung mit Microsoft Teams rooms-Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a107-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="4a107-130">Erforderliche unterstützende Komponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4a107-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="4a107-131">Montieren Sie die erforderlichen Komponenten auf dem Installationsmedium.</span><span class="sxs-lookup"><span data-stu-id="4a107-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="4a107-132">Eine bestimmte Version von Windows 10 ist erforderlich, und diese Version steht nur für Volumenlizenzkunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4a107-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="4a107-133">Sie können eine Kopie vom [Volumen Lizenzierungs-Service Center](https://www.microsoft.com/Licensing/servicecenter/)erhalten.</span><span class="sxs-lookup"><span data-stu-id="4a107-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="4a107-134">Wenn Sie den Vorgang beenden, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren Sie mit [der Installation von Windows 10 und der Konsolen-App Microsoft Teams rooms](console.md#Reimage)fort.</span><span class="sxs-lookup"><span data-stu-id="4a107-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="4a107-135">Installieren von Windows 10 und der Microsoft Teams rooms-Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="4a107-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="4a107-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-136"></span></span>

<span data-ttu-id="4a107-137">Sie müssen nun das von Ihnen erstellte Setup-Medium übernehmen.</span><span class="sxs-lookup"><span data-stu-id="4a107-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="4a107-138">Das Zielgerät wird als Appliance ausgeführt, und der Standardbenutzer wird so eingestellt, dass nur die Microsoft Teams rooms Console-app ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4a107-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="4a107-139">Wenn das Zielgerät in einem Dock (z.b. Surface pro) installiert wird, trennen Sie es vom Dock.</span><span class="sxs-lookup"><span data-stu-id="4a107-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="4a107-140">Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4a107-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="4a107-141">Stellen Sie sicher, dass das Zielgerät mit dem Stromnetz verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4a107-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="4a107-142">Schließen Sie die USB-Setupdiskette an das Zielgerät an.</span><span class="sxs-lookup"><span data-stu-id="4a107-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="4a107-143">Starten Sie die USB-Setupdiskette.</span><span class="sxs-lookup"><span data-stu-id="4a107-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="4a107-144">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="4a107-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="4a107-145">Wenn es sich bei Ihrem Zielgerät um einen Surface pro handelt, führen Sie die folgenden Schritte aus, um die USB-Setupdiskette zu starten:</span><span class="sxs-lookup"><span data-stu-id="4a107-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="4a107-146">a.</span><span class="sxs-lookup"><span data-stu-id="4a107-146">a.</span></span> <span data-ttu-id="4a107-147">Drücken Sie die Taste, und fahren Sie fort, um die Lautstärketaste (-) zu halten.</span><span class="sxs-lookup"><span data-stu-id="4a107-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="4a107-148">b.</span><span class="sxs-lookup"><span data-stu-id="4a107-148">b.</span></span> <span data-ttu-id="4a107-149">Drücken Sie die Power-Taste, und lassen Sie sie los.</span><span class="sxs-lookup"><span data-stu-id="4a107-149">Press and release the power button.</span></span>

    <span data-ttu-id="4a107-150">c.</span><span class="sxs-lookup"><span data-stu-id="4a107-150">c.</span></span> <span data-ttu-id="4a107-151">Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.</span><span class="sxs-lookup"><span data-stu-id="4a107-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="4a107-152">Sobald die Installation abgeschlossen ist, wird das System beendet.</span><span class="sxs-lookup"><span data-stu-id="4a107-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="4a107-153">Nachdem das System heruntergefahren wurde, ist es sicher, die USB-Setupdiskette zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4a107-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="4a107-154">An dieser Stelle können Sie das Zielgerät in der Docking-Station platzieren (wenn Sie ein Dock-basiertes Produkt verwenden), die für den Besprechungsraum benötigten Peripheriegeräte anschließen und eine Verbindung mit dem Netzwerk herstellen.</span><span class="sxs-lookup"><span data-stu-id="4a107-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="4a107-155">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="4a107-155">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="4a107-156">Software Updates für Microsoft Teams-Chatrooms werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="4a107-156">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="4a107-157">Weitere Informationen finden Sie unter [Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) , um zu überprüfen, ob die Raum Konsole auf den Store zugreifen und sich selbst aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="4a107-157">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="4a107-158">Auswählen einer Sprache</span><span class="sxs-lookup"><span data-stu-id="4a107-158">Selecting a language</span></span> 

<span data-ttu-id="4a107-159">Im Update des Erstellers müssen Sie das ApplyCurrentRegionAndLanguage. ps1-Skript in Szenarien verwenden, in denen der Benutzer mit der impliziten Sprachauswahl nicht über die tatsächliche Anwendungssprache verfügt, die er verwenden soll (beispielsweise, dass die Konsolen-App auf Französisch bereitgestellt werden soll, aber Es kommt in Englisch vor.)</span><span class="sxs-lookup"><span data-stu-id="4a107-159">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a107-160">Die folgenden Anweisungen funktionieren nur für Konsolen, die mit dem Update von Windows Creator erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4a107-160">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="4a107-161">Legacy/in-Market-Systeme, die nicht mithilfe von Medien mit dem neuen Bereitstellungssystem eingerichtet wurden, können diese Anweisungen nicht verwenden, sollten aber auch nicht unter dem anfänglichen Problem leiden, das diesen manuellen Eingriff erfordert (Anniversary Edition ermöglicht es Ihnen, Ihre APP-Sprache explizit als Teil des Setups auszuwählen).</span><span class="sxs-lookup"><span data-stu-id="4a107-161">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="4a107-162">So wenden Sie die gewünschte Sprache an</span><span class="sxs-lookup"><span data-stu-id="4a107-162">To apply your desired language</span></span>

1. <span data-ttu-id="4a107-163">Wechseln Sie in den Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="4a107-163">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="4a107-164">Wählen Sie das Startmenü aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-164">Select the Start menu.</span></span>
    
3. <span data-ttu-id="4a107-165">Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.</span><span class="sxs-lookup"><span data-stu-id="4a107-165">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="4a107-166">Wählen **Sie &amp; Uhrzeit Sprache**aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-166">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="4a107-167">Wählen **Sie &amp; Regions Sprache**aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-167">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="4a107-168">Wählen Sie **Sprache hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-168">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="4a107-169">Wählen Sie die Sprache aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a107-169">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="4a107-170">Wählen Sie die Sprache aus, die Sie soeben in der Liste "Sprachen" hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="4a107-170">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="4a107-171">Wählen Sie **Als Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-171">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="4a107-172">Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="4a107-172">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="4a107-p115">a. Wählen Sie die Sprache aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="4a107-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="4a107-p116">b. Wählen Sie **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a107-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="4a107-177">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="4a107-177">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="4a107-178">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4a107-178">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="4a107-179">Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="4a107-179">Restart the system.</span></span>
    
<span data-ttu-id="4a107-180">Die gewünschte Sprache wird nun auf die Microsoft Teams rooms-Konsole angewendet.</span><span class="sxs-lookup"><span data-stu-id="4a107-180">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="4a107-181">Anfängliche Einrichtung der Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-181">Initial set up of the console</span></span>
<span data-ttu-id="4a107-182"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-182"></span></span>

<span data-ttu-id="4a107-183">Nach der Installation von Windows geht die Konsolen-App Microsoft Teams Rooms in den ersten Setup Prozess über, wenn Sie als nächstes gestartet wird oder wenn die/Reboot-Option ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a107-183">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="4a107-184">Der Bildschirm Benutzerkonto wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a107-184">The User Account screen appears.</span></span> <span data-ttu-id="4a107-185">Geben Sie die Skype-Anmeldeadresse (in User@Domain Format) des für die Konsole zu verwendenden Chatroom-Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="4a107-185">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="4a107-186">Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.</span><span class="sxs-lookup"><span data-stu-id="4a107-186">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="4a107-187">Legen Sie unter "Domäne konfigurieren" den FQDN für den Skype for Business-Server ein.</span><span class="sxs-lookup"><span data-stu-id="4a107-187">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="4a107-188">Wenn sich die Skype for Business-SIP-Domäne von der Exchange-Domäne des Benutzers unterscheidet, geben Sie die Exchange-Domäne in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="4a107-188">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="4a107-189">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4a107-189">Click **Next**.</span></span>
    
5. <span data-ttu-id="4a107-190">Wählen Sie auf dem Bildschirm Funktionen die angezeigten Geräte aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="4a107-190">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="4a107-191">Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a107-191">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="4a107-192">Die folgenden Geräte können ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="4a107-192">The devices to select are:</span></span>
    
   - <span data-ttu-id="4a107-193">Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum</span><span class="sxs-lookup"><span data-stu-id="4a107-193">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="4a107-194">Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen </span><span class="sxs-lookup"><span data-stu-id="4a107-194">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="4a107-195">Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="4a107-195">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="4a107-p120">Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="4a107-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="4a107-198">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4a107-198">Click **Finish**.</span></span>
    
<span data-ttu-id="4a107-199">Die Microsoft Teams rooms Console-app sollte sich sofort mit der Anmeldung bei Skype for Business Server mit den oben eingegebenen Anmeldeinformationen beginnen und auch mit der Synchronisierung Ihres Kalenders mit Exchange mit denselben Anmeldeinformationen beginnen.</span><span class="sxs-lookup"><span data-stu-id="4a107-199">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="4a107-200">Einzelheiten zur Verwendung der Konsolen-App finden Sie in der [Hilfe zu Microsoft Teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="4a107-200">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4a107-201">Microsoft Teams rooms beruht auf dem vorhanden sein zertifizierter Konsolen Hardware.</span><span class="sxs-lookup"><span data-stu-id="4a107-201">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="4a107-202">Selbst ein korrekt erstelltes Bild, das die Microsoft Teams rooms-Konsolen-app enthält, wird nicht über den anfänglichen Setupvorgang gestartet, es sei denn, die Konsolen Hardware wird erkannt.</span><span class="sxs-lookup"><span data-stu-id="4a107-202">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="4a107-203">Bei Surface pro-basierten Lösungen muss Surface pro mit der dazugehörigen Dock-Hardware verbunden sein, um diese Prüfung durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4a107-203">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a107-204">Einige Benutzer, die nicht in der englischen Sprache sind, benötigen möglicherweise während der Ersteinrichtung eine physische Tastatur, die mit der Konsole verbunden ist, falls Symbole auf der Bildschirmtastatur nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4a107-204">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="4a107-205">Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-205">Install a private CA certificate on the console</span></span>
<span data-ttu-id="4a107-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-206"></span></span>

<span data-ttu-id="4a107-207">Die Microsoft Teams rooms-Konsole muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit denen Sie eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="4a107-207">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="4a107-208">Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut.</span><span class="sxs-lookup"><span data-stu-id="4a107-208">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="4a107-209">In einem Fall, in dem die Zertifizierungsstelle privat ist, beispielsweise eine lokale Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle, können Sie das Zertifikat auf verschiedene Arten zur Konsole Microsoft Teams rooms hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4a107-209">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="4a107-210">Sie können die Konsole an Active Directory anschließen und automatisch die erforderlichen Zertifikate hinzufügen, wenn die Zertifizierungsstelle in Active Directory veröffentlicht wird (normale Bereitstellungsoption).</span><span class="sxs-lookup"><span data-stu-id="4a107-210">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="4a107-211">Sie können das Zertifikat nach der Imageerstellung manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="4a107-211">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="4a107-212">Bevor Sie dies tun, müssen Sie [die erste Einrichtung der Konsole](console.md#Initial)abschließen.</span><span class="sxs-lookup"><span data-stu-id="4a107-212">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="4a107-213">So installieren Sie das Zertifikat manuell </span><span class="sxs-lookup"><span data-stu-id="4a107-213">To manually install the certificate</span></span>

1. <span data-ttu-id="4a107-214">Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.</span><span class="sxs-lookup"><span data-stu-id="4a107-214">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="4a107-215">Setzen Sie die Konsole in den Administratormodus (siehe [Administratormodus und Geräteverwaltung](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="4a107-215">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="4a107-216">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4a107-216">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="4a107-217">Teilnehmen an einer Active Directory-Domäne (optional)</span><span class="sxs-lookup"><span data-stu-id="4a107-217">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="4a107-218"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-218"></span></span>

<span data-ttu-id="4a107-219">Sie können an Microsoft Teams rooms-Konsolen an Ihre Domäne teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4a107-219">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="4a107-220">Microsoft Teams rooms-Konsolen sollten in einer separaten ou von Ihren PC-Workstations installiert werden, da viele Arbeitsstations Richtlinien nicht mit Microsoft Teams-Räumen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="4a107-220">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="4a107-221">Ein allgemeines Beispiel sind Kenn Wort Erzwingungsrichtlinien, die verhindern, dass Microsoft Teams-Räume automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="4a107-221">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="4a107-222">Informationen zur Verwaltung von GPO-Einstellungen finden Sie unter Verwalten von [Microsoft Teams-Räumen](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4a107-222">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="4a107-223">So nehmen Sie an einer Domäne an Microsoft Teams-Chatrooms Teil</span><span class="sxs-lookup"><span data-stu-id="4a107-223">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="4a107-224">Registrieren Sie sich über das Administratorkonto bei der Konsole (siehe [Administratormodus und Geräteverwaltung](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="4a107-224">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="4a107-225">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="4a107-225">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="4a107-226">Geben Sie in PowerShell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4a107-226">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="4a107-227">Wenn Ihre vollqualifizierte Domäne beispielsweise Redmond.Corp.Microsoft.com ist und Sie möchten, dass sich Ihre Microsoft Teams rooms-Konsolen in einer OU "Microsoft Teams Rooms" befinden, die ein untergeordnetes Element einer "Resources"-ou ist, lautet der Befehl wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4a107-227">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="4a107-228">Wenn Sie den Computer umbenennen möchten, wenn Sie ihn einer Domäne hinzugefügt haben, verwenden Sie das-Name-Flag, gefolgt vom neuen Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="4a107-228">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="4a107-229">Checkliste für Microsoft Teams rooms-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="4a107-229">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="4a107-230"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-230"></span></span>

<span data-ttu-id="4a107-231">Verwenden Sie die folgende Checkliste, während Sie eine abschließende Überprüfung durchführen, dass die Konsole und alle zugehörigen Peripheriegeräte vollständig konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="4a107-231">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="4a107-232">**Anwendungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="4a107-232">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4a107-233">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-233">☐</span></span>  <br/> |<span data-ttu-id="4a107-234">Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a107-234">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="4a107-235">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-235">☐</span></span>  <br/> |<span data-ttu-id="4a107-236">Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="4a107-236">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="4a107-237">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-237">☐</span></span>  <br/> |<span data-ttu-id="4a107-238">Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.</span><span class="sxs-lookup"><span data-stu-id="4a107-238">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="4a107-239">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-239">☐</span></span>  <br/> |<span data-ttu-id="4a107-240">Alle Firmware-Updates wurden angewendet</span><span class="sxs-lookup"><span data-stu-id="4a107-240">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="4a107-241">**Audio/Video-Peripheriegeräte**</span><span class="sxs-lookup"><span data-stu-id="4a107-241">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4a107-242">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-242">☐</span></span>  <br/> |<span data-ttu-id="4a107-243">Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="4a107-243">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="4a107-244">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-244">☐</span></span>  <br/> |<span data-ttu-id="4a107-245">Kamera funktionell und optimal positioniert</span><span class="sxs-lookup"><span data-stu-id="4a107-245">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="4a107-246">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-246">☐</span></span>  <br/> |<span data-ttu-id="4a107-247">Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a107-247">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="4a107-248">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-248">☐</span></span>  <br/> |<span data-ttu-id="4a107-249">Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a107-249">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="4a107-250">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-250">☐</span></span>  <br/> |<span data-ttu-id="4a107-251">Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="4a107-251">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="4a107-252">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-252">☐</span></span>  <br/> |<span data-ttu-id="4a107-253">Das Audioeingabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="4a107-253">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="4a107-254">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-254">☐</span></span>  <br/> |<span data-ttu-id="4a107-255">Das Audioausgabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="4a107-255">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="4a107-256">**Dock**</span><span class="sxs-lookup"><span data-stu-id="4a107-256">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4a107-257">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-257">☐</span></span>  <br/> |<span data-ttu-id="4a107-258">Die Kabel sind sicher angeschlossen und nicht eingeklemmt.</span><span class="sxs-lookup"><span data-stu-id="4a107-258">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="4a107-259">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-259">☐</span></span>  <br/> |<span data-ttu-id="4a107-260">Die Audioerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="4a107-260">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="4a107-261">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-261">☐</span></span>  <br/> |<span data-ttu-id="4a107-262">Die Videoerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="4a107-262">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="4a107-263">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-263">☐</span></span>  <br/> |<span data-ttu-id="4a107-264">Das Dock lässt sich frei drehen.</span><span class="sxs-lookup"><span data-stu-id="4a107-264">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="4a107-265">☐</span><span class="sxs-lookup"><span data-stu-id="4a107-265">☐</span></span>  <br/> |<span data-ttu-id="4a107-266">Die Helligkeit des Bildschirms ist für die Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="4a107-266">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4a107-267">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a107-267">See also</span></span>
<span data-ttu-id="4a107-268"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="4a107-268"></span></span>

[<span data-ttu-id="4a107-269">Planen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="4a107-269">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="4a107-270">Bereitstellen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="4a107-270">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="4a107-271">Konfigurieren einer Microsoft Teams rooms-Konsole</span><span class="sxs-lookup"><span data-stu-id="4a107-271">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4a107-272">Microsoft Teams Rooms verwalten</span><span class="sxs-lookup"><span data-stu-id="4a107-272">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
