---
title: Konfigurieren einer Microsoft-Teams Räume-Konsole
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie die Microsoft-Teams Räume-Konsole und zugehörigen Peripheriegeräte einrichten.
ms.openlocfilehash: fc1d50ffe6dd7415848e02571eab1484bd3dfe22
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012613"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="406dc-103">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="406dc-104">In diesem Artikel wird beschrieben, wie die Microsoft-Teams Räume-Konsole und zugehörigen Peripheriegeräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="406dc-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="406dc-105">Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="406dc-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="406dc-106">Sie benötigen die Hardware und Software, die in [Microsoft Teams Chatrooms Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="406dc-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="406dc-107">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="406dc-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="406dc-108">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="406dc-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="406dc-109">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="406dc-110">Installieren Sie Windows 10 und die Microsoft-Teams Chatrooms Konsole-app</span><span class="sxs-lookup"><span data-stu-id="406dc-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="406dc-111">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="406dc-112">Prüfliste für die Bereitstellung von Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="406dc-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="406dc-113">Microsoft-Teams Chatrooms funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md)ordnungsgemäß eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="406dc-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="406dc-114">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="406dc-114">Prepare the installation media</span></span>
<span data-ttu-id="406dc-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-115"></span></span>

<span data-ttu-id="406dc-116">Installieren der Microsoft-Teams Chatrooms Konsole-app erfordert ein USB-Speichergerät mit mindestens 32GB Kapazität.</span><span class="sxs-lookup"><span data-stu-id="406dc-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="406dc-117">Es sollte keine anderen Dateien auf dem Gerät vorhanden sein. alle vorhandenen Dateien auf den USB-Speicher geht verloren.</span><span class="sxs-lookup"><span data-stu-id="406dc-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="406dc-118">Fehler bei die Microsoft-Teams Chatrooms Installationsmedien entsprechend diese Anweisungen wahrscheinlich in unerwartetes Verhalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="406dc-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="406dc-119">Der nachfolgend beschriebenen Vorgang ist für das Erstellen Installationsmedium Bild neue Microsoft-Teams Chatrooms Geräte.</span><span class="sxs-lookup"><span data-stu-id="406dc-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="406dc-120">Vorhandene Geräte aktualisieren standardmäßig automatisch aus Windows Update und den Windows Store.</span><span class="sxs-lookup"><span data-stu-id="406dc-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="406dc-121">Laden Sie das [Skript CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="406dc-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="406dc-122">Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="406dc-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="406dc-123">Führen Sie das Skript-Anweisungen, um eine Microsoft-Teams Chatrooms USB-Installationsdiskette erstellen.</span><span class="sxs-lookup"><span data-stu-id="406dc-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="406dc-124">Der Name des Ordners, den Sie das Medium Erstellungsskript aus ausführen kann keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="406dc-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="406dc-125">Das Skript schlägt fehl, wenn ein Leerzeichen in Ordnernamen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="406dc-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="406dc-126">Das Skript CreateSrsMedia.ps1 automatisiert die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="406dc-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="406dc-127">Laden Sie den neueste Version MSI-Installer für Microsoft-Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="406dc-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="406dc-128">Bestimmen des Builds von Windows, die der Benutzer eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="406dc-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="406dc-129">Die am häufigsten kürzlich veröffentlichten Versionen möglicherweise oder möglicherweise nicht getestet und für die Verwendung mit Microsoft-Teams Chatrooms Geräte unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="406dc-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="406dc-130">Laden Sie die erforderliche unterstützende Komponenten.</span><span class="sxs-lookup"><span data-stu-id="406dc-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="406dc-131">Die erforderlichen Komponenten auf dem Installationsmedium zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="406dc-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="406dc-132">Eine bestimmte Version von Windows 10 ist erforderlich, und dieser Version ist nur verfügbar für Volume licensing-Kunden.</span><span class="sxs-lookup"><span data-stu-id="406dc-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="406dc-133">Sie können eine Kopie aus dem [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/)abrufen.</span><span class="sxs-lookup"><span data-stu-id="406dc-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="406dc-134">Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Microsoft-Teams Räume console app](console.md#Reimage)fort.</span><span class="sxs-lookup"><span data-stu-id="406dc-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="406dc-135">Installieren Sie Windows 10 und die Microsoft-Teams Chatrooms Konsole-app</span><span class="sxs-lookup"><span data-stu-id="406dc-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="406dc-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-136"></span></span>

<span data-ttu-id="406dc-137">Nun müssen Sie die Setup-Medien anwenden, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="406dc-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="406dc-138">Das Zielgerät wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Microsoft-Teams Chatrooms Konsole app ausgeführt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="406dc-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="406dc-139">Wenn das Zielgerät in ein (z. B. eine Surface Pro) Andocken installiert wird, trennen sie die Dockingstation.</span><span class="sxs-lookup"><span data-stu-id="406dc-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="406dc-140">Stellen Sie sicher, dass das Gerät nicht mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="406dc-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="406dc-141">Stellen Sie sicher, dass das Gerät mit Strom verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="406dc-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="406dc-142">Schließen Sie den USB-Setup-Speicher an das Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="406dc-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="406dc-143">Starten Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="406dc-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="406dc-144">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="406dc-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="406dc-145">Wenn Ihr Zielgerät Surface Pro ist, gehen Sie folgendermaßen vor, der USB-Installationsdatenträger zu starten:</span><span class="sxs-lookup"><span data-stu-id="406dc-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="406dc-146">a.</span><span class="sxs-lookup"><span data-stu-id="406dc-146">a.</span></span> <span data-ttu-id="406dc-147">Halten Sie weiterhin die Lautstärke (-) gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="406dc-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="406dc-148">b.</span><span class="sxs-lookup"><span data-stu-id="406dc-148">b.</span></span> <span data-ttu-id="406dc-149">Drücken und halten.</span><span class="sxs-lookup"><span data-stu-id="406dc-149">Press and release the power button.</span></span>

    <span data-ttu-id="406dc-150">c.</span><span class="sxs-lookup"><span data-stu-id="406dc-150">c.</span></span> <span data-ttu-id="406dc-151">Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.</span><span class="sxs-lookup"><span data-stu-id="406dc-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="406dc-152">Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="406dc-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="406dc-153">Nachdem das System heruntergefahren hat, ist es sicher, entfernen Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="406dc-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="406dc-154">Zu diesem Zeitpunkt können Sie seine andocken (bei Verwendung von einem Produkt Andocken-basierte) das Zielgerät versehen, fügen Sie die Peripheriegeräte für Ihre Besprechungsraum erforderlich ist und mit dem Netzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="406dc-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="406dc-155">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="406dc-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="406dc-156">Auswählen einer Sprache</span><span class="sxs-lookup"><span data-stu-id="406dc-156">Selecting a language</span></span> 

<span data-ttu-id="406dc-157">In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B. möchten sie die Konsole-app in Französisch, angezeigt, aber Es ist in Englisch stattfindende).</span><span class="sxs-lookup"><span data-stu-id="406dc-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="406dc-158">Die folgenden Anweisungen funktionieren nur für Konsolen mithilfe des Erstellers Windows Update erstellt.</span><span class="sxs-lookup"><span data-stu-id="406dc-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="406dc-159">Legacy-Market/Systeme, die nicht eingerichtet wurde, die neue Bereitstellungssystem Medien mit werden nicht verwenden Sie diese Anweisungen, jedoch sollten auch nicht leiden unter das anfängliche Problem, das diese manuelle Eingriffe erfordert (Jahrestag Edition können Sie auswählen, Ihre App Sprache explizit als Teil des Setups).</span><span class="sxs-lookup"><span data-stu-id="406dc-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="406dc-160">So wenden Sie die gewünschte Sprache an</span><span class="sxs-lookup"><span data-stu-id="406dc-160">To apply your desired language</span></span>

