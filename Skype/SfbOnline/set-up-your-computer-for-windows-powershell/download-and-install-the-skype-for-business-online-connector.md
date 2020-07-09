---
title: Herunterladen und Installieren des Skype for Business Online-Connectormoduls
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Laden Sie den Skype for Business Online-Connector herunter, installieren Sie ihn, und verwenden Sie ihn, um eine Windows PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085701"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="e36fa-103">Herunterladen und Installieren des Skype for Business Online-Connectormoduls</span><span class="sxs-lookup"><span data-stu-id="e36fa-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="e36fa-104">Die neueste [Version von Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.</span><span class="sxs-lookup"><span data-stu-id="e36fa-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="e36fa-105">Das Skype for Business Online-Connectormodul umfasst das **New-CsOnlineSession** -Cmdlet, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="e36fa-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="e36fa-106">Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird (Weitere Informationen finden Sie unter [Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), die im Microsoft Download Center unter heruntergeladen werden kann [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="e36fa-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="e36fa-107">Laden Sie die Datei „SkypeOnlinePowershell.exe" herunter, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e36fa-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="e36fa-108">Doppelklicken Sie auf die Datei **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="e36fa-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="e36fa-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span><span class="sxs-lookup"><span data-stu-id="e36fa-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="e36fa-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span><span class="sxs-lookup"><span data-stu-id="e36fa-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="e36fa-111">Klicken Sie auf der Seite **Completed the Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online abgeschlossen) auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e36fa-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="e36fa-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span><span class="sxs-lookup"><span data-stu-id="e36fa-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="e36fa-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span><span class="sxs-lookup"><span data-stu-id="e36fa-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="e36fa-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span><span class="sxs-lookup"><span data-stu-id="e36fa-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="e36fa-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="e36fa-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="e36fa-116">Wenn Editor angezeigt wird, fügen Sie die folgende Zeile am Ende der gegebenenfalls bereits im Profil vorhandenen Befehle hinzu:</span><span class="sxs-lookup"><span data-stu-id="e36fa-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="e36fa-117">Save the file.</span><span class="sxs-lookup"><span data-stu-id="e36fa-117">Save the file.</span></span> <span data-ttu-id="e36fa-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span><span class="sxs-lookup"><span data-stu-id="e36fa-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="e36fa-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span><span class="sxs-lookup"><span data-stu-id="e36fa-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="e36fa-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="e36fa-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="e36fa-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e36fa-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="e36fa-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span><span class="sxs-lookup"><span data-stu-id="e36fa-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="e36fa-123">Um die Versionsnummer des zurzeit auf dem Computer installierten Connectormoduls zu überprüfen, öffnen Sie die Systemsteuerung, öffnen Sie **Programme und Features**, und überprüfen Sie dann die Versionsnummer von **Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online).</span><span class="sxs-lookup"><span data-stu-id="e36fa-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e36fa-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e36fa-124">Related topics</span></span>
[<span data-ttu-id="e36fa-125">Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e36fa-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
