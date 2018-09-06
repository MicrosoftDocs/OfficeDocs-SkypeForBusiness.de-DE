---
title: Konfigurieren einer Konsole für Skype Room Systems v2
ms.author: jambirk
author: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie die Skype Raum Systemen v2-Konsole und die zugehörigen Peripheriegeräte einrichten.
ms.openlocfilehash: c2be3c1a8ee36120eac0198da364ab0101ae482e
ms.sourcegitcommit: 53c10589c284c6e4bbba574a7ba2df2d29519d1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "23828715"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="0e4b9-103">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="0e4b9-104">In diesem Artikel wird beschrieben, wie die Skype Raum Systemen v2-Konsole und die zugehörigen Peripheriegeräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="0e4b9-105">Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="0e4b9-106">Sie benötigen die Hardware und Software in [Skype Raum Systemen v2 Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="0e4b9-107">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="0e4b9-108">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="0e4b9-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="0e4b9-109">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="0e4b9-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="0e4b9-110">Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="0e4b9-111">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="0e4b9-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="0e4b9-112">Prüfliste für die Bereitstellung von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="0e4b9-113">Skype-Chatroom-Systemen v2 funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)ordnungsgemäß eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="0e4b9-114">Vorbereiten der Installationsmedien</span><span class="sxs-lookup"><span data-stu-id="0e4b9-114">Prepare the installation media</span></span>
<span data-ttu-id="0e4b9-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-115"></span></span>

<span data-ttu-id="0e4b9-116">Installieren der Skype Raum Systemen v2 Konsole-app erfordert ein USB-Speichergerät mit mindestens 32GB Arbeitsspeicher als FAT32 Datenträger formatiert.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="0e4b9-117">Auf dem Gerät sollten sich keine anderen Dateien befinden. Im USB-Speicher vorhandene Dateien gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e4b9-118">Fehler beim Skype Raum Systemen v2 Installationsmedium entsprechend diese Anweisungen wahrscheinlich in unerwartetes Verhalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="0e4b9-119">Windows 10 Enterprise Jahrestag Update (Version 1607) ist für die Erstellung von Skype Raum Systemen v2 Installation Medien nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e4b9-120">Eine vorhandene v2 Skype Raum Systeme mit Windows 10 Enterprise Jahrestag Update verschieben in Skype Raum Systemen v2 Update 3 über die Windows Store ausgeführt werden, jedoch sollte eine neue Installation durchgeführt werden, wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="0e4b9-121">Laden Sie das [Skript CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="0e4b9-122">(Optional) Herunterladen Sie, und platzieren Sie alle gewünschten Language Pack CAB-Dateien im gleichen Verzeichnis befindet wie das Skript.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="0e4b9-123">Das Skript wird angegeben, in dem Sie Language Pack-Dateien für den Typ von Medien, die Sie erstellen, die Wenn Sie nicht sicher sind, wo Sie die Language Packs von erwerben sind herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="0e4b9-124">Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="0e4b9-125">Führen Sie das Skript-Anweisungen, um eine Skype Raum Systemen v2 USB-Installationsdiskette erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="0e4b9-126">Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Skype Raum Systemen v2 Konsole app](console.md#Reimage)fort.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="0e4b9-127">Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="0e4b9-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-128"></span></span>

<span data-ttu-id="0e4b9-129">Nun müssen Sie die Setup-Medien anwenden, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-129">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="0e4b9-130">Das Zielgerät wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Skype Raum Systemen v2 Konsole app ausgeführt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-130">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="0e4b9-131">Wenn das Zielgerät in ein (z. B. eine Surface Pro) Andocken installiert wird, trennen sie die Dockingstation.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-131">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="0e4b9-132">Stellen Sie sicher, dass das Gerät nicht mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-132">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="0e4b9-133">Stellen Sie sicher, dass das Gerät mit Strom verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-133">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="0e4b9-134">Schließen Sie den USB-Setup-Speicher an das Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-134">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="0e4b9-135">Starten Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-135">Boot to the USB setup disk.</span></span> <span data-ttu-id="0e4b9-136">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-136">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="0e4b9-137">Wenn Ihr Zielgerät Surface Pro ist, gehen Sie folgendermaßen vor, der USB-Installationsdatenträger zu starten:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-137">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="0e4b9-138">Halten Sie weiterhin die Lautstärke (-) gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-138">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="0e4b9-139">Drücken und halten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-139">Press and release the power button.</span></span>

    3. <span data-ttu-id="0e4b9-140">Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-140">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="0e4b9-141">Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-141">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="0e4b9-142">Nachdem das System heruntergefahren hat, ist es sicher, entfernen Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-142">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="0e4b9-143">Zu diesem Zeitpunkt können Sie seine andocken (bei Verwendung von einem Produkt Andocken-basierte) das Ziel Devcie versehen, fügen Sie die Peripheriegeräte für Ihre Besprechungsraum erforderlich ist und mit dem Netzwerk verbunden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-143">At this point, you can place the target devcie in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="0e4b9-144">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-144">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="0e4b9-145">Auswählen einer Sprache in Creators Update</span><span class="sxs-lookup"><span data-stu-id="0e4b9-145">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="0e4b9-146">In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B. möchten sie die Konsole-app in Französisch, angezeigt, aber Es ist in Englisch stattfindende).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-146">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e4b9-147">Die folgenden Anweisungen funktionieren nur für Konsolen mithilfe des Erstellers Windows Update erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-147">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="0e4b9-148">Legacy-Market/Systeme, die nicht eingerichtet wurde, die neue Bereitstellungssystem Medien mit werden nicht verwenden Sie diese Anweisungen, jedoch sollten auch nicht leiden unter das anfängliche Problem, das diese manuelle Eingriffe erfordert (Jahrestag Edition können Sie auswählen, Ihre App Sprache explizit als Teil des Setups).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-148">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="0e4b9-149">So wenden Sie die gewünschte Sprache an</span><span class="sxs-lookup"><span data-stu-id="0e4b9-149">To apply your desired language</span></span>

1. <span data-ttu-id="0e4b9-150">Wechseln Sie in den Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-150">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="0e4b9-151">Wählen Sie das Startmenü aus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-151">Select the Start menu.</span></span>
    
3. <span data-ttu-id="0e4b9-152">Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-152">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="0e4b9-153">Wählen Sie **Zeit &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-153">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="0e4b9-154">Wählen Sie **Region &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-154">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="0e4b9-155">Wählen Sie **Sprache hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-155">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="0e4b9-156">Wählen Sie die Sprache aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-156">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="0e4b9-157">Wählen Sie die Sprache, die Sie soeben hinzugefügt, um der Liste "Sprachen haben".</span><span class="sxs-lookup"><span data-stu-id="0e4b9-157">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="0e4b9-158">Wählen Sie **Als Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-158">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="0e4b9-159">Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-159">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="0e4b9-160">a.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-160">a.</span></span> <span data-ttu-id="0e4b9-161">Wählen Sie die Sprache aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-161">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="0e4b9-162">b.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-162">b.</span></span> <span data-ttu-id="0e4b9-163">Wählen Sie **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-163">Select **Remove**.</span></span>
    
11. <span data-ttu-id="0e4b9-164">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-164">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="0e4b9-165">Führen Sie den folgenden Befehl aus: </span><span class="sxs-lookup"><span data-stu-id="0e4b9-165">Run the following command:</span></span> 
    
    <span data-ttu-id="0e4b9-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="0e4b9-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="0e4b9-167">Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-167">Restart the system.</span></span>
    
<span data-ttu-id="0e4b9-168">Die gewünschte Sprache wird jetzt in der Konsole der Skype Raum Systemen v2 angewendet.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-168">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="0e4b9-169">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="0e4b9-169">Initial set up of the console</span></span>
<span data-ttu-id="0e4b9-170"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-170"></span></span>

<span data-ttu-id="0e4b9-171">Nach der Installation von Windows gehen die Skype Raum Systemen v2 Konsole app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-171">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="0e4b9-172">Der Benutzerkonto Bildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-172">The User Account screen appears.</span></span> <span data-ttu-id="0e4b9-173">Geben Sie die Skype-Anmeldeadresse ein (im Format user@domain) des Raums Kontos, das mit der Konsole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-173">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="0e4b9-174">Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-174">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="0e4b9-175">Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-175">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="0e4b9-176">Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-176">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="0e4b9-177">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-177">Click **Next**.</span></span>
    
5. <span data-ttu-id="0e4b9-178">Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-178">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="0e4b9-179">Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-179">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="0e4b9-180">Die folgenden Geräte können ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-180">The devices to select are:</span></span>
    
   - <span data-ttu-id="0e4b9-181">Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum</span><span class="sxs-lookup"><span data-stu-id="0e4b9-181">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="0e4b9-182">Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen </span><span class="sxs-lookup"><span data-stu-id="0e4b9-182">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="0e4b9-183">Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="0e4b9-183">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="0e4b9-p115">Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-p115">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="0e4b9-186">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-186">Click **Finish**.</span></span>
    
<span data-ttu-id="0e4b9-187">Die Skype Raum Systemen v2 Konsole app Anmelden bei Skype für Business Server mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch die Synchronisierung der Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-187">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="0e4b9-188">Ausführliche Informationen zum Verwenden der Verwaltungskonsole app finden Sie in der [Hilfe Skype Raum Systeme, Version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-188">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0e4b9-189">Skype Raum Systemen v2 erfordert das Vorhandensein von zertifizierten Konsole Hardware.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-189">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="0e4b9-190">Sogar eine ordnungsgemäß erstellte Image, enthält die Skype Raum Systemen v2 Konsole app kann nicht nach der Erstinstallation Verfahren starten, es sei denn, die Konsole Hardware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-190">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="0e4b9-191">Für Surface Pro-basierte Lösungen muss die Surface Pro für die zugehörige Andocken Hardware, übergeben dieses Kontrollkästchen verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-191">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e4b9-192">Möglicherweise benötigen einige Benutzer nicht-englischen eine physische Tastatur während des Setups mit der Konsole verbunden, Symbole auf der Bildschirmtastatur nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-192">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="0e4b9-193">Installieren Sie das Zertifikat einen privates in der Konsole</span><span class="sxs-lookup"><span data-stu-id="0e4b9-193">Install a private CA certificate on the console</span></span>
<span data-ttu-id="0e4b9-194"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-194"></span></span>

<span data-ttu-id="0e4b9-195">Die Skype Raum Systemen v2-Konsole muss Zertifikate von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-195">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="0e4b9-196">Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-196">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="0e4b9-197">In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat der Skype Raum Systemen v2-Konsole in eine Reihe von Methoden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-197">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="0e4b9-198">Sie können die Konsole Active Directory teilnehmen und, die werden automatisch hinzugefügt, die erforderlichen Zertifikate erhält der Zertifizierungsstelle auf Active Directory (normale Bereitstellungsoption) veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-198">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="0e4b9-199">Sie können das Zertifikat nach der Imageerstellung manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-199">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="0e4b9-200">Bevor Sie dies tun, müssen Sie die [Initial Einrichten der Konsole](console.md#Initial)durchführen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-200">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="0e4b9-201">So installieren Sie das Zertifikat manuell </span><span class="sxs-lookup"><span data-stu-id="0e4b9-201">To manually install the certificate</span></span>

1. <span data-ttu-id="0e4b9-202">Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-202">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="0e4b9-203">Platzieren Sie die Konsole im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-203">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="0e4b9-204">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-204">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="0e4b9-205">Teilnehmen an einer Active Directory-Domäne (Optional)</span><span class="sxs-lookup"><span data-stu-id="0e4b9-205">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="0e4b9-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-206"></span></span>

<span data-ttu-id="0e4b9-207">Sie können Skype Raum Systemen v2 Konsolen an Ihre Domäne beitreten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-207">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="0e4b9-208">Skype Raum Systemen v2 Konsolen sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht mit Skype Raum Systemen v2 kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-208">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="0e4b9-209">Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die verhindern Skype Raum Systemen v2 automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-209">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="0e4b9-210">Informationen über die Verwaltung der Gruppenrichtlinienergebnisse finden Sie unter [Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-210">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="0e4b9-211">So verbinden Sie Skype Room Systems v2 durch einen Domänenbeitritt mit einer Domäne</span><span class="sxs-lookup"><span data-stu-id="0e4b9-211">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="0e4b9-212">Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-212">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="0e4b9-213">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-213">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="0e4b9-214">Geben Sie in PowerShell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-214">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="0e4b9-215">Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten Ihre Skype Raum Systemen v2 Konsolen "Skype Raum Systemen v2" werden beispielsweise Organisationseinheit, die ein untergeordnetes Element des einer OU "Ressourcen" ist der Befehl werden:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-215">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="0e4b9-216">Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-216">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="0e4b9-217">Prüfliste für die Bereitstellung von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-217">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="0e4b9-218"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-218"></span></span>

<span data-ttu-id="0e4b9-219">Verwenden Sie die folgende Checkliste, während eine endgültige Überprüfung, dass die Konsole und alle zugehörigen Peripheriegeräte konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="0e4b9-219">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="0e4b9-220">**Anwendungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="0e4b9-220">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0e4b9-221">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-221">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-222">Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-222">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="0e4b9-223">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-223">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-224">Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-224">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="0e4b9-225">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-225">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-226">Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-226">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="0e4b9-227">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-227">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-228">Alle Firmwareupdates wurden angewendet</span><span class="sxs-lookup"><span data-stu-id="0e4b9-228">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="0e4b9-229">**A/v-Peripheriegeräte**</span><span class="sxs-lookup"><span data-stu-id="0e4b9-229">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0e4b9-230">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-230">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-231">Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-231">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="0e4b9-232">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-232">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-233">Kamera funktionale und optimal positioniert</span><span class="sxs-lookup"><span data-stu-id="0e4b9-233">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="0e4b9-234">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-234">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-235">Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-235">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="0e4b9-236">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-236">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-237">Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-237">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="0e4b9-238">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-238">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-239">Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="0e4b9-239">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="0e4b9-240">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-240">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-241">Das Audioeingabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-241">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="0e4b9-242">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-242">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-243">Das Audioausgabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-243">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="0e4b9-244">**Dock**</span><span class="sxs-lookup"><span data-stu-id="0e4b9-244">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0e4b9-245">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-245">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-246">Die Kabel sind sicher angeschlossen und nicht eingeklemmt.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-246">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="0e4b9-247">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-247">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-248">Die Audioerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-248">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="0e4b9-249">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-249">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-250">Die Videoerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-250">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="0e4b9-251">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-251">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-252">Das Dock lässt sich frei drehen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-252">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="0e4b9-253">☐</span><span class="sxs-lookup"><span data-stu-id="0e4b9-253">☐</span></span>  <br/> |<span data-ttu-id="0e4b9-254">Die Helligkeit des Bildschirms ist für die Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-254">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e4b9-255">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e4b9-255">See also</span></span>
<span data-ttu-id="0e4b9-256"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4b9-256"></span></span>

[<span data-ttu-id="0e4b9-257">Planung für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-257">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="0e4b9-258">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-258">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="0e4b9-259">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-259">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="0e4b9-260">Verwalten von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0e4b9-260">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)