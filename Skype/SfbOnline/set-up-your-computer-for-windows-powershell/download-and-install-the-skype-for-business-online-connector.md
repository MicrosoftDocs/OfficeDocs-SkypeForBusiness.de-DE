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
description: Laden Sie skype for Business Online Connector herunter, installieren Sie ihn, und verwenden Sie ihn dann, um eine Remotesitzung Windows PowerShell zu erstellen, die eine Verbindung mit Skype for Business Online herstellt.
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097201"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Herunterladen und Installieren des Teams PowerShell-Moduls

> [!NOTE]

> Die neueste öffentliche Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) ist in Skype for Business Online Connector integriert und stellt ein einzelnes Modul für die Verwaltung von Teams und Skype for Business Online PowerShell zur Verfügung.


1. Installieren Sie [das Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Herstellen einer Verbindung mit allen [Microsoft 365- oder Office 365-Diensten in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) einem einzigen Windows PowerShell-Fenster oder Einrichten Ihres Computers [für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für skype for business online management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)