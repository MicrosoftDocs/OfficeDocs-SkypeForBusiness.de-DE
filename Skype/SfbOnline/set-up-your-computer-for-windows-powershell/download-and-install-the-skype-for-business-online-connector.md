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
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Herunterladen und Installieren des Skype for Business Online-Connectormoduls

> [!NOTE]
> Die neueste [Version von Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.

Das Skype for Business Online-Connectormodul umfasst das **New-CsOnlineSession** -Cmdlet, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird (Weitere Informationen finden Sie unter [Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), die im Microsoft Download Center unter heruntergeladen werden kann [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Laden Sie die Datei „SkypeOnlinePowershell.exe" herunter, und gehen Sie dann wie folgt vor:
  
1. Doppelklicken Sie auf die Datei **SkypeOnlinePowershell.exe**.
    
2. In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.
    
3. Klicken Sie auf der Seite **Completed the Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online abgeschlossen) auf **Fertig stellen**.
    
The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:
  
```PowerShell
notepad.exe $profile
```

 Wenn Editor angezeigt wird, fügen Sie die folgende Zeile am Ende der gegebenenfalls bereits im Profil vorhandenen Befehle hinzu:
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.
  
In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.
  
Um die Versionsnummer des zurzeit auf dem Computer installierten Connectormoduls zu überprüfen, öffnen Sie die Systemsteuerung, öffnen Sie **Programme und Features**, und überprüfen Sie dann die Versionsnummer von **Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online).
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
