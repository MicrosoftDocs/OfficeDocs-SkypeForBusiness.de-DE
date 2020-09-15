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
description: Laden Sie den Skype for Business Online-Connector herunter, installieren Sie ihn, und verwenden Sie ihn, um eine Windows PowerShell-Remotesitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814564"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Herunterladen und Installieren des Skype for Business Online-Connectormoduls

> [!NOTE]
> Die neueste [PowerShell-Version von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und bietet ein einzelnes Modul für die PowerShell-Verwaltung von Teams.

Das Skype for Business Online-Connectormodul umfasst das **New-CsOnlineSession** -Cmdlet, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird (Weitere Informationen finden Sie unter [Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), die im Microsoft Download Center unter heruntergeladen werden kann [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Laden Sie die Datei „SkypeOnlinePowershell.exe" herunter, und gehen Sie dann wie folgt vor:
  
1. Doppelklicken Sie auf die Datei **SkypeOnlinePowershell.exe**.
    
2. Wählen Sie im Windows PowerShell-Setup-Assistenten für Skype for Business Online auf der Seite **Microsoft-Software-Lizenzbedingungen** die Option **Ich stimme den Lizenzbedingungen zu** aus, und klicken Sie dann auf **Installieren**. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**, um die Installation fortzusetzen.
    
3. Klicken Sie auf der Seite **Completed the Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online abgeschlossen) auf **Fertig stellen**.
    
Das Setupprogramm kopiert das Skype for Business Online-Connectormodul (und das **New-CsOnlineSession** -Cmdlet) auf den Computer. Um auf das Modul zuzugreifen, starten Sie eine Windows PowerShell-Sitzung mit Administratoranmeldeinformationen, und führen Sie dann den folgenden Befehl aus:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Wenn Sie diesen Befehl nicht bei jedem Start von Windows PowerShell eingeben möchten, können Sie ihn zu Ihrem Windows PowerShell-Profil hinzufügen. Geben Sie dazu den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```PowerShell
notepad.exe $profile
```

 Wenn Editor angezeigt wird, fügen Sie die folgende Zeile am Ende der gegebenenfalls bereits im Profil vorhandenen Befehle hinzu:
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Speichern Sie die Datei. Wenn Sie Windows PowerShell das nächste Mal starten, wird das Skype for Business Online-Connectormodul automatisch importiert. Beachten Sie: Wenn Sie Windows PowerShell nicht mit Administratoranmeldeinformationen ausführen, wird eine Fehlermeldung angezeigt, und das Modul wird nicht geladen.
  
Neben dem Skype for Business Online-Connectormodul installiert „SkypeOnlinePowershell.exe" drei weitere Komponenten: 1) Identity Service Client Runtime Library (IDCRL) zum Verarbeiten der Clientauthentifizierung gegenüber Skype for Business Online, 2) .NET Framework 4.5 und 3) das Microsoft Visual C++ 2012 Redistributable (x64)-Paket (Version 11.0.50727). .NET Framework 4.5 stellt die Infrastruktur zum Erstellen und Ausführen von .NET-Anwendungen bereit, einschließlich Windows PowerShell. Das Visual C++ Redistributable-Paket installiert Visual C++-Laufzeitkomponenten für Computer, auf denen Microsoft Visual Studio 2012 nicht installiert ist.
  
Um die Versionsnummer des zurzeit auf dem Computer installierten Connectormoduls zu überprüfen, öffnen Sie die Systemsteuerung, öffnen Sie **Programme und Features**, und überprüfen Sie dann die Versionsnummer von **Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online).
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