1. <span data-ttu-id="406dc-161">Wechseln Sie in den Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="406dc-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="406dc-162">Wählen Sie das Startmenü aus.</span><span class="sxs-lookup"><span data-stu-id="406dc-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="406dc-163">Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.</span><span class="sxs-lookup"><span data-stu-id="406dc-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="406dc-164">Wählen Sie **Zeit &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="406dc-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="406dc-165">Wählen Sie **Region &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="406dc-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="406dc-166">Wählen Sie **Sprache hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="406dc-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="406dc-167">Wählen Sie die Sprache aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="406dc-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="406dc-168">Wählen Sie die Sprache, die Sie soeben hinzugefügt, um der Liste "Sprachen haben".</span><span class="sxs-lookup"><span data-stu-id="406dc-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="406dc-169">Wählen Sie **Als Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="406dc-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="406dc-170">Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="406dc-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="406dc-p114">a. Wählen Sie die Sprache aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="406dc-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="406dc-p115">b. Wählen Sie **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="406dc-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="406dc-175">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="406dc-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="406dc-176">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="406dc-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="406dc-177">Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="406dc-177">Restart the system.</span></span>
    
<span data-ttu-id="406dc-178">Die gewünschte Sprache ist jetzt auf der Microsoft-Teams Chatrooms Konsole angewendet.</span><span class="sxs-lookup"><span data-stu-id="406dc-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="406dc-179">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-179">Initial set up of the console</span></span>
<span data-ttu-id="406dc-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-180"></span></span>

<span data-ttu-id="406dc-181">Nach der Installation von Windows gehen die Microsoft-Teams Chatrooms Konsole app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="406dc-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="406dc-182">Der Benutzerkonto Bildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="406dc-182">The User Account screen appears.</span></span> <span data-ttu-id="406dc-183">Geben Sie die Skype-Anmeldeadresse ein (im Format user@domain) des Raums Kontos, das mit der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="406dc-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="406dc-184">Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.</span><span class="sxs-lookup"><span data-stu-id="406dc-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="406dc-185">Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest.</span><span class="sxs-lookup"><span data-stu-id="406dc-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="406dc-186">Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="406dc-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="406dc-187">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="406dc-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="406dc-188">Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="406dc-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="406dc-189">Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="406dc-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="406dc-190">Die folgenden Geräte können ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="406dc-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="406dc-191">Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum</span><span class="sxs-lookup"><span data-stu-id="406dc-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="406dc-192">Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen </span><span class="sxs-lookup"><span data-stu-id="406dc-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="406dc-193">Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="406dc-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="406dc-p119">Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="406dc-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="406dc-196">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="406dc-196">Click **Finish**.</span></span>
    
<span data-ttu-id="406dc-197">Die Microsoft-Teams Chatrooms Konsole app Anmelden bei Skype für Business Server mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch den Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden wird synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="406dc-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="406dc-198">Ausführliche Informationen zum Verwenden der Verwaltungskonsole app finden Sie in der [Hilfe von Microsoft Teams Chatrooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="406dc-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="406dc-199">Microsoft-Teams Chatrooms erfordert das Vorhandensein von zertifizierten Konsole Hardware.</span><span class="sxs-lookup"><span data-stu-id="406dc-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="406dc-200">Selbst ein Bild ordnungsgemäß erstellte, enthält die Microsoft-Teams Chatrooms Konsole app startet nicht nach der Erstinstallation Verfahren, wenn die Konsole Hardware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="406dc-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="406dc-201">Für Surface Pro-basierte Lösungen muss die Surface Pro für die zugehörige Andocken Hardware, übergeben dieses Kontrollkästchen verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="406dc-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="406dc-202">Möglicherweise benötigen einige Benutzer nicht-englischen eine physische Tastatur während des Setups mit der Konsole verbunden, Symbole auf der Bildschirmtastatur nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="406dc-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="406dc-203">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="406dc-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-204"></span></span>

<span data-ttu-id="406dc-205">Zertifikate wird von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit muss die Microsoft-Teams Chatrooms Konsole.</span><span class="sxs-lookup"><span data-stu-id="406dc-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="406dc-206">Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut.</span><span class="sxs-lookup"><span data-stu-id="406dc-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="406dc-207">In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat auf der Microsoft-Teams Räume-Konsole in eine Reihe von Methoden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="406dc-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="406dc-208">Sie können die Konsole Active Directory teilnehmen und, die werden automatisch hinzugefügt, die erforderlichen Zertifikate erhält der Zertifizierungsstelle auf Active Directory (normale Bereitstellungsoption) veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="406dc-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="406dc-209">Sie können das Zertifikat nach der Imageerstellung manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="406dc-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="406dc-210">Bevor Sie dies tun, müssen Sie die [Initial Einrichten der Konsole](console.md#Initial)durchführen.</span><span class="sxs-lookup"><span data-stu-id="406dc-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="406dc-211">So installieren Sie das Zertifikat manuell </span><span class="sxs-lookup"><span data-stu-id="406dc-211">To manually install the certificate</span></span>

1. <span data-ttu-id="406dc-212">Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.</span><span class="sxs-lookup"><span data-stu-id="406dc-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="406dc-213">Platzieren Sie die Konsole im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="406dc-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="406dc-214">Führen Sie den folgenden Befehl aus:  </span><span class="sxs-lookup"><span data-stu-id="406dc-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="406dc-215">Teilnehmen an einer Active Directory-Domäne (Optional)</span><span class="sxs-lookup"><span data-stu-id="406dc-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="406dc-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-216"></span></span>

<span data-ttu-id="406dc-217">Sie können Microsoft Teams Chatrooms Konsolen an Ihre Domäne beitreten.</span><span class="sxs-lookup"><span data-stu-id="406dc-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="406dc-218">Microsoft-Teams Chatrooms Konsolen sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht kompatibel mit Microsoft-Teams Räumen sind.</span><span class="sxs-lookup"><span data-stu-id="406dc-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="406dc-219">Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die Microsoft-Teams Chatrooms verhindern automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="406dc-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="406dc-220">Informationen über die Verwaltung der Gruppenrichtlinienergebnisse finden Sie unter [Verwalten von Microsoft Teams Räumen](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="406dc-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="406dc-221">Microsoft-Teams Chatrooms einer Domäne beitreten</span><span class="sxs-lookup"><span data-stu-id="406dc-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="406dc-222">Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="406dc-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="406dc-223">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="406dc-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="406dc-224">Geben Sie in PowerShell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="406dc-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="406dc-225">Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten die Microsoft-Teams Chatrooms Konsolen in einer Organisationseinheit "Microsoft-Teams Rooms" sein, die ein untergeordnetes Element des einer OU "Ressourcen" ist, kann beispielsweise der Befehl werden:</span><span class="sxs-lookup"><span data-stu-id="406dc-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="406dc-226">Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.</span><span class="sxs-lookup"><span data-stu-id="406dc-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="406dc-227">Prüfliste für die Bereitstellung von Microsoft-Teams Räume</span><span class="sxs-lookup"><span data-stu-id="406dc-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="406dc-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-228"></span></span>

<span data-ttu-id="406dc-229">Verwenden Sie die folgende Checkliste, während eine endgültige Überprüfung, dass die Konsole und alle zugehörigen Peripheriegeräte konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="406dc-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="406dc-230">**Anwendungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="406dc-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="406dc-231">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-231">☐</span></span>  <br/> |<span data-ttu-id="406dc-232">Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="406dc-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="406dc-233">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-233">☐</span></span>  <br/> |<span data-ttu-id="406dc-234">Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="406dc-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="406dc-235">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-235">☐</span></span>  <br/> |<span data-ttu-id="406dc-236">Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.</span><span class="sxs-lookup"><span data-stu-id="406dc-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="406dc-237">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-237">☐</span></span>  <br/> |<span data-ttu-id="406dc-238">Alle Firmwareupdates wurden angewendet</span><span class="sxs-lookup"><span data-stu-id="406dc-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="406dc-239">**A/v-Peripheriegeräte**</span><span class="sxs-lookup"><span data-stu-id="406dc-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="406dc-240">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-240">☐</span></span>  <br/> |<span data-ttu-id="406dc-241">Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="406dc-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="406dc-242">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-242">☐</span></span>  <br/> |<span data-ttu-id="406dc-243">Kamera funktionale und optimal positioniert</span><span class="sxs-lookup"><span data-stu-id="406dc-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="406dc-244">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-244">☐</span></span>  <br/> |<span data-ttu-id="406dc-245">Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="406dc-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="406dc-246">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-246">☐</span></span>  <br/> |<span data-ttu-id="406dc-247">Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="406dc-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="406dc-248">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-248">☐</span></span>  <br/> |<span data-ttu-id="406dc-249">Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="406dc-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="406dc-250">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-250">☐</span></span>  <br/> |<span data-ttu-id="406dc-251">Das Audioeingabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="406dc-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="406dc-252">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-252">☐</span></span>  <br/> |<span data-ttu-id="406dc-253">Das Audioausgabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="406dc-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="406dc-254">**Dock**</span><span class="sxs-lookup"><span data-stu-id="406dc-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="406dc-255">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-255">☐</span></span>  <br/> |<span data-ttu-id="406dc-256">Die Kabel sind sicher angeschlossen und nicht eingeklemmt.</span><span class="sxs-lookup"><span data-stu-id="406dc-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="406dc-257">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-257">☐</span></span>  <br/> |<span data-ttu-id="406dc-258">Die Audioerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="406dc-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="406dc-259">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-259">☐</span></span>  <br/> |<span data-ttu-id="406dc-260">Die Videoerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="406dc-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="406dc-261">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-261">☐</span></span>  <br/> |<span data-ttu-id="406dc-262">Das Dock lässt sich frei drehen.</span><span class="sxs-lookup"><span data-stu-id="406dc-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="406dc-263">☐</span><span class="sxs-lookup"><span data-stu-id="406dc-263">☐</span></span>  <br/> |<span data-ttu-id="406dc-264">Die Helligkeit des Bildschirms ist für die Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="406dc-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="406dc-265">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="406dc-265">See also</span></span>
<span data-ttu-id="406dc-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="406dc-266"></span></span>

[<span data-ttu-id="406dc-267">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="406dc-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="406dc-268">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="406dc-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="406dc-269">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="406dc-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="406dc-270">Verwalten von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="406dc-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)