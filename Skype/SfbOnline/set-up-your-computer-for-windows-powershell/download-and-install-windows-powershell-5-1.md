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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Herunterladen Sie, installieren Sie, und klicken Sie dann verwenden Sie Windows PowerShell 5.1, um eine remote-PowerShell-Sitzung zu erstellen, die mit Skype für Business Online verbindet.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926699"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="a351f-103">Herunterladen und Installieren von Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a351f-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="a351f-104">Wenn Sie Windows 10 Jahrestag Update oder Windows Server 2016 verwenden, sollten Sie bereits Windows PowerShell 5.1 verfügen.</span><span class="sxs-lookup"><span data-stu-id="a351f-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="a351f-105">Das liegt daran, dass die Anwendung unter diesen Betriebssystemen vorinstalliert ist.</span><span class="sxs-lookup"><span data-stu-id="a351f-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="a351f-106">Um zu bestimmen, welche Version von Microsoft PowerShelll Sie verwenden, gehen Sie auf Ihrem Windows 7 oder Windows Server 2008 R2 oder Windows Server 2012-Computer:</span><span class="sxs-lookup"><span data-stu-id="a351f-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="a351f-107">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör**, auf **Windows PowerShell** und dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a351f-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a351f-108">Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a351f-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="a351f-109">Im Konsolenfenster sollten dann etwa die folgenden Informationen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a351f-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="a351f-110">Wenn die zurückgegebene Versionsnummer 5.1 ist, werden Sie Windows PowerShell 5.1 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a351f-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="a351f-111">Wenn die zurückgegebene Versionsnummer nicht 5.1 ist, müssen Sie Windows PowerShell 5.1 installieren.</span><span class="sxs-lookup"><span data-stu-id="a351f-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="a351f-112">Sie können Windows Management Framework 5.1, einschließlich Windows PowerShell 5.1, aus dem [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a351f-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="a351f-113">Nachdem Sie sichergestellt haben, dass Windows PowerShell 5.1 installiert ist, müssen Sie sicherstellen, dass für das Ausführen von Skripts remote PowerShell konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a351f-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="a351f-114">Starten Sie dazu PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="a351f-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="a351f-115">Unter Windows 7, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a351f-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="a351f-116">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a351f-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a351f-117">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a351f-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a351f-118">Unter Windows 8 gehen Sie stattdessen so vor:</span><span class="sxs-lookup"><span data-stu-id="a351f-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="a351f-p104">Greifen Sie auf die Charmsleiste zu, klicken Sie auf **Suchen**, und klicken Sie dann mit der rechten Maustaste auf **Windows PowerShell**. Auf Windows 8-Computern (mit oder ohne Touchscreen) können Sie schnell auf die Charmsleiste zugreifen, indem Sie die WINDOWS-TASTE gedrückt halten und C drücken.</span><span class="sxs-lookup"><span data-stu-id="a351f-p104">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="a351f-121">Klicken Sie auf der Symbolleiste unten auf dem Bildschirm auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a351f-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="a351f-122">Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**. Damit bestätigen Sie, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a351f-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a351f-p105">Wenn PowerShell ausgeführt wird, müssen Sie die Ausführungsrichtlinie ändern, um die Ausführung von Remoteskripts zuzulassen. Geben Sie in der PowerShell-Konsole den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a351f-p105">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="a351f-125">Wenn Sie mit dem vorstehenden Befehl ausführen, erhalten Sie möglicherweise die folgenden Fehler angezeigt: > *Set-ExecutionPolicy: Zugriff auf den Registrierungsschlüssel "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' wird verweigert.*</span><span class="sxs-lookup"><span data-stu-id="a351f-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="a351f-126">Diese Fehlermeldung tritt typischerweise auf, wenn Sie PowerShell nicht unter Administratoranmeldeinformationen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a351f-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="a351f-127">Schließen der PowerShell-Sitzung, und starten Sie eine neue Sitzung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="a351f-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="a351f-128">Um zu überprüfen, ob die Ausführungsrichtlinie richtig konfiguriert ist, geben Sie Folgendes an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a351f-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="a351f-129">Wenn der folgende Wert zurückgegeben wird, ist alles richtig konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="a351f-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="a351f-130">Wenn Sie Windows PowerShell 5.1 derzeit nicht ausgeführt werden, müssen Sie auch zum Herunterladen und Installieren von Windows Management Framework 5.1 aus dem Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="a351f-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="a351f-131">Dies ist ein Installationspaket, die Windows PowerShell 5.1 und Windows-Remoteverwaltung (WinRM) 3.0 enthält.</span><span class="sxs-lookup"><span data-stu-id="a351f-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="a351f-132">Dieses Installationspaket kann erforderlich sein, wenn Sie beispielsweise Windows 7 SP1 ausgeführt werden und noch nicht auf Windows PowerShell 5.1 aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="a351f-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="a351f-133">Wenn Sie Windows Server 2016 oder Windows 10 Jahrestag Update ausführen, sollten keine müssen Windows PowerShell 5.1 installieren werden.</span><span class="sxs-lookup"><span data-stu-id="a351f-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="a351f-134">Windows PowerShell 5.1 ist auf diesen Betriebssystemen vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a351f-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="a351f-135">Vor der Installation von Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="a351f-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="a351f-136">Vergewissern Sie sich, dass Sie die richtige Version des Installationspakets heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a351f-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="a351f-137">Wenn Sie die 64-Bit-Version von Windows 7 SP1 ausgeführt werden, laden Sie die Datei Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="a351f-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="a351f-138">Wenn Sie die 32-Bit-Version von Windows 7 ausgeführt werden, laden Sie die Datei Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="a351f-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="a351f-139">Wenn Sie auf Ihrem Computer Windows 7 ausführen, vergewissern Sie sich, dass Windows 7 Service Pack 1 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a351f-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="a351f-p109">Wenn Sie nicht sicher sind, welche Version von Windows ausgeführt wird oder ob Windows 7 Service Pack 1 installiert ist, klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**. Diese Informationen werden im Dialogfeld „System" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a351f-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="a351f-142">Führen Sie zum Installieren von Windows Management Framework 5.1 das Verfahren in [Installieren und Konfigurieren von WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span><span class="sxs-lookup"><span data-stu-id="a351f-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span></span>
  
<span data-ttu-id="a351f-p110">Überprüfen Sie nach dem Neustart des Computers, ob Windows PowerShell gestartet wird und ob die Anwendung mit Anmeldeinformationen ausgeführt werden kann. Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="a351f-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="a351f-145">Klicken Sie auf **Start**, auf **Alle Programme**, auf **Zubehör** und auf **Windows PowerShell**. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a351f-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a351f-146">Wenn das Dialogfeld „Benutzerkontensteuerung" angezeigt wird, klicken Sie auf **Ja**, um zu bestätigen, dass Sie PowerShell mit Administratoranmeldeinformationen ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a351f-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a351f-p111">Wenn die PowerShell-Konsole angezeigt wird, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird und richtig konfiguriert ist. Um zu überprüfen, ob der Dienst ausgeführt wird, geben Sie den folgenden Befehl an der PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a351f-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="a351f-149">Auf dem Bildschirm werden dann Informationen zum WinRM-Dienst angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a351f-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="a351f-150">Wenn der Dienststatus nicht „Running" (Wird ausgeführt) entspricht, starten Sie den WinRM-Dienst, indem Sie den folgenden Befehl eingeben und dann die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="a351f-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="a351f-151">Nachdem der Dienst gestartet wurde, führen Sie den folgenden Befehl aus, um sicherzustellen, dass WinRM Standardauthentifizierung verwendet:</span><span class="sxs-lookup"><span data-stu-id="a351f-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="a351f-152">Auf dem Bildschirm werden etwa die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a351f-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="a351f-153">Wenn die Standardauthentifizierung festgelegt wurde auf "true", und klicken Sie dann Sie PowerShell verwenden, um eine Verbindung mit Skype für Business Online bereit sind.</span><span class="sxs-lookup"><span data-stu-id="a351f-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="a351f-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a351f-154">Related topics</span></span>
[<span data-ttu-id="a351f-155">Einrichten Ihres Computers für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a351f-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
