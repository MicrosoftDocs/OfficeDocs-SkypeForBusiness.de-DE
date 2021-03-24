---
title: Das Vorab-Laden von Inhalten für Besprechungen mit Outlook ein- oder ausschalten
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
- Setup
description: 'Erfahren Sie, wie Sie vorab geladene Inhalte für Skype for Business-Besprechungen mithilfe von Dateien oder Anlagen in einer Outlook-Besprechungseinladung aktivieren oder deaktivieren. '
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103801"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Das Vorab-Laden von Inhalten für Besprechungen mit Outlook ein- oder ausschalten

Benutzer können Inhalte, Dateien oder Anlagen, die an eine Outlook-Besprechungseinladung angefügt sind, vorab in eine Skype for Business Online-Besprechung laden, aber Sie können sie aktivieren oder deaktivieren. Sie ist standardmäßig für alle Organisationen aktiviert, die Skype for Business Online verwenden. Erfahren Sie, wie [Sie Anlagen für eine Skype for Business-Besprechung vorab laden.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)
  
> [!NOTE]
> Derzeit sind in Skype for Business Online keine Cmdlets zum Festlegen oder Anzeigen von Onlinewerten für _MaxContentStorageMB_ und _MaxUploadFileMB verfügbar._ Sie sind nur für Bereitstellungen vor Ort verfügbar. Es ist wichtig zu wissen, dass Inhalte nicht in eine Besprechung hochgeladen werden, wenn der angefügte Inhalt den  _MaxUploadFileSizeMB-Wert_ überschreitet oder wenn das _MaxContentStorageMB-Limit_ erreicht ist.
  
## <a name="to-get-you-started"></a>Erste Schritte

## <a name="start-windows-powershell"></a>Starten Windows PowerShell

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
1. Installieren Sie [das Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Herstellen einer Verbindung mit allen [Microsoft 365- oder Office 365-Diensten in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) einem einzigen Windows PowerShell-Fenster oder Einrichten Ihres Computers [für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="turning-it-on-or-off"></a>Aktivieren oder Deaktivieren dieser Funktion

Die Möglichkeit zum Vorabladen von Inhalten, die an eine Outlook-Besprechungseinladung angefügt sind, in Skype for Business Online-Besprechungen ist standardmäßig aktiviert. Möglicherweise müssen Sie jedoch verhindern, dass Benutzer in Ihrer Organisation Inhalte in ihren Besprechungen vorab laden.
  
> [!IMPORTANT]
> Diese Einstellung kann nur für Ihre gesamte Organisation aktiviert oder deaktiviert werden. Sie können sie nicht für einen einzelnen Benutzer aktivieren oder deaktivieren. 
  
 **Um die Funktion zu deaktivieren, öffnen Sie Windows PowerShell und führen Sie die folgenden Schritte aus:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Wenn Sie sie wieder aktivieren möchten, öffnen Sie Windows PowerShell und gehen Sie wie folgt vor:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sechs Gründe, warum Sie microsoft Windows PowerShell Office 365 oder Office 365 verwalten möchten](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
