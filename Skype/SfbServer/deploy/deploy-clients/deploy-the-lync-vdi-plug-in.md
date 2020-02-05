---
title: Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert.
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768948"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="d571a-103">Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d571a-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="d571a-104">In diesem Thema werden Bereitstellungsverfahren für die Verwendung von Skype for Business beim Herstellen einer Verbindung mit einem virtuellen Remote Desktop erläutert.</span><span class="sxs-lookup"><span data-stu-id="d571a-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="d571a-105">Planungsüberlegungen sind [für Skype for Business in VDI-Umgebungen vorgesehen](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="d571a-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="d571a-106">Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind.</span><span class="sxs-lookup"><span data-stu-id="d571a-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="d571a-107">Die Benutzer arbeiten mit lokalen Windows-Computern und verwenden Clients auf einem virtuellen Desktop.</span><span class="sxs-lookup"><span data-stu-id="d571a-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="d571a-108">Die Verwendung von Skype for Business für eine solche Verbindung erfordert eine zusätzliche VDI-Plug-in-Software.</span><span class="sxs-lookup"><span data-stu-id="d571a-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="d571a-109">Für die VDI-Plug-in-Komponente stehen zwei Lösungen zur Verfügung – eine von Microsoft und eine von Citrix angebotene.</span><span class="sxs-lookup"><span data-stu-id="d571a-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="d571a-110">Microsoft empfiehlt die Verwendung der neuen HDX-Realtime Optimization Pack-Lösung in neuen Bereitstellungen, unterstützt aber weiterhin das ursprüngliche lync-VDI-Plug-in für den Rest des Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="d571a-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="d571a-111">Dieses Thema enthält Details zur Bereitstellung des Microsoft lync VDI-Plug-ins, das nur unter Windows 7 und Windows 8 oder Windows Server 2008 unterstützt wird, und unterstützt nur lync 2013-oder Skype for Business-Clients.</span><span class="sxs-lookup"><span data-stu-id="d571a-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="d571a-112">Es gibt keine Pläne, dieses Plugin zu aktualisieren, aber das [Citrix HDX Realtime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype for Business wird bei Bedarf aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d571a-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="d571a-113">Vorbereiten Ihrer Umgebung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="d571a-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="d571a-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="d571a-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="d571a-115">Stellen Sie in Skype for Business Server sicher, dass EnableMediaRedirection für alle Benutzer von lync VDI-Plug-Ins auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d571a-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="d571a-116">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) und dem Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="d571a-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="d571a-117">Installieren Sie auf dem Rechenzentrumsserver den Skype for Business-Client auf allen virtuellen Desktops.</span><span class="sxs-lookup"><span data-stu-id="d571a-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="d571a-118">Installieren Sie auf den lokalen Computern das lync VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="d571a-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="d571a-119">Die Benutzer sollten jetzt ein Gerät wie etwa ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.</span><span class="sxs-lookup"><span data-stu-id="d571a-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="d571a-120">Konfigurieren von Einstellungen der Remotedesktopverbindung</span><span class="sxs-lookup"><span data-stu-id="d571a-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="d571a-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="d571a-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="d571a-122">Führen Sie die folgenden Schritte auf dem lokalen Computer aus, um die Remote Desktop Verbindung für das lync VDI-Plug-in vorzubereiten:</span><span class="sxs-lookup"><span data-stu-id="d571a-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="d571a-123">Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="d571a-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="d571a-124">Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des [Remote Desktop Dienste-Clients](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="d571a-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="d571a-125">Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.</span><span class="sxs-lookup"><span data-stu-id="d571a-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="d571a-126">Klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="d571a-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="d571a-127">Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="d571a-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="d571a-128">Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.</span><span class="sxs-lookup"><span data-stu-id="d571a-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="d571a-129">Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.</span><span class="sxs-lookup"><span data-stu-id="d571a-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="d571a-130">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d571a-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="d571a-131">Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="d571a-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="d571a-132">Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen des virtuellen Desktops ein, und klicken Sie dann auf **Verbinden**. </span><span class="sxs-lookup"><span data-stu-id="d571a-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="d571a-133">Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="d571a-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="d571a-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="d571a-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="d571a-135">Nachdem das lync-VDI-Plug-in aktiviert wurde, führt der Benutzer die folgenden Schritte aus, wenn er sich bei Skype for Business auf dem virtuellen Desktop anmeldet.</span><span class="sxs-lookup"><span data-stu-id="d571a-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="d571a-136">Der Benutzer gibt seine Anmeldeinformationen in den Skype for Business-Client ein, der auf dem virtuellen Desktop ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d571a-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="d571a-137">Nachdem Skype for Business das lync VDI-Plug-in erkannt hat, fordert Skype for Business den Benutzer auf, die Anmeldeinformationen erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="d571a-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="d571a-138">In diesem Dialogfeld sollten die Benutzer das Kontrollkästchen **Kennwort speichern** aktivieren, damit sie die Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="d571a-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="d571a-139">Skype for Business beginnt mit der Kopplung mit dem lync VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="d571a-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="d571a-140">In diesem Fall zeigt der Client zwei Symbole in der Statusleiste von Skype for Business an.</span><span class="sxs-lookup"><span data-stu-id="d571a-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="d571a-141">Das Symbol in der unteren linken Ecke zeigt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol in der unteren rechten Ecke zeigt an, dass die VDI-Kopplung in Bearbeitung ist: a.</span><span class="sxs-lookup"><span data-stu-id="d571a-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="d571a-142">Nachdem die VDI-Kopplung erfolgreich war, ändern sich die Symbole, um das Audiogerät anzugeben, das für Anrufe verwendet wird, und den Erfolg der VDI-Kopplung: b.</span><span class="sxs-lookup"><span data-stu-id="d571a-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="d571a-143">Der Benutzer kann nun seine Anwesenheit auf Skype for Business-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind, und Anrufe wie gewohnt tätigen und annehmen.</span><span class="sxs-lookup"><span data-stu-id="d571a-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="d571a-144">Problembehandlung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="d571a-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="d571a-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="d571a-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="d571a-146">Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="d571a-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="d571a-147">Probleme beim Installieren des Lync VDI-Plug-Ins </span><span class="sxs-lookup"><span data-stu-id="d571a-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="d571a-148">Wenn Probleme mit der Installation des lync VDI-Plug-ins auftreten, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d571a-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="d571a-149">Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d571a-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="d571a-150">Stellen Sie sicher, dass der Schreibschutz deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d571a-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="d571a-151">Anweisungen hierzu finden Sie in der Dokumentation Ihres Geräteherstellers.</span><span class="sxs-lookup"><span data-stu-id="d571a-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="d571a-152">Problembehandlung für die Kopplung</span><span class="sxs-lookup"><span data-stu-id="d571a-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="d571a-153">Wenn die Kopplung von lync VDI-Plug-ins fehlschlägt, wird das Kopplungs Symbol in der unteren rechten Ecke als rotes "X" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d571a-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="d571a-154">Nachfolgend finden Sie mögliche Gründe für Fehler und Maßnahmen, mit denen Sie das Problem korrigieren können. </span><span class="sxs-lookup"><span data-stu-id="d571a-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="d571a-155">**Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**</span><span class="sxs-lookup"><span data-stu-id="d571a-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="d571a-156">Der Benutzer sollte sich bei Skype for Business abmelden und sich mit den korrekten Anmeldeinformationen erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="d571a-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="d571a-157">Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d571a-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="d571a-158">**Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="d571a-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="d571a-159">Wenn Sie in Windows die Remote Desktop Verbindung verwenden, sollten die Benutzer die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d571a-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="d571a-160">Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.</span><span class="sxs-lookup"><span data-stu-id="d571a-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="d571a-161">Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="d571a-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="d571a-162">Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. </span><span class="sxs-lookup"><span data-stu-id="d571a-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="d571a-163">Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. </span><span class="sxs-lookup"><span data-stu-id="d571a-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="d571a-164">**Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**</span><span class="sxs-lookup"><span data-stu-id="d571a-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="d571a-165">Vergewissern Sie sich nach der Installation des Plug-Ins auf dem lokalen Computer, dass die folgenden Dateien in „C:\Programme\Microsoft Office\Office15“ (ändern Sie gegebenenfalls den Laufwerkbuchstaben) vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="d571a-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="d571a-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="d571a-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="d571a-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="d571a-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="d571a-168">**Der Skype for Business-Client wird auf dem lokalen Computer ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="d571a-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="d571a-169">Wenn Sie das lync VDI-Plug-in verwenden möchten, muss ein Skype for Business-Client nicht auf dem lokalen Computer ausgeführt werden, da andernfalls die Kopplung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="d571a-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="d571a-170">Als bewährte Methode sollte der Benutzer keinen Skype for Business-Client auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="d571a-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d571a-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d571a-171">See also</span></span>
<span data-ttu-id="d571a-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="d571a-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="d571a-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="d571a-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
