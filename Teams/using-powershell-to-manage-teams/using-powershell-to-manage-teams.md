---
title: Verwenden von PowerShell zum Verwalten von Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Informationen Sie zum Windows PowerShell verwenden, um alle Features von Microsoft-Teams verwalten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678346"
---
# <a name="using-powershell-to-manage-teams"></a>Verwenden von PowerShell zum Verwalten von Teams

Features in Teams können mithilfe von PowerShell oder der Microsoft-Teams und Skype für Business Admin Center verwaltet werden. 

> ! [Hinweis] Nicht alle Features in Teams können mithilfe des Teams Connector-Moduls verwaltet werden. Sie müssen möglicherweise die Skype für Business Connector verwenden. Finden Sie unter [herunterladen und Installieren der Skype für Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

### <a name="step-1-prerequisites"></a>Schritt 1: erforderliche Komponenten

Remoteverwaltung von Microsoft-Teams, mithilfe von PowerShell wird nur auf 64-Bit-Computern mit einem der folgenden Betriebssysteme unterstützt:
  
- Windows 10
- Windows 8.1
- Windows 8 
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008
- Windows 7
    
Zusätzlich zur ein unterstütztes Betriebssystem muss der Computer auch Folgendes ausgeführt werden:
  
- PowerShell 3.0 oder höher
    
- Teams PowerShell Connector-Modul


### <a name="step-2-install-powershell-30-or-higher"></a>Schritt 2: Install PowerShell 3.0 oder höher
[Verwenden Sie dieses Thema für die Hilfe](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a>Schritt 3: Herunterladen Sie und installieren Sie des Teams Connector-Moduls
[Verwenden Sie dieses Thema für die Hilfe](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

Installieren Sie das aktuelle Modul über die PowerShell-Katalog mit: 
  
  Install-Modul MicrosoftTeams

Oder Weitere Informationen des Pakets finden Sie hier:https://www.powershellgallery.com/packages/MicrosoftTeams/

### <a name="step-4-connect-using-the-teams-connector-module"></a>Schritt 4: Verbinden Sie mithilfe des Teams Connector-Moduls
[Verwenden Sie dieses Thema für die Hilfe](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a>Verwandte Themen
- [Verwalten von Teams Funktionen mit PowerShell](manage-features-with-powershell.md)
