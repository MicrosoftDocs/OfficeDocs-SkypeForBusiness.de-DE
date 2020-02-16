---
title: Herunterladen und Installieren von Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Sie können Windows PowerShell 5.1 herunterladen, installieren und dann verwenden, um eine Remote-PowerShell-Sitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029096"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="762db-103">Herunterladen und Installieren von Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="762db-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="762db-104">Wenn Sie das Windows 10 Anniversary Update oder Windows Server 2016 verwenden, sollten Sie bereits über Windows PowerShell 5.1 verfügen.</span><span class="sxs-lookup"><span data-stu-id="762db-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="762db-105">Das liegt daran, dass diese Anwendung mit diesen Betriebssystemen vorinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="762db-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="762db-106">Um zu ermitteln, welche Version von Microsoft PowerShell Sie verwenden, gehen Sie auf Ihrem Computer unter Windows 7 oder Windows Server 2008 R2 oder Windows Server 2012 wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="762db-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="762db-107">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="762db-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="762db-108">Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="762db-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="762db-109">Nun werden im Konsolenfenster Informationen wie die folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="762db-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="762db-110">Wenn die Versionsnummer 5.1 zurückgegeben wird, führen Sie Windows PowerShell 5.1 aus.</span><span class="sxs-lookup"><span data-stu-id="762db-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="762db-111">Wenn anstelle von 5.1 eine andere Versionsnummer zurückgegeben wird, müssen Sie Windows PowerShell 5.1 installieren.</span><span class="sxs-lookup"><span data-stu-id="762db-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="762db-112">Sie können Windows Management Framework 5.1 (einschließlich Windows PowerShell 5.1) aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="762db-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="762db-113">Wenn Sie sich vergewissert haben, dass Windows PowerShell 5.1 installiert ist, müssen Sie sicherstellen, dass PowerShell für die Ausführung von Remoteskripts konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="762db-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="762db-114">Starten Sie dazu PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="762db-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="762db-115">Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="762db-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="762db-116">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="762db-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="762db-117">Klicken Sie dann im Dialogfeld **Benutzerkontensteuerung** auf **Ja**, um zu bestätigen, dass Sie PowerShell mit den Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="762db-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="762db-118">Wenn Sie Windows 8 verwenden, gehen Sie stattdessen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="762db-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="762db-p104">Greifen Sie auf die Charmsleiste zu, klicken Sie auf **Suchen**, und klicken Sie dann mit der rechten Maustaste auf **Windows PowerShell**. Auf Windows 8-Computern (mit oder ohne Touchscreen) können Sie schnell auf die Charmsleiste zugreifen, indem Sie die WINDOWS-TASTE gedrückt halten und C drücken.</span><span class="sxs-lookup"><span data-stu-id="762db-p104">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="762db-121">Klicken Sie auf der Symbolleiste unten auf dem Bildschirm auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="762db-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="762db-122">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="762db-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="762db-p105">Wenn PowerShell ausgeführt wird, müssen Sie die Ausführungsrichtlinie ändern, um die Ausführung von Remoteskripts zuzulassen. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="762db-p105">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="762db-125">Wenn Sie den vorstehenden Befehl ausführen, wird möglicherweise die folgende Fehlermeldung angezeigt:> *Set-ExecutionPolicy : Der Zugriff auf den Registrierungsschlüssel „HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShel“ wird verweigert.*</span><span class="sxs-lookup"><span data-stu-id="762db-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="762db-126">Diese Fehlermeldung wird normalerweise ausgegeben, wenn Sie PowerShell nicht mit Administratorrechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="762db-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="762db-127">Schließen Sie die PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="762db-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="762db-128">Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="762db-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="762db-129">Wenn der folgende Wert zurückgegeben wird, wurde alles ordnungsgemäß konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="762db-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="762db-130">Wenn Sie zurzeit nicht Windows PowerShell 5.1 ausführen, müssen Sie auch Windows Management Framework 5.1 aus dem Microsoft Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="762db-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="762db-131">Dabei handelt es sich um ein Installationspaket, in dem Windows PowerShell 5.1 und Windows-Remoteverwaltung (WinRM) 3.0 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="762db-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="762db-132">Das Installationspaket ist möglicherweise erforderlich, wenn Sie beispielsweise Windows 7 SP1 ausführen und noch nicht auf Windows PowerShell 5.1 aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="762db-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="762db-133">Wenn Sie Windows Server 2016 oder das Windows 10 Anniversary Update ausführen, sollte es nicht erforderlich sein, Windows PowerShell 5.1 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="762db-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="762db-134">Unter diesen Betriebssystemen ist Windows PowerShell 5.1 vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="762db-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="762db-135">Vor der Installation von Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="762db-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="762db-136">Vergewissern Sie sich, dass Sie die korrekte Version des Installationspakets heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="762db-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="762db-137">Wenn Sie die 64-Bit-Version von Windows 7 SP1 verwenden, laden Sie die Datei "Win7AndW2K8R2-KB3191566-x64.ZIP" herunter.</span><span class="sxs-lookup"><span data-stu-id="762db-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="762db-138">Für die 32-Bit-Version von Windows 7 laden Sie die Datei "Win7-KB3191566-x86.ZIP" herunter.</span><span class="sxs-lookup"><span data-stu-id="762db-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="762db-139">Wenn auf Ihrem Computer Windows 7 ausgeführt wird, vergewissern Sie sich, dass Sie Windows 7 Service Pack 1 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="762db-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="762db-p109">Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="762db-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="762db-142">Um Windows Management Framework 5.1 zu installieren, führen Sie die Schritte unter [Installieren und Konfigurieren von WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure) aus.</span><span class="sxs-lookup"><span data-stu-id="762db-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="762db-p110">Überprüfen Sie nach dem Neustart des Computers, ob Windows PowerShell gestartet wird und ob die Anwendung mit Anmeldeinformationen ausgeführt werden kann. Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="762db-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="762db-145">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="762db-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="762db-146">Wenn das Dialogfeld „Benutzerkontensteuerung" angezeigt wird, klicken Sie auf **Ja**, um zu bestätigen, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="762db-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="762db-p111">Wenn die PowerShell-Konsole angezeigt wird, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird und richtig konfiguriert ist. Um zu überprüfen, ob der Dienst ausgeführt wird, geben Sie den folgenden Befehl an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="762db-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="762db-149">Auf dem Bildschirm werden nun Informationen zum Dienst WinRM angezeigt:</span><span class="sxs-lookup"><span data-stu-id="762db-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="762db-150">Wenn der Dienststatus nicht „Running" (Wird ausgeführt) entspricht, starten Sie den WinRM-Dienst, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="762db-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="762db-151">Nachdem der Dienst gestartet wurde, führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass WinRM mit der Standardauthentifizierung arbeitet:</span><span class="sxs-lookup"><span data-stu-id="762db-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="762db-152">Auf dem Bildschirm werden nun Informationen wie die folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="762db-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="762db-153">Wenn die Standardauthentifizierung auf „true" festgelegt ist, können Sie PowerShell verwenden, um eine Verbindung mit Skype for Business Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="762db-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="762db-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="762db-154">Related topics</span></span>
[<span data-ttu-id="762db-155">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="762db-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
