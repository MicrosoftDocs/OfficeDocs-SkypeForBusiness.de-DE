---
title: Konfigurieren einer Konsole für Skype Room Systems v2
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie die Skype Raum Systemen v2-Konsole und die zugehörigen Peripheriegeräte einrichten.
ms.openlocfilehash: 00203c8aa781c489d8a1cc8c2bf91a364bea057f
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694720"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="568ef-103">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="568ef-104">In diesem Artikel wird beschrieben, wie die Skype Raum Systemen v2-Konsole und die zugehörigen Peripheriegeräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="568ef-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="568ef-105">Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="568ef-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="568ef-106">Sie benötigen die Hardware und Software in [Skype Raum Systemen v2 Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="568ef-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="568ef-107">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="568ef-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="568ef-108">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="568ef-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="568ef-109">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="568ef-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="568ef-110">Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="568ef-111">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="568ef-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="568ef-112">Prüfliste für die Bereitstellung von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="568ef-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="568ef-113">Skype-Chatroom-Systemen v2 funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)ordnungsgemäß eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="568ef-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="568ef-114">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="568ef-114">Prepare the installation media</span></span>
<span data-ttu-id="568ef-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-115"></span></span>

<span data-ttu-id="568ef-116">Installieren der Skype Raum Systemen v2 Konsole-app erfordert ein USB-Speichergerät mit mindestens 32GB Kapazität.</span><span class="sxs-lookup"><span data-stu-id="568ef-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="568ef-117">Es sollte keine anderen Dateien auf dem Gerät vorhanden sein. alle vorhandenen Dateien auf den USB-Speicher geht verloren.</span><span class="sxs-lookup"><span data-stu-id="568ef-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="568ef-118">Fehler beim Skype Raum Systemen v2 Installationsmedium entsprechend diese Anweisungen wahrscheinlich in unerwartetes Verhalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="568ef-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="568ef-119">Der nachfolgend beschriebenen Vorgang ist für die Erstellung des-Installationsmedien Bild neue Skype Raum System v2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="568ef-119">The process below is for creating installation media to image new Skype Room System v2 devices.</span></span> <span data-ttu-id="568ef-120">Vorhandene Geräte aktualisieren standardmäßig automatisch aus Windows Update und den Windows Store.</span><span class="sxs-lookup"><span data-stu-id="568ef-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="568ef-121">Laden Sie das [Skript „CreateSrsMedia.ps1“](https://go.microsoft.com/fwlink/?linkid=867842) herunter. </span><span class="sxs-lookup"><span data-stu-id="568ef-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="568ef-122">Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="568ef-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="568ef-123">Führen Sie das Skript-Anweisungen, um eine Skype Raum Systemen v2 USB-Installationsdiskette erstellen.</span><span class="sxs-lookup"><span data-stu-id="568ef-123">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="568ef-124">Der Name des Ordners, den Sie das Medium Erstellungsskript aus ausführen kann keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="568ef-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="568ef-125">Das Skript schlägt fehl, wenn ein Leerzeichen in Ordnernamen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="568ef-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="568ef-126">Das Skript CreateSrsMedia.ps1 automatisiert die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="568ef-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="568ef-127">Laden Sie den neueste Version MSI-Installer für Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="568ef-127">Download the latest MSI installer for Skype Room Systems v2.</span></span>
2. <span data-ttu-id="568ef-128">Bestimmen des Builds von Windows, die der Benutzer eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="568ef-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="568ef-129">Die am häufigsten kürzlich veröffentlichten Versionen möglicherweise oder möglicherweise nicht getestet und für die Verwendung mit Skype Raum System v2 Geräte unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="568ef-129">The most recently released versions may or may not be tested and supported for use with Skype Room System v2 devices.</span></span>
3. <span data-ttu-id="568ef-130">Laden Sie die erforderliche unterstützende Komponenten.</span><span class="sxs-lookup"><span data-stu-id="568ef-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="568ef-131">Die erforderlichen Komponenten auf dem Installationsmedium zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="568ef-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="568ef-132">Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Skype Raum Systemen v2 Konsole app](console.md#Reimage)fort.</span><span class="sxs-lookup"><span data-stu-id="568ef-132">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="568ef-133">Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-133">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="568ef-134"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-134"></span></span>

<span data-ttu-id="568ef-135">Nun müssen Sie die Setup-Medien anwenden, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="568ef-135">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="568ef-136">Das Zielgerät wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Skype Raum Systemen v2 Konsole app ausgeführt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="568ef-136">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="568ef-137">Wenn das Zielgerät in ein (z. B. eine Surface Pro) Andocken installiert wird, trennen sie die Dockingstation.</span><span class="sxs-lookup"><span data-stu-id="568ef-137">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="568ef-138">Stellen Sie sicher, dass das Gerät nicht mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="568ef-138">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="568ef-139">Stellen Sie sicher, dass das Gerät mit Strom verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="568ef-139">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="568ef-140">Schließen Sie den USB-Setup-Speicher an das Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="568ef-140">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="568ef-141">Starten Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="568ef-141">Boot to the USB setup disk.</span></span> <span data-ttu-id="568ef-142">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="568ef-142">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="568ef-143">Wenn Ihr Zielgerät Surface Pro ist, gehen Sie folgendermaßen vor, der USB-Installationsdatenträger zu starten:</span><span class="sxs-lookup"><span data-stu-id="568ef-143">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="568ef-144">a.</span><span class="sxs-lookup"><span data-stu-id="568ef-144">a.</span></span> <span data-ttu-id="568ef-145">Halten Sie weiterhin die Lautstärke (-) gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="568ef-145">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="568ef-146">b.</span><span class="sxs-lookup"><span data-stu-id="568ef-146">b.</span></span> <span data-ttu-id="568ef-147">Drücken und halten.</span><span class="sxs-lookup"><span data-stu-id="568ef-147">Press and release the power button.</span></span>

    <span data-ttu-id="568ef-148">c.</span><span class="sxs-lookup"><span data-stu-id="568ef-148">c.</span></span> <span data-ttu-id="568ef-149">Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.</span><span class="sxs-lookup"><span data-stu-id="568ef-149">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="568ef-150">Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="568ef-150">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="568ef-151">Nachdem das System heruntergefahren hat, ist es sicher, entfernen Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="568ef-151">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="568ef-152">Zu diesem Zeitpunkt können Sie seine andocken (bei Verwendung von einem Produkt Andocken-basierte) das Zielgerät versehen, fügen Sie die Peripheriegeräte für Ihre Besprechungsraum erforderlich ist und mit dem Netzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="568ef-152">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="568ef-153">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="568ef-153">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="568ef-154">Auswählen einer Sprache</span><span class="sxs-lookup"><span data-stu-id="568ef-154">Selecting a language</span></span> 

<span data-ttu-id="568ef-155">In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B. möchten sie die Konsole-app in Französisch, angezeigt, aber Es ist in Englisch stattfindende).</span><span class="sxs-lookup"><span data-stu-id="568ef-155">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="568ef-156">Die folgenden Anweisungen funktionieren nur für Konsolen mithilfe des Erstellers Windows Update erstellt.</span><span class="sxs-lookup"><span data-stu-id="568ef-156">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="568ef-157">Legacy-Market/Systeme, die nicht eingerichtet wurde, die neue Bereitstellungssystem Medien mit werden nicht verwenden Sie diese Anweisungen, jedoch sollten auch nicht leiden unter das anfängliche Problem, das diese manuelle Eingriffe erfordert (Jahrestag Edition können Sie auswählen, Ihre App Sprache explizit als Teil des Setups).</span><span class="sxs-lookup"><span data-stu-id="568ef-157">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="568ef-158">So wenden Sie die gewünschte Sprache an</span><span class="sxs-lookup"><span data-stu-id="568ef-158">To apply your desired language</span></span>

