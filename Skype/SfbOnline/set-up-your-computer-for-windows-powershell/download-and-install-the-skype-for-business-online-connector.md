---
title: Herunterladen und Installieren des Skype for Business Online-Connectormoduls
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: deffed8da6b5b7a7c2ae522782f5316744de3394
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858331"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Herunterladen und Installieren des Skype for Business Online-Connectormoduls

Das Skype for Business Online-Connectormodul umfasst das **New-CsOnlineSession** -Cmdlet, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. In diesem Modul wird nur auf 64-Bit-Computern (siehe [Einrichten des Computers für Skype für das Business Online Management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md) für Weitere Informationen) unterstützt, können heruntergeladen werden, aus dem Microsoft Download Center unter [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Laden Sie die Datei „SkypeOnlinePowershell.exe" herunter, und gehen Sie dann wie folgt vor:
  
1. Doppelklicken Sie auf die Datei **SkypeOnlinePowershell.exe**.
    
2. Wählen Sie im Windows PowerShell-Setup-Assistenten für Skype for Business Online auf der Seite **Microsoft-Software-Lizenzbedingungen** die Option **Ich stimme den Lizenzbedingungen zu** aus, und klicken Sie dann auf **Installieren**. Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Ja**, um die Installation fortzusetzen.
    
3. Klicken Sie auf der Seite **Completed the Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online abgeschlossen) auf **Fertig stellen**.
    
Das Setupprogramm kopiert das Skype for Business Online-Connectormodul (und das **New-CsOnlineSession** -Cmdlet) auf den Computer. Um auf das Modul zuzugreifen, starten Sie eine Windows PowerShell-Sitzung mit Administratoranmeldeinformationen, und führen Sie dann den folgenden Befehl aus:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Wenn Sie diesen Befehl nicht bei jedem Start von Windows PowerShell eingeben möchten, können Sie ihn zu Ihrem Windows PowerShell-Profil hinzufügen. Geben Sie dazu den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:
  
```
notepad.exe $profile
```

 Wenn Editor angezeigt wird, fügen Sie die folgende Zeile am Ende der gegebenenfalls bereits im Profil vorhandenen Befehle hinzu:
  
```
Import-Module SkypeOnlineConnector
```

Speichern Sie die Datei. Wenn Sie Windows PowerShell das nächste Mal starten, wird das Skype for Business Online-Connectormodul automatisch importiert. Beachten Sie: Wenn Sie Windows PowerShell nicht mit Administratoranmeldeinformationen ausführen, wird eine Fehlermeldung angezeigt, und das Modul wird nicht geladen.
  
Neben dem Skype for Business Online-Connectormodul installiert „SkypeOnlinePowershell.exe" drei weitere Komponenten: 1) Identity Service Client Runtime Library (IDCRL) zum Verarbeiten der Clientauthentifizierung gegenüber Skype for Business Online, 2) .NET Framework 4.5 und 3) das Microsoft Visual C++ 2012 Redistributable (x64)-Paket (Version 11.0.50727). .NET Framework 4.5 stellt die Infrastruktur zum Erstellen und Ausführen von .NET-Anwendungen bereit, einschließlich Windows PowerShell. Das Visual C++ Redistributable-Paket installiert Visual C++-Laufzeitkomponenten für Computer, auf denen Microsoft Visual Studio 2012 nicht installiert ist.
  
Um die Versionsnummer des zurzeit auf dem Computer installierten Connectormoduls zu überprüfen, öffnen Sie die Systemsteuerung, öffnen Sie **Programme und Features**, und überprüfen Sie dann die Versionsnummer von **Skype for Business Online, Windows PowerShell Module** (Windows PowerShell-Modul für Skype for Business Online).
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 