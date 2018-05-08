---
title: Konfigurieren einer Konsole für Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie das Skype Room Systems v2-Konsolengerät und die entsprechenden Peripheriegeräte einrichten.
ms.openlocfilehash: b9b786de35af63202b168b0664440d28302492e5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c58f8-103">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c58f8-104">In diesem Artikel wird beschrieben, wie Sie das Skype Room Systems v2-Konsolengerät und die entsprechenden Peripheriegeräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="c58f8-105">Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c58f8-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c58f8-106">Sie benötigen die Hardware und Software in [Skype Raum Systemen v2 Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c58f8-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c58f8-107">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="c58f8-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c58f8-108">Vorbereiten des Installationsimages</span><span class="sxs-lookup"><span data-stu-id="c58f8-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="c58f8-109">Installieren Sie das Zertifikat einen privates auf dem Tablettgerät</span><span class="sxs-lookup"><span data-stu-id="c58f8-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c58f8-110">Installieren Sie Windows 10 und die app Skype Raum Systeme v2-Konsole</span><span class="sxs-lookup"><span data-stu-id="c58f8-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c58f8-111">Anfängliche Einrichten der Konsole</span><span class="sxs-lookup"><span data-stu-id="c58f8-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="c58f8-112">Prüfliste für die Bereitstellung von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c58f8-113">Skype-Chatroom-Systemen v2 funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)ordnungsgemäß eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="c58f8-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="c58f8-114">Vorbereiten des Installationsimages</span><span class="sxs-lookup"><span data-stu-id="c58f8-114">Prepare the installation image</span></span>
<span data-ttu-id="c58f8-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-115"></span></span>

<span data-ttu-id="c58f8-116">Installieren der Skype Raum Systemen v2-app in einem Surface Pro 4 oder Surface Pro erfordert ein USB-Speichergerät mit mindestens 32GB Arbeitsspeicher als FAT32 Datenträger formatiert.</span><span class="sxs-lookup"><span data-stu-id="c58f8-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="c58f8-117">Es sollte keine anderen Dateien auf dem Gerät, alle vorhandenen Dateien auf den USB-Speicher gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="c58f8-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c58f8-118">Wenn das Konsolenimage nicht gemäß diesen Anweisungen erstellt wurde, kann dies zu unerwünschtem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="c58f8-119">Update für Windows 10 Enterprise Jahrestag (Version 1607) ist für die Erstellung von Skype Raum Systemen v2 Bild nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c58f8-120">Eine vorhandene v2 Skype Raum Systeme mit Windows 10 Enterprise Jahrestag Update verschieben in Skype Raum Systemen v2 Update 3 über die Windows Store ausgeführt werden, jedoch sollte eine neue Installation durchgeführt werden, wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c58f8-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="c58f8-121">Laden Sie die [MSU für KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span><span class="sxs-lookup"><span data-stu-id="c58f8-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="c58f8-122">Laden Sie das [Skript CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="c58f8-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="c58f8-123">Platzieren Sie die MSU für KB4056892 im gleichen Verzeichnis befindet wie das Skript CreateSrsMedia.ps1.</span><span class="sxs-lookup"><span data-stu-id="c58f8-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="c58f8-124">Führen Sie das Skript CreateSrsMedia.ps1 aus einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows-10-Computer.</span><span class="sxs-lookup"><span data-stu-id="c58f8-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="c58f8-125">Führen Sie das Skript-Anweisungen, um eine Skype Raum Systemen v2 USB-Installationsdiskette erstellen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="c58f8-126">Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Skype Raum Systemen v2 Konsole app ](console.md#Reimage)fort.</span><span class="sxs-lookup"><span data-stu-id="c58f8-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c58f8-127">Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2 </span><span class="sxs-lookup"><span data-stu-id="c58f8-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c58f8-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-128"></span></span>

<span data-ttu-id="c58f8-129">Jetzt müssen Sie das erstellte Image anwenden.</span><span class="sxs-lookup"><span data-stu-id="c58f8-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="c58f8-130">Das Tablet wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Skype Raum Systemen v2 app ausgeführt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c58f8-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="c58f8-131">Das Tablet muss mit einer Stromquelle verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="c58f8-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="c58f8-132">Beginnen Sie mit dem Gerät im vollständig ausgeschalteten Zustand.</span><span class="sxs-lookup"><span data-stu-id="c58f8-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="c58f8-133">Drücken Sie gegebenenfalls den Netzschalter, und halten Sie ihn gedrückt, bis das Tablet ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="c58f8-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="c58f8-134">Schließen Sie den USB-Installationsdatenträger an das Tablet an.</span><span class="sxs-lookup"><span data-stu-id="c58f8-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="c58f8-135">Drücken Sie die Leiser-Taste (-) am Tablet, und halten Sie sie gedrückt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="c58f8-136">Drücken Sie den Netzschalter am Tablet, und lassen Sie ihn wieder los.</span><span class="sxs-lookup"><span data-stu-id="c58f8-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="c58f8-137">Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.</span><span class="sxs-lookup"><span data-stu-id="c58f8-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="c58f8-138">Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c58f8-138">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c58f8-139">Nachdem das System heruntergefahren hat, ist es sicher, entfernen Sie die Installationsdiskette USB.</span><span class="sxs-lookup"><span data-stu-id="c58f8-139">After the system has shut down, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="c58f8-140">Jetzt können Sie das Tablet im Dock platzieren und die für Ihren Besprechungsraum benötigten Peripheriegeräte anschließen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-140">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="c58f8-141">Weitere Informationen finden Sie in den Anweisungen des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="c58f8-141">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="c58f8-142">Auswählen einer Sprache in Creators Update</span><span class="sxs-lookup"><span data-stu-id="c58f8-142">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="c58f8-143">In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B., sie möchten die app in Französisch angezeigt, aber es ist stattfindende nur auf Englisch verfügbar).</span><span class="sxs-lookup"><span data-stu-id="c58f8-143">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c58f8-144">Die folgenden Anweisungen gelten nur für Geräte, die mit Windows Creators Update erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c58f8-144">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="c58f8-145">Für Legacysysteme bzw. auf dem Markt vorhandene Systeme, für die nicht ordnungsgemäß dem neuen Bereitstellungssystem entsprechende neue Images angewendet wurden, können diese Anweisungen nicht verwendet werden. Diese Systeme sollten aber auch nicht von dem anfänglichen Problem betroffen sein, das diesen manuellen Eingriff erforderlich macht (in Anniversary Edition können Sie die App-Sprache beim Setup explizit auswählen).</span><span class="sxs-lookup"><span data-stu-id="c58f8-145">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c58f8-146">So wenden Sie die gewünschte Sprache an</span><span class="sxs-lookup"><span data-stu-id="c58f8-146">To apply your desired language</span></span>