1. <span data-ttu-id="568ef-159">Wechseln Sie in den Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="568ef-159">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="568ef-160">Wählen Sie das Startmenü aus.</span><span class="sxs-lookup"><span data-stu-id="568ef-160">Select the Start menu.</span></span>
    
3. <span data-ttu-id="568ef-161">Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.</span><span class="sxs-lookup"><span data-stu-id="568ef-161">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="568ef-162">Wählen Sie **Zeit &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="568ef-162">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="568ef-163">Wählen Sie **Region &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="568ef-163">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="568ef-164">Wählen Sie **Sprache hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="568ef-164">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="568ef-165">Wählen Sie die Sprache aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="568ef-165">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="568ef-166">Wählen Sie die Sprache, die Sie soeben hinzugefügt, um der Liste "Sprachen haben".</span><span class="sxs-lookup"><span data-stu-id="568ef-166">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="568ef-167">Wählen Sie **Als Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="568ef-167">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="568ef-168">Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="568ef-168">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="568ef-p113">a. Wählen Sie die Sprache aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="568ef-p113">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="568ef-p114">b. Wählen Sie **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="568ef-p114">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="568ef-173">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="568ef-173">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="568ef-174">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="568ef-174">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="568ef-175">Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="568ef-175">Restart the system.</span></span>
    
