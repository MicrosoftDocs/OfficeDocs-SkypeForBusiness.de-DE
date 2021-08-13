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
description: Laden Sie den Skype for Business Online Connector herunter, installieren Sie ihn, und verwenden Sie ihn dann, um eine Remote-Windows PowerShell-Sitzung zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: fd0a114bcd434e624937b323fbfa787d252db96ffafb701c3f13ff3a677b7118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339283"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Herunterladen und Installieren des Teams PowerShell-Moduls

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> Die neueste [Teams PowerShell Public Release](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und stellt ein einzelnes Modul für Teams und Skype for Business Online-PowerShell-Verwaltung zur Verfügung.


1. Installieren Sie [Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Verbinden für alle [Microsoft 365-](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) oder Office 365-Dienste in einem einzigen Windows PowerShell-Fenster oder Einrichten des Computers [für Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Onlineverwaltung in Skype for Business mithilfe Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