1. <span data-ttu-id="c58f8-147">Wechseln Sie in den Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="c58f8-147">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c58f8-148">Wählen Sie das Startmenü aus.</span><span class="sxs-lookup"><span data-stu-id="c58f8-148">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c58f8-149">Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-149">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c58f8-150">Wählen Sie **Zeit &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="c58f8-150">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c58f8-151">Wählen Sie **Region &amp; Sprache**.</span><span class="sxs-lookup"><span data-stu-id="c58f8-151">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c58f8-152">Wählen Sie **Sprache hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c58f8-152">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c58f8-153">Wählen Sie die Sprache aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-153">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c58f8-154">Wählen Sie die Sprache, die Sie soeben hinzugefügt, um der Liste "Sprachen haben".</span><span class="sxs-lookup"><span data-stu-id="c58f8-154">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c58f8-155">Wählen Sie **Als Standard** aus.</span><span class="sxs-lookup"><span data-stu-id="c58f8-155">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c58f8-156">Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="c58f8-156">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c58f8-157">a.</span><span class="sxs-lookup"><span data-stu-id="c58f8-157">a.</span></span> <span data-ttu-id="c58f8-158">Wählen Sie die Sprache aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-158">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c58f8-159">b.</span><span class="sxs-lookup"><span data-stu-id="c58f8-159">b.</span></span> <span data-ttu-id="c58f8-160">Wählen Sie **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="c58f8-160">Select **Remove**.</span></span>
    
11. <span data-ttu-id="c58f8-161">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-161">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c58f8-162">Führen Sie den folgenden Befehl aus: </span><span class="sxs-lookup"><span data-stu-id="c58f8-162">Run the following command:</span></span> 
    
    <span data-ttu-id="c58f8-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="c58f8-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="c58f8-164">Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="c58f8-164">Restart the system.</span></span>
    
<span data-ttu-id="c58f8-165">Die gewünschte Sprache ist jetzt auf das Skype Raum Systemen v2 Gerät angewendet.</span><span class="sxs-lookup"><span data-stu-id="c58f8-165">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c58f8-166">Anfangssetup der Konsole </span><span class="sxs-lookup"><span data-stu-id="c58f8-166">Initial set up of the Console</span></span>
<span data-ttu-id="c58f8-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-167"></span></span>

