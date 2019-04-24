---
title: Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: krishra
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema wird die Bereitstellungsverfahren für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop.
ms.openlocfilehash: 792e6ab2521be2eaf46bc3a43979173d878fcb63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219409"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="4b62a-103">Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4b62a-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="4b62a-104">In diesem Thema wird die Bereitstellungsverfahren für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop.</span><span class="sxs-lookup"><span data-stu-id="4b62a-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="4b62a-105">Planungsüberlegungen befinden sich in [Skype für Unternehmen in einer VDI-Umgebung planen](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4b62a-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="4b62a-106">Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind.</span><span class="sxs-lookup"><span data-stu-id="4b62a-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="4b62a-107">Die Benutzer arbeiten mit lokalen Windows-Computern und verwenden Clients auf einem virtuellen Desktop.</span><span class="sxs-lookup"><span data-stu-id="4b62a-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="4b62a-108">Verwendung von Skype für Unternehmen für eine Verbindung auf dem erfordert zusätzlichen VDI-Plug-in-Software.</span><span class="sxs-lookup"><span data-stu-id="4b62a-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="4b62a-109">Ihnen stehen zwei Methoden zur Verfügung, für die VDI-Plug-in-Komponente - eine Angeboten von Microsoft und eine von Citrix angeboten.</span><span class="sxs-lookup"><span data-stu-id="4b62a-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="4b62a-110">Microsoft empfiehlt die Verwendung der neuen HDX-Echtzeit Optimization Pack-Lösung in neuen Bereitstellungen ist jedoch weiterhin die ursprünglichen Lync VDI-Plug-In für den Rest des Lebenszyklus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4b62a-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="4b62a-111">Dieses Thema enthält Details zum Bereitstellen des Microsoft Lync VDI-Plug-in, die wird nur unter Windows 7 und Windows 8 oder Windows Server 2008 unterstützt, und nur Lync 2013 oder Skype für Business Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b62a-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="4b62a-112">Es ist nicht geplant, dieses Plug-in aktualisieren, aber die [Citrix HDX-Echtzeit Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype für Unternehmen wird aktualisiert werden, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4b62a-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="4b62a-113">Vorbereiten Ihrer Umgebung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="4b62a-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="4b62a-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4b62a-114"></span></span>

1. <span data-ttu-id="4b62a-115">Skype für Business Server sicher, dass für alle Lync-VDI-Plug-in-Benutzer EnableMediaRedirection auf TRUE festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4b62a-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="4b62a-116">Weitere Informationen hierzu finden Sie unter der Themen der Onlinehilfe für das Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) und [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4b62a-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="4b62a-117">Installieren Sie auf dem Data Center-Server der Skype für Business-Client auf allen virtuellen Desktops.</span><span class="sxs-lookup"><span data-stu-id="4b62a-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="4b62a-118">Installieren Sie auf den lokalen Computern das Lync VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="4b62a-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="4b62a-119">Die Benutzer sollten jetzt ein Gerät wie etwa ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.</span><span class="sxs-lookup"><span data-stu-id="4b62a-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="4b62a-120">Konfigurieren von Einstellungen der Remotedesktopverbindung</span><span class="sxs-lookup"><span data-stu-id="4b62a-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="4b62a-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4b62a-121"></span></span>

<span data-ttu-id="4b62a-122">Zur Vorbereitung von Remotedesktopverbindung für das Lync VDI-Plug-in auf dem lokalen Computer folgendermaßen Sie vor:</span><span class="sxs-lookup"><span data-stu-id="4b62a-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="4b62a-123">Wenn auf der lokale Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="4b62a-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="4b62a-124">Wenn auf der lokale Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des [Remote Desktop Services Client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="4b62a-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="4b62a-125">Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.</span><span class="sxs-lookup"><span data-stu-id="4b62a-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="4b62a-126">Klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="4b62a-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="4b62a-127">Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4b62a-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="4b62a-128">Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.</span><span class="sxs-lookup"><span data-stu-id="4b62a-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="4b62a-129">Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.</span><span class="sxs-lookup"><span data-stu-id="4b62a-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="4b62a-130">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b62a-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="4b62a-131">Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="4b62a-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="4b62a-132">Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen des virtuellen Desktops ein, und klicken Sie dann auf **Verbinden**. </span><span class="sxs-lookup"><span data-stu-id="4b62a-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="4b62a-133">Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="4b62a-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="4b62a-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="4b62a-134"></span></span>

<span data-ttu-id="4b62a-135">Nachdem das Lync VDI-Plug-in aktiviert ist, gilt für den Benutzer diese Schritte beim auf dem virtuellen Desktop Skype für Unternehmen anmelden.</span><span class="sxs-lookup"><span data-stu-id="4b62a-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="4b62a-136">Der Benutzer gibt seine Anmeldeinformationen für die Skype für Business-Client auf dem virtuellen Desktop.</span><span class="sxs-lookup"><span data-stu-id="4b62a-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="4b62a-137">Nachdem Skype für Unternehmen des Lync-VDI-Plug-in erkennt, Skype für Business der Benutzer aufgefordert, die Anmeldeinformationen erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="4b62a-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="4b62a-138">In diesem Dialogfeld sollten die Benutzer das Kontrollkästchen **Kennwort speichern** aktivieren, damit sie die Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="4b62a-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="4b62a-139">Skype für Unternehmen beginnt eine Kopplung mit der Lync-VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="4b62a-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="4b62a-140">Während dies geschieht, zeigt der Client zwei Symbole an, in der Skype für Business Statusleiste.</span><span class="sxs-lookup"><span data-stu-id="4b62a-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="4b62a-141">Das Symbol in der unteren linken Ecke gibt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol in der unteren rechten Ecke gibt an, dass VDI-Paarung auftreten ausgeführt wird: ein.</span><span class="sxs-lookup"><span data-stu-id="4b62a-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="4b62a-142">Nach dem VDI-Paarung auftreten erfolgreich ist, wird die Symbole ändern, um das Audiogerät anzugeben, die für Anrufe und des VDI-Paarung Erfolg verwendet werden: b.</span><span class="sxs-lookup"><span data-stu-id="4b62a-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="4b62a-143">Der Benutzer kann jetzt seine Anwesenheit auf Skype für kompatible Geräte Business sehen, die mit dem lokalen Computer verbunden sind und Anrufe tätigen und entgegennehmen wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="4b62a-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="4b62a-144">Problembehandlung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="4b62a-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="4b62a-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4b62a-145"></span></span>

<span data-ttu-id="4b62a-146">Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="4b62a-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="4b62a-147">Probleme beim Installieren des Lync VDI-Plug-Ins </span><span class="sxs-lookup"><span data-stu-id="4b62a-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="4b62a-148">Wenn Probleme bei der Installation des Lync-VDI-Plug-in vorhanden sind, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b62a-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="4b62a-149">Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4b62a-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="4b62a-150">Stellen Sie sicher, dass der Schreibschutz deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4b62a-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="4b62a-151">Finden Sie in der Dokumentation des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="4b62a-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="4b62a-152">Problembehandlung für die Kopplung</span><span class="sxs-lookup"><span data-stu-id="4b62a-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="4b62a-153">Wenn Lync-VDI-Plug-in eine Kopplung fehlschlägt, das paarungssymbol in der unteren rechten zeigt als rotes "X" als dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4b62a-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="4b62a-154">Nachfolgend finden Sie mögliche Gründe für Fehler und Maßnahmen, mit denen Sie das Problem korrigieren können. </span><span class="sxs-lookup"><span data-stu-id="4b62a-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="4b62a-155">**Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**</span><span class="sxs-lookup"><span data-stu-id="4b62a-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="4b62a-156">Der Benutzer sollte Abmelden bei Skype für Unternehmen und mit den richtigen Anmeldeinformationen erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="4b62a-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="4b62a-157">Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4b62a-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="4b62a-158">**Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="4b62a-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="4b62a-159">Wenn sie in Windows Remotedesktopverbindung verwenden, sollten die Benutzer Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b62a-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="4b62a-160">Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.</span><span class="sxs-lookup"><span data-stu-id="4b62a-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="4b62a-161">Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="4b62a-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="4b62a-162">Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. </span><span class="sxs-lookup"><span data-stu-id="4b62a-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="4b62a-163">Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. </span><span class="sxs-lookup"><span data-stu-id="4b62a-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="4b62a-164">**Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**</span><span class="sxs-lookup"><span data-stu-id="4b62a-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="4b62a-165">Vergewissern Sie sich nach der Installation des Plug-Ins auf dem lokalen Computer, dass die folgenden Dateien in „C:\Programme\Microsoft Office\Office15“ (ändern Sie gegebenenfalls den Laufwerkbuchstaben) vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="4b62a-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="4b62a-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="4b62a-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="4b62a-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="4b62a-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="4b62a-168">**Die Skype für Business-Client wird auf dem lokalen Computer ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="4b62a-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="4b62a-169">Für die Verwendung des Lync VDI-Plug-in, einen Skype für Business-Client nicht auf dem lokalen Computer ausgeführt werden muss fehl, andernfalls eine Kopplung.</span><span class="sxs-lookup"><span data-stu-id="4b62a-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="4b62a-170">Es empfiehlt sich sollte der Benutzer einen Skype für Business-Client nicht auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="4b62a-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4b62a-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b62a-171">See also</span></span>
<span data-ttu-id="4b62a-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4b62a-172"></span></span>

[<span data-ttu-id="4b62a-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="4b62a-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)