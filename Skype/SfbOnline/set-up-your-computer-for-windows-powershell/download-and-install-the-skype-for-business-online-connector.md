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
f1keywords: None
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: 7e97bc31d85370919eec7c50fae01d00f5b1ddac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284710"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="3ffdd-103">Herunterladen und Installieren des Skype for Business Online-Connectormoduls</span><span class="sxs-lookup"><span data-stu-id="3ffdd-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="3ffdd-104">Das Skype for Business Online-Connectormodul umfasst das **New-CsOnlineSession** -Cmdlet, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3ffdd-105">Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird (Weitere Informationen finden Sie unter [Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), die im [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)Microsoft Download Center unter heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="3ffdd-106">Laden Sie die Datei „SkypeOnlinePowershell.exe" herunter, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3ffdd-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="3ffdd-107">Doppelklicken Sie auf die Datei **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="3ffdd-p102">Wählen Sie im Windows PowerShell-Setup-Assistenten für Skype for Business Online auf der Seite **Microsoft-Software-Lizenzbedingungen** die Option **Ich stimme den Lizenzbedingungen zu** aus, und klicken Sie dann auf **Installieren**. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**, um die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="3ffdd-110">Klicken Sie auf der Seite **Completed the Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online abgeschlossen) auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="3ffdd-p103">Das Setupprogramm kopiert das Skype for Business Online-Connectormodul (und das **New-CsOnlineSession** -Cmdlet) auf den Computer. Um auf das Modul zuzugreifen, starten Sie eine Windows PowerShell-Sitzung mit Administratoranmeldeinformationen, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="3ffdd-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="3ffdd-p104">Wenn Sie diesen Befehl nicht bei jedem Start von Windows PowerShell eingeben möchten, können Sie ihn zu Ihrem Windows PowerShell-Profil hinzufügen. Geben Sie dazu den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3ffdd-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="3ffdd-115">Wenn Editor angezeigt wird, fügen Sie die folgende Zeile am Ende der gegebenenfalls bereits im Profil vorhandenen Befehle hinzu:</span><span class="sxs-lookup"><span data-stu-id="3ffdd-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="3ffdd-p105">Speichern Sie die Datei. Wenn Sie Windows PowerShell das nächste Mal starten, wird das Skype for Business Online-Connectormodul automatisch importiert. Beachten Sie: Wenn Sie Windows PowerShell nicht mit Administratoranmeldeinformationen ausführen, wird eine Fehlermeldung angezeigt, und das Modul wird nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="3ffdd-p106">Neben dem Skype for Business Online-Connectormodul installiert „SkypeOnlinePowershell.exe" drei weitere Komponenten: 1) Identity Service Client Runtime Library (IDCRL) zum Verarbeiten der Clientauthentifizierung gegenüber Skype for Business Online, 2) .NET Framework 4.5 und 3) das Microsoft Visual C++ 2012 Redistributable (x64)-Paket (Version 11.0.50727). .NET Framework 4.5 stellt die Infrastruktur zum Erstellen und Ausführen von .NET-Anwendungen bereit, einschließlich Windows PowerShell. Das Visual C++ Redistributable-Paket installiert Visual C++-Laufzeitkomponenten für Computer, auf denen Microsoft Visual Studio 2012 nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="3ffdd-122">Um die Versionsnummer des zurzeit auf dem Computer installierten Connectormoduls zu überprüfen, öffnen Sie die Systemsteuerung, öffnen Sie **Programme und Features**, und überprüfen Sie dann die Versionsnummer von **Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online).</span><span class="sxs-lookup"><span data-stu-id="3ffdd-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3ffdd-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3ffdd-123">Related topics</span></span>
[<span data-ttu-id="3ffdd-124">Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ffdd-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
