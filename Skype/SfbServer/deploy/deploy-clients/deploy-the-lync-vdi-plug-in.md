---
title: Bereitstellen des Lync VDI-Plug-Ins in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In diesem Thema wird die Bereitstellungsverfahren für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop.
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="08245-103">Bereitstellen des Lync VDI-Plug-Ins in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="08245-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="08245-104">In diesem Thema wird die Bereitstellungsverfahren für die Verwendung von Skype für Unternehmen beim Herstellen einer Verbindung mit einem virtuellen Remotedesktop.</span><span class="sxs-lookup"><span data-stu-id="08245-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="08245-105">Eine VDI-Umgebung (Virtual Desktop Infrastructure) wird in einigen Organisationen verwendet, in denen Sicherheits- und Complianceprobleme besonders sensibel sind.</span><span class="sxs-lookup"><span data-stu-id="08245-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="08245-106">Die Benutzer arbeiten mit lokalen Windows-Computern und verwenden Clients auf einem virtuellen Desktop.</span><span class="sxs-lookup"><span data-stu-id="08245-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="08245-107">Verwendung von Skype für Unternehmen für eine Verbindung auf dem erfordert zusätzlichen VDI-Plug-in-Software.</span><span class="sxs-lookup"><span data-stu-id="08245-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="08245-108">Ihnen stehen zwei Methoden zur Verfügung, für die VDI-Plug-in-Komponente - eine Angeboten von Microsoft und eine von Citrix angeboten.</span><span class="sxs-lookup"><span data-stu-id="08245-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="08245-109">Microsoft empfiehlt die Verwendung der neuen HDX-Echtzeit Optimization Pack-Lösung in neuen Bereitstellungen ist jedoch weiterhin die ursprünglichen Lync VDI-Plug-In für den Rest des Lebenszyklus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="08245-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="08245-110">Dieses Thema enthält Details zum Bereitstellen des Microsoft Lync VDI-Plug-in, wodurch wird nur unter Windows 7 und Windows 8 oder Windows Server 2008 unterstützt, und unterstützt nur Lync 2013 oder Skype für Business 2015 Clients.</span><span class="sxs-lookup"><span data-stu-id="08245-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="08245-111">Es ist nicht geplant, dieses Plug-in aktualisieren, aber die [Citrix HDX-Echtzeit Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) für Skype für Unternehmen wird aktualisiert werden, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="08245-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="08245-112">Vorbereiten Ihrer Umgebung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="08245-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="08245-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="08245-113"></span></span>

1. <span data-ttu-id="08245-114">Skype für Business Server 2015 sicher, dass für alle Lync-VDI-Plug-in-Benutzer EnableMediaRedirection auf TRUE festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="08245-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="08245-115">Weitere Informationen hierzu finden Sie unter der Themen der Onlinehilfe für das Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) und [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08245-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="08245-116">Installieren Sie auf dem Data Center-Server der Skype für Business 2015-Client auf allen virtuellen Desktops.</span><span class="sxs-lookup"><span data-stu-id="08245-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="08245-117">Installieren Sie auf den lokalen Computern das Lync VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="08245-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="08245-118">Die Benutzer sollten jetzt ein Gerät wie etwa ein Headset oder eine Webcam mit ihrem lokalen Computer verbinden.</span><span class="sxs-lookup"><span data-stu-id="08245-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="08245-119">Konfigurieren von Einstellungen der Remotedesktopverbindung</span><span class="sxs-lookup"><span data-stu-id="08245-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="08245-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="08245-120"></span></span>

<span data-ttu-id="08245-121">Zur Vorbereitung von Remotedesktopverbindung für das Lync VDI-Plug-in auf dem lokalen Computer folgendermaßen Sie vor:</span><span class="sxs-lookup"><span data-stu-id="08245-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="08245-122">Wenn auf der lokale Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="08245-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="08245-123">Wenn auf der lokale Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des [Remote Desktop Services Client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="08245-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="08245-124">Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.</span><span class="sxs-lookup"><span data-stu-id="08245-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="08245-125">Klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="08245-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="08245-126">Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="08245-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="08245-127">Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.</span><span class="sxs-lookup"><span data-stu-id="08245-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="08245-128">Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.</span><span class="sxs-lookup"><span data-stu-id="08245-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="08245-129">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="08245-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="08245-130">Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="08245-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="08245-131">Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen des virtuellen Desktops ein, und klicken Sie dann auf **Verbinden**. </span><span class="sxs-lookup"><span data-stu-id="08245-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="08245-132">Anmelden und Verwenden von Skype for Business auf dem virtuellen Desktop</span><span class="sxs-lookup"><span data-stu-id="08245-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="08245-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="08245-133"></span></span>

<span data-ttu-id="08245-134">Nachdem das Lync VDI-Plug-in aktiviert ist, gilt für den Benutzer folgende Schritte aus, wenn auf dem virtuellen Desktop Skype für Business 2015 anmelden.</span><span class="sxs-lookup"><span data-stu-id="08245-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="08245-135">Der Benutzer gibt seine Anmeldeinformationen für die Skype für Business 2015-Client auf dem virtuellen Desktop.</span><span class="sxs-lookup"><span data-stu-id="08245-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="08245-136">Nachdem das Lync VDI-Plug-in von Skype für Business 2015 erkannt hat, Skype für Business 2015 der Benutzer aufgefordert, die Anmeldeinformationen erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="08245-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="08245-137">In diesem Dialogfeld sollten die Benutzer das Kontrollkästchen **Kennwort speichern** aktivieren, damit sie die Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="08245-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="08245-138">Skype für Business 2015 beginnt eine Kopplung mit der Lync-VDI-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="08245-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="08245-139">Während dies geschieht, zeigt der Client zwei Symbole an, in der Skype für Business 2015 Statusleiste.</span><span class="sxs-lookup"><span data-stu-id="08245-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="08245-140">Das Symbol links unten zeigt an, dass keine Audiogeräte verfügbar sind, während das blinkende Symbol rechts unten signalisiert, dass die VDI-Kopplung gerade durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="08245-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="08245-141">Nach einer erfolgreichen VDI-Kopplung ändern sich die Symbole und zeigen nun das für Anrufe verwendete Audiogerät bzw. den Erfolg der VDI-Kopplung an:</span><span class="sxs-lookup"><span data-stu-id="08245-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="08245-142">Der Benutzer kann jetzt seine Anwesenheit auf Skype für kompatible Geräte Business 2015 sehen, die mit dem lokalen Computer verbunden sind und Anrufe tätigen und entgegennehmen wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="08245-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="08245-143">Problembehandlung für das Lync VDI-Plug-In</span><span class="sxs-lookup"><span data-stu-id="08245-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="08245-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="08245-144"></span></span>

<span data-ttu-id="08245-145">Lesen Sie die folgenden Abschnitte, wenn nach der Installation des Lync VDI-Plug-Ins Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="08245-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="08245-146">Probleme beim Installieren des Lync VDI-Plug-Ins </span><span class="sxs-lookup"><span data-stu-id="08245-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="08245-147">Wenn Probleme bei der Installation des Lync-VDI-Plug-in vorhanden sind, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="08245-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="08245-148">Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="08245-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="08245-149">Stellen Sie sicher, dass der Schreibschutz deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="08245-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="08245-150">Finden Sie in der Dokumentation des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="08245-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="08245-151">Problembehandlung für die Kopplung</span><span class="sxs-lookup"><span data-stu-id="08245-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="08245-152">Wenn Lync-VDI-Plug-in eine Kopplung fehlschlägt, das paarungssymbol in der unteren rechten zeigt als rotes "X" als dargestellt:</span><span class="sxs-lookup"><span data-stu-id="08245-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="08245-153">Nachfolgend finden Sie mögliche Gründe für Fehler und Maßnahmen, mit denen Sie das Problem korrigieren können. </span><span class="sxs-lookup"><span data-stu-id="08245-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="08245-154">**Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**</span><span class="sxs-lookup"><span data-stu-id="08245-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="08245-155">Der Benutzer sollte Abmelden bei Skype für Unternehmen und mit den richtigen Anmeldeinformationen erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="08245-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="08245-156">Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="08245-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="08245-157">**Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="08245-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="08245-158">Wenn sie in Windows Remotedesktopverbindung verwenden, sollten die Benutzer Folgendes:</span><span class="sxs-lookup"><span data-stu-id="08245-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="08245-159">Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.</span><span class="sxs-lookup"><span data-stu-id="08245-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="08245-160">Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="08245-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="08245-161">Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. </span><span class="sxs-lookup"><span data-stu-id="08245-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="08245-162">Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. </span><span class="sxs-lookup"><span data-stu-id="08245-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="08245-163">**Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**</span><span class="sxs-lookup"><span data-stu-id="08245-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="08245-164">Vergewissern Sie sich nach der Installation des Plug-Ins auf dem lokalen Computer, dass die folgenden Dateien in „C:\Programme\Microsoft Office\Office15“ (ändern Sie gegebenenfalls den Laufwerkbuchstaben) vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="08245-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="08245-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="08245-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="08245-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="08245-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="08245-167">**Die Skype für Business 2015-Client wird auf dem lokalen Computer ausgeführt.**</span><span class="sxs-lookup"><span data-stu-id="08245-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="08245-168">Zum Verwenden des Lync-VDI-Plug-in, einen Skype für Business 2015 Client muss nicht auf dem lokalen Computer ausgeführt werden, schlägt fehl andernfalls eine Kopplung.</span><span class="sxs-lookup"><span data-stu-id="08245-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="08245-169">Es empfiehlt sich sollte der Benutzer einen Skype für Business 2015 Client nicht auf dem lokalen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="08245-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="08245-170">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="08245-170">See also</span></span>
<span data-ttu-id="08245-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="08245-171"></span></span>

#### 

[<span data-ttu-id="08245-172">Planen von Skype für Unternehmen in einer VDI-Umgebung</span><span class="sxs-lookup"><span data-stu-id="08245-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

