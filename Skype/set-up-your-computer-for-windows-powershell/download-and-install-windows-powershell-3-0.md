---
title: Herunterladen und Installieren von Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 5b28607248e2e2778ef4c8832379da0b4d111719
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="1cd3a-103">Herunterladen und Installieren von Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="1cd3a-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="1cd3a-p101">Wenn Sie Windows 8.1, Windows 8, Windows Server 2012 R2 oder Windows Server 2012 verwenden, sollten Sie bereits über Windows PowerShell 3.0 verfügen. Das liegt daran, dass die Anwendung unter diesen Betriebssystemen vorinstalliert ist.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p101">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0. That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="1cd3a-p102">Wenn Sie Windows 7 oder Windows Server 2008 R2 ausführen, führen Sie möglicherweise auch Windows PowerShell 3.0 aus. Es kann jedoch auch sein, dass Sie stattdessen Version 2.0 ausführen - die Version, die ursprünglich mit diesen Betriebssystemen ausgeliefert wurde. Um zu ermitteln, welche Version von Microsoft PowerShell Sie verwenden, gehen Sie auf Ihrem Computer unter Windows 7 oder Windows Server 2008 R2 wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p102">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0. However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems. To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="1cd3a-109">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1cd3a-110">Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="1cd3a-111">Im Konsolenfenster sollten dann etwa die folgenden Informationen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="1cd3a-p103">Wenn die Versionsnummer 3.0 zurückgegeben wird, führen Sie Windows PowerShell 3.0 aus. Wenn anstelle von 3.0 eine andere Versionsnummer zurückgegeben wird, müssen Sie Windows PowerShell 3.0 installieren. Sie können Windows Management Framework 3.0 (einschließlich Windows PowerShell 3.0) aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p103">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0. If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0. You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="1cd3a-p104">Wenn Sie sich vergewissert haben, dass Windows PowerShell 3.0 installiert ist, müssen Sie sicherstellen, dass PowerShell für die Ausführung von Remoteskripts konfiguriert ist. Starten Sie dazu PowerShell als Administrator. Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p104">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts. To do that, start PowerShell as an administrator. On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="1cd3a-118">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1cd3a-119">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1cd3a-120">Unter Windows 8 gehen Sie stattdessen so vor:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="1cd3a-p105">Greifen Sie auf die Charmsleiste zu, klicken Sie auf **Suchen**, und klicken Sie dann mit der rechten Maustaste auf **Windows PowerShell**. Auf Windows 8-Computern (mit oder ohne Touchscreen) können Sie schnell auf die Charmsleiste zugreifen, indem Sie die WINDOWS-TASTE gedrückt halten und C drücken.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p105">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="1cd3a-123">Klicken Sie auf der Symbolleiste unten auf dem Bildschirm auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="1cd3a-124">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1cd3a-p106">Wenn PowerShell ausgeführt wird, müssen Sie die Ausführungsrichtlinie ändern, um die Ausführung von Remoteskripts zuzulassen. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p106">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="1cd3a-127">Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="1cd3a-128">Wenn der folgende Wert zurückgegeben wird, ist alles richtig konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="1cd3a-p107">Wenn Sie zurzeit nicht Windows PowerShell 3.0 ausführen, müssen Sie auch Windows Management Framework 3.0 aus dem Microsoft Download Center herunterladen. Dabei handelt es sich um ein Installationspaket, in dem Windows PowerShell 3.0 und Windows-Remoteverwaltung (WinRM) 3.0 enthalten sind. Das Installationspaket ist möglicherweise erforderlich, wenn Sie Windows 7 ausführen und noch nicht auf Windows PowerShell 3.0 aktualisiert haben. Wenn Sie Windows Server 2012, Windows Server 2012 R2, Windows 8 oder Windows 8.1 ausführen, sollte die Installation von Windows PowerShell 3.0 nicht notwendig sein. Unter diesen Betriebssystemen ist Windows PowerShell 3.0 vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p107">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center. This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0. This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0. If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0. Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="1cd3a-134">Vor der Installation von Windows Management Framework 3.0:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="1cd3a-p108">Vergewissern Sie sich, dass Sie die richtige Version des Installationspakets heruntergeladen haben. Wenn Sie die 64-Bit-Version von Windows 7 ausführen, laden Sie die Datei „Windows6.1-KB2506143-x64.msu" herunter. Wenn Sie die 32-Bit-Version von Windows 7 ausführen, laden Sie die Datei „Windows6.1-KB2506143-x86.msu" herunter.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p108">Make sure you have downloaded the correct version of the installation package. If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu. If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="1cd3a-138">Wenn Sie auf Ihrem Computer Windows 7 ausführen, vergewissern Sie sich, dass Windows 7 Service Pack 1 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="1cd3a-p109">Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="1cd3a-141">Um Windows Management Framework 3.0 zu installieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="1cd3a-142">Doppelklicken Sie auf die MSU-Installationsdatei ( **Windows6.1-KB2506143-x64.msu** oder **Windows6.1-KB2506143-x86.msu**).</span><span class="sxs-lookup"><span data-stu-id="1cd3a-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="1cd3a-143">Klicken Sie im Assistenten zum Herunterladen und Installieren von Updates auf der Seite **Lesen Sie die Lizenzbedingungen (1 von 1)** auf **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="1cd3a-144">Nach Abschluss der Installation klicken Sie auf **Jetzt neu starten**, um den Computer neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="1cd3a-p110">Überprüfen Sie nach dem Neustart des Computers, ob Windows PowerShell gestartet wird und ob die Anwendung mit Anmeldeinformationen ausgeführt werden kann. Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="1cd3a-147">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1cd3a-148">Wenn das Dialogfeld „Benutzerkontensteuerung" angezeigt wird, klicken Sie auf **Ja**, um zu bestätigen, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1cd3a-p111">Wenn die PowerShell-Konsole angezeigt wird, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird und richtig konfiguriert ist. Um zu überprüfen, ob der Dienst ausgeführt wird, geben Sie den folgenden Befehl an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="1cd3a-151">Auf dem Bildschirm werden dann Informationen zum WinRM-Dienst angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="1cd3a-152">Wenn der Dienststatus nicht „Running" (Wird ausgeführt) entspricht, starten Sie den WinRM-Dienst, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="1cd3a-153">Nachdem der Dienst gestartet wurde, führen Sie den folgenden Befehl aus, um sicherzustellen, dass WinRM Standardauthentifizierung verwendet:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="1cd3a-154">Auf dem Bildschirm werden etwa die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1cd3a-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="1cd3a-155">Wenn die Standardauthentifizierung festgelegt wurde auf "true", und klicken Sie dann Sie PowerShell verwenden, um eine Verbindung mit Skype für Business Online bereit sind.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1cd3a-156">See Also</span><span class="sxs-lookup"><span data-stu-id="1cd3a-156">Related topics</span></span>
[<span data-ttu-id="1cd3a-157">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1cd3a-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 