<span data-ttu-id="c58f8-168">Nach der Installation von Windows gehen die Skype Raum Systemen v2-app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="c58f8-168">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c58f8-p111">Daraufhin wird der Bildschirm „Benutzerkonto“ angezeigt. Geben Sie die Skype-Anmeldeadresse des Raumkontos ein, das für das Gerät verwendet werden soll. Verwenden Sie das Format „benutzer@domäne“.</span><span class="sxs-lookup"><span data-stu-id="c58f8-p111">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="c58f8-171">Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.</span><span class="sxs-lookup"><span data-stu-id="c58f8-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c58f8-172">Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest.</span><span class="sxs-lookup"><span data-stu-id="c58f8-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c58f8-173">Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="c58f8-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c58f8-174">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c58f8-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="c58f8-175">Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c58f8-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c58f8-176">Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c58f8-177">Die folgenden Geräte können ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="c58f8-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="c58f8-178">Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum</span><span class="sxs-lookup"><span data-stu-id="c58f8-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c58f8-179">Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen </span><span class="sxs-lookup"><span data-stu-id="c58f8-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c58f8-180">Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="c58f8-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="c58f8-p114">Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-p114">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c58f8-183">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c58f8-183">Click **Finish**.</span></span>
    
<span data-ttu-id="c58f8-184">Die app Anmelden bei Skype für Business Server 2015 mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch den Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden wird synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="c58f8-184">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c58f8-185">Ausführliche Informationen zum Verwenden der app finden Sie in der [Hilfe Skype Raum Systeme, Version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c58f8-185">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c58f8-186">Skype Raum Systemen v2 erfordert das Vorhandensein von zertifizierten Konsole Hardware (das Logitech SmartDock).</span><span class="sxs-lookup"><span data-stu-id="c58f8-186">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="c58f8-187">Sogar eine ordnungsgemäß erstellte Image, enthält die Skype Raum Systemen v2 app auf einem Surface Pro 4 oder Surface Pro geladen kann nicht nach der Erstinstallation Verfahren starten, es sei denn, die Konsole Hardware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c58f8-187">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c58f8-188">Einige nicht englischsprachige Benutzer müssen beim Anfangssetup eine physische Tastatur an die Konsole anschließen, wenn auf der Bildschirmtastatur keine Symbole unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c58f8-188">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="c58f8-189">Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf dem Tablet</span><span class="sxs-lookup"><span data-stu-id="c58f8-189">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="c58f8-190"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-190"></span></span>

<span data-ttu-id="c58f8-191">Das Skype Raum Systemen v2-Gerät muss Zertifikate von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c58f8-191">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c58f8-192">Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut.</span><span class="sxs-lookup"><span data-stu-id="c58f8-192">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c58f8-193">In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat zum Skype Raum Systemen v2 Gerät in eine Reihe von Methoden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c58f8-193">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="c58f8-194">Sie können das Gerät mit Active Directory verbinden. Dadurch werden automatisch die erforderlichen Zertifikate hinzugefügt, wenn die Zertifizierungsstelle in Active Directory veröffentlicht ist (normale Bereitstellungsoption).</span><span class="sxs-lookup"><span data-stu-id="c58f8-194">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c58f8-p118">Sie können das Zertifikat nach der Imageerstellung manuell installieren. Zuvor müssen Sie das [Anfangssetup der Konsole](console.md#Initial) abschließen. </span><span class="sxs-lookup"><span data-stu-id="c58f8-p118">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c58f8-197">So installieren Sie das Zertifikat manuell </span><span class="sxs-lookup"><span data-stu-id="c58f8-197">To manually install the certificate</span></span>

1. <span data-ttu-id="c58f8-198">Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.</span><span class="sxs-lookup"><span data-stu-id="c58f8-198">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c58f8-199">Platzieren Sie die Fläche 4 im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c58f8-199">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c58f8-200">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c58f8-200">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c58f8-201">Beitritt zu einer Active Directory-Domäne (optional)</span><span class="sxs-lookup"><span data-stu-id="c58f8-201">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="c58f8-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-202"></span></span>

<span data-ttu-id="c58f8-203">Sie können an Ihre Domäne Skype Raum Systemen v2 Geräte teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-203">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="c58f8-204">Skype Raum Systemen v2 Geräte sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht mit Skype Raum Systemen v2 kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="c58f8-204">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c58f8-205">Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die verhindern Skype Raum Systemen v2 automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="c58f8-205">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c58f8-206">Informationen über die Verwaltung der Gruppenrichtlinienergebnisse finden Sie unter [Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c58f8-206">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c58f8-207">So verbinden Sie Skype Room Systems v2 durch einen Domänenbeitritt mit einer Domäne</span><span class="sxs-lookup"><span data-stu-id="c58f8-207">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c58f8-208">Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c58f8-208">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c58f8-209">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="c58f8-209">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c58f8-210">Geben Sie in PowerShell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="c58f8-210">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="c58f8-211">Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten Ihre Skype Raum Systemen v2-Geräte in "Skype Raum Systemen v2" werden beispielsweise Organisationseinheit, die ein untergeordnetes Element des einer OU "Ressourcen" ist der Befehl werden:</span><span class="sxs-lookup"><span data-stu-id="c58f8-211">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c58f8-212">Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.</span><span class="sxs-lookup"><span data-stu-id="c58f8-212">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c58f8-213">Bereitstellungsprüfliste für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-213">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="c58f8-214"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-214"></span></span>

<span data-ttu-id="c58f8-215">Vergewissern Sie sich abschließend anhand der folgenden Prüfliste, dass das Konsolengerät und alle Peripheriegeräte vollständig konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="c58f8-215">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c58f8-216">**Anwendungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="c58f8-216">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c58f8-217">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-217">☐</span></span>  <br/> |<span data-ttu-id="c58f8-218">Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-218">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c58f8-219">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-219">☐</span></span>  <br/> |<span data-ttu-id="c58f8-220">Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="c58f8-220">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c58f8-221">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-221">☐</span></span>  <br/> |<span data-ttu-id="c58f8-222">Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-222">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c58f8-223">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-223">☐</span></span>  <br/> |<span data-ttu-id="c58f8-224">Alle Surface Pro 4- oder Surface Pro-Systemupdates wurden angewendet.</span><span class="sxs-lookup"><span data-stu-id="c58f8-224">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c58f8-225">**A/v-Peripheriegeräte**</span><span class="sxs-lookup"><span data-stu-id="c58f8-225">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c58f8-226">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-226">☐</span></span>  <br/> |<span data-ttu-id="c58f8-227">Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="c58f8-227">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c58f8-228">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-228">☐</span></span>  <br/> |<span data-ttu-id="c58f8-229">Kamera funktionale und optimal positioniert</span><span class="sxs-lookup"><span data-stu-id="c58f8-229">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c58f8-230">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-230">☐</span></span>  <br/> |<span data-ttu-id="c58f8-231">Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-231">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c58f8-232">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-232">☐</span></span>  <br/> |<span data-ttu-id="c58f8-233">Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-233">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c58f8-234">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-234">☐</span></span>  <br/> |<span data-ttu-id="c58f8-235">Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).</span><span class="sxs-lookup"><span data-stu-id="c58f8-235">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c58f8-236">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-236">☐</span></span>  <br/> |<span data-ttu-id="c58f8-237">Das Audioeingabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="c58f8-237">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c58f8-238">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-238">☐</span></span>  <br/> |<span data-ttu-id="c58f8-239">Das Audioausgabegerät ist funktionsfähig und optimal positioniert.</span><span class="sxs-lookup"><span data-stu-id="c58f8-239">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c58f8-240">**Andocken**</span><span class="sxs-lookup"><span data-stu-id="c58f8-240">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c58f8-241">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-241">☐</span></span>  <br/> |<span data-ttu-id="c58f8-242">Die Kabel sind sicher angeschlossen und nicht eingeklemmt.</span><span class="sxs-lookup"><span data-stu-id="c58f8-242">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c58f8-243">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-243">☐</span></span>  <br/> |<span data-ttu-id="c58f8-244">Die Audioerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="c58f8-244">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c58f8-245">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-245">☐</span></span>  <br/> |<span data-ttu-id="c58f8-246">Die Videoerfassung über HDMI ist funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="c58f8-246">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c58f8-247">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-247">☐</span></span>  <br/> |<span data-ttu-id="c58f8-248">Das Dock lässt sich frei drehen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-248">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c58f8-249">☐</span><span class="sxs-lookup"><span data-stu-id="c58f8-249">☐</span></span>  <br/> |<span data-ttu-id="c58f8-250">Die Helligkeit des Bildschirms ist für die Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="c58f8-250">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c58f8-251">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c58f8-251">See also</span></span>
<span data-ttu-id="c58f8-252"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c58f8-252"></span></span>

#### 

[<span data-ttu-id="c58f8-253">Planen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-253">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c58f8-254">Bereitstellen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-254">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c58f8-255">Konfigurieren einer Skype Raum Systemen v2-Konsole</span><span class="sxs-lookup"><span data-stu-id="c58f8-255">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c58f8-256">Verwalten von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="c58f8-256">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