<span data-ttu-id="568ef-176">Die gewünschte Sprache wird jetzt in der Konsole der Skype Raum Systemen v2 angewendet.</span><span class="sxs-lookup"><span data-stu-id="568ef-176">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="568ef-177">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="568ef-177">Initial set up of the console</span></span>
<span data-ttu-id="568ef-178"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-178"></span></span>

<span data-ttu-id="568ef-179">Nach der Installation von Windows gehen die Skype Raum Systemen v2 Konsole app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="568ef-179">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="568ef-180">Der Benutzerkonto Bildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="568ef-180">The User Account screen appears.</span></span> <span data-ttu-id="568ef-181">Geben Sie die Skype-Anmeldeadresse ein (im Format user@domain) des Raums Kontos, das mit der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="568ef-181">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="568ef-182">Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.</span><span class="sxs-lookup"><span data-stu-id="568ef-182">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="568ef-183">Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest.</span><span class="sxs-lookup"><span data-stu-id="568ef-183">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="568ef-184">Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="568ef-184">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="568ef-185">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="568ef-185">Click **Next**.</span></span>
    
5. <span data-ttu-id="568ef-186">Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="568ef-186">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="568ef-187">Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="568ef-187">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="568ef-188">Die folgenden Geräte können ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="568ef-188">The devices to select are:</span></span>
    
   - <span data-ttu-id="568ef-189">Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum</span><span class="sxs-lookup"><span data-stu-id="568ef-189">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="568ef-190">Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen </span><span class="sxs-lookup"><span data-stu-id="568ef-190">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="568ef-191">Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="568ef-191">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="568ef-p118">Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="568ef-p118">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="568ef-194">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="568ef-194">Click **Finish**.</span></span>
    
<span data-ttu-id="568ef-195">Die Skype Raum Systemen v2 Konsole app Anmelden bei Skype für Business Server mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch die Synchronisierung der Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="568ef-195">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="568ef-196">Ausführliche Informationen zum Verwenden der Verwaltungskonsole app finden Sie in der [Hilfe Skype Raum Systeme, Version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="568ef-196">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="568ef-197">Skype Raum Systemen v2 erfordert das Vorhandensein von zertifizierten Konsole Hardware.</span><span class="sxs-lookup"><span data-stu-id="568ef-197">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="568ef-198">Sogar eine ordnungsgemäß erstellte Image, enthält die Skype Raum Systemen v2 Konsole app kann nicht nach der Erstinstallation Verfahren starten, es sei denn, die Konsole Hardware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="568ef-198">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="568ef-199">Für Surface Pro-basierte Lösungen muss die Surface Pro für die zugehörige Andocken Hardware, übergeben dieses Kontrollkästchen verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="568ef-199">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="568ef-200">Möglicherweise benötigen einige Benutzer nicht-englischen eine physische Tastatur während des Setups mit der Konsole verbunden, Symbole auf der Bildschirmtastatur nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="568ef-200">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="568ef-201">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="568ef-201">Install a private CA certificate on the console</span></span>
<span data-ttu-id="568ef-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-202"></span></span>

<span data-ttu-id="568ef-203">Die Skype Raum Systemen v2-Konsole muss Zertifikate von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="568ef-203">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="568ef-204">Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut.</span><span class="sxs-lookup"><span data-stu-id="568ef-204">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="568ef-205">In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat der Skype Raum Systemen v2-Konsole in eine Reihe von Methoden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="568ef-205">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="568ef-206">Sie können die Konsole Active Directory teilnehmen und, die werden automatisch hinzugefügt, die erforderlichen Zertifikate erhält der Zertifizierungsstelle auf Active Directory (normale Bereitstellungsoption) veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="568ef-206">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="568ef-207">Sie können das Zertifikat nach der Imageerstellung manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="568ef-207">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="568ef-208">Bevor Sie dies tun, müssen Sie die [Initial Einrichten der Konsole](console.md#Initial)durchführen.</span><span class="sxs-lookup"><span data-stu-id="568ef-208">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="568ef-209">So installieren Sie das Zertifikat manuell </span><span class="sxs-lookup"><span data-stu-id="568ef-209">To manually install the certificate</span></span>

1. <span data-ttu-id="568ef-210">Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.</span><span class="sxs-lookup"><span data-stu-id="568ef-210">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="568ef-211">Platzieren Sie die Konsole im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="568ef-211">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="568ef-212">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="568ef-212">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="568ef-213">Teilnehmen an einer Active Directory-Domäne (Optional)</span><span class="sxs-lookup"><span data-stu-id="568ef-213">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="568ef-214"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-214"></span></span>

<span data-ttu-id="568ef-215">Sie können Skype Raum Systemen v2 Konsolen an Ihre Domäne beitreten.</span><span class="sxs-lookup"><span data-stu-id="568ef-215">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="568ef-216">Skype Raum Systemen v2 Konsolen sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht mit Skype Raum Systemen v2 kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="568ef-216">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="568ef-217">Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die verhindern Skype Raum Systemen v2 automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="568ef-217">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="568ef-218">Weitere Informationen zur Verwaltung von GPO-Einstellungen finden Sie unter [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="568ef-218">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="568ef-219">So verbinden Sie Skype Room Systems v2 durch einen Domänenbeitritt mit einer Domäne</span><span class="sxs-lookup"><span data-stu-id="568ef-219">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="568ef-220">Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="568ef-220">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="568ef-221">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="568ef-221">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="568ef-222">Geben Sie in PowerShell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="568ef-222">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="568ef-223">Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten Ihre Skype Raum Systemen v2 Konsolen "Skype Raum Systemen v2" werden beispielsweise Organisationseinheit, die ein untergeordnetes Element des einer OU "Ressourcen" ist der Befehl werden:</span><span class="sxs-lookup"><span data-stu-id="568ef-223">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="568ef-224">Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.</span><span class="sxs-lookup"><span data-stu-id="568ef-224">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="568ef-225">Prüfliste für die Bereitstellung von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="568ef-225">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="568ef-226"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-226"></span></span>

<span data-ttu-id="568ef-227">Verwenden Sie die folgende Checkliste, während eine endgültige Überprüfung, dass die Konsole und alle zugehörigen Peripheriegeräte konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="568ef-227">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="568ef-228">**Anwendungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="568ef-228">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568ef-229">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-229">☐</span></span>  <br/> |<span data-ttu-id="568ef-230">Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="568ef-230">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="568ef-231">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-231">☐</span></span>  <br/> |<span data-ttu-id="568ef-232">Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="568ef-232">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="568ef-233">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-233">☐</span></span>  <br/> |<span data-ttu-id="568ef-234">Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.</span><span class="sxs-lookup"><span data-stu-id="568ef-234">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="568ef-235">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-235">☐</span></span>  <br/> |<span data-ttu-id="568ef-236">Alle Firmwareupdates wurden angewendet</span><span class="sxs-lookup"><span data-stu-id="568ef-236">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="568ef-237">**A/v-Peripheriegeräte**</span><span class="sxs-lookup"><span data-stu-id="568ef-237">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568ef-238">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-238">☐</span></span>  <br/> |<span data-ttu-id="568ef-239">Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="568ef-239">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="568ef-240">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-240">☐</span></span>  <br/> |<span data-ttu-id="568ef-241">Kamera funktionale und optimal positioniert</span><span class="sxs-lookup"><span data-stu-id="568ef-241">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="568ef-242">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-242">☐</span></span>  <br/> |<span data-ttu-id="568ef-243">Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="568ef-243">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="568ef-244">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-244">☐</span></span>  <br/> |<span data-ttu-id="568ef-245">Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="568ef-245">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="568ef-246">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-246">☐</span></span>  <br/> |<span data-ttu-id="568ef-247">Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="568ef-247">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="568ef-248">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-248">☐</span></span>  <br/> |<span data-ttu-id="568ef-249">Das Audioeingabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="568ef-249">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="568ef-250">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-250">☐</span></span>  <br/> |<span data-ttu-id="568ef-251">Das Audioausgabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="568ef-251">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="568ef-252">**Dock**</span><span class="sxs-lookup"><span data-stu-id="568ef-252">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568ef-253">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-253">☐</span></span>  <br/> |<span data-ttu-id="568ef-254">Die Kabel sind sicher angeschlossen und nicht eingeklemmt.</span><span class="sxs-lookup"><span data-stu-id="568ef-254">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="568ef-255">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-255">☐</span></span>  <br/> |<span data-ttu-id="568ef-256">Die Audioerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="568ef-256">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="568ef-257">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-257">☐</span></span>  <br/> |<span data-ttu-id="568ef-258">Die Videoerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="568ef-258">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="568ef-259">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-259">☐</span></span>  <br/> |<span data-ttu-id="568ef-260">Das Dock lässt sich frei drehen.</span><span class="sxs-lookup"><span data-stu-id="568ef-260">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="568ef-261">☐</span><span class="sxs-lookup"><span data-stu-id="568ef-261">☐</span></span>  <br/> |<span data-ttu-id="568ef-262">Die Helligkeit des Bildschirms ist für die Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="568ef-262">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="568ef-263">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="568ef-263">See also</span></span>
<span data-ttu-id="568ef-264"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="568ef-264"></span></span>

[<span data-ttu-id="568ef-265">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-265">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="568ef-266">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-266">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="568ef-267">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-267">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="568ef-268">Verwalten von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="568ef-268">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)