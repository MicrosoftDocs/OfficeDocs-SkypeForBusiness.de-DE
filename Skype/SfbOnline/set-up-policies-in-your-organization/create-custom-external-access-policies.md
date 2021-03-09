---
title: Erstellen von benutzerdefinierten externen Zugriffsrichtlinien
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Mit Skype for Business Online können Sie zusätzliche Richtlinien für den externen Zugriff erstellen. Im Gegensatz zu Client- oder Konferenzrichtlinien, bei denen sie mehrere Kombinationen haben können, gibt es drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken können.
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569131"
---
# <a name="create-custom-external-access-policies"></a>Erstellen von benutzerdefinierten externen Zugriffsrichtlinien

Mit Skype for Business Online können Sie zusätzliche Richtlinien für den externen Zugriff erstellen. Im Gegensatz zu Client- oder Konferenzrichtlinien, bei denen sie mehrere Kombinationen haben können, gibt es drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken können. Dies sind:
  
- Kein Verbund- oder Skype-Consumerzugriff (_Tag:NoFederationAndPIC_ )
    
- Nur Verbundzugriff (_Tag:FederationOnly_ )
    
- Verbund- und Consumerzugriff (_FederationAndPICDefault_)
    
Benutzerdefinierte externe Richtlinien ermöglichen es Ihnen, zusätzliche Richtlinien zu erstellen, die nicht von den oben genannten Einstellungen abgedeckt werden. Beim Erstellen der Richtlinie müssen Sie alle erforderlichen Parameter festlegen, die Sie später nicht mehr ändern konnten. Durch das Erstellen neuer benutzerdefinierter Richtlinien können Sie Features wie den Skype-Benutzerzugriff oder eine Richtlinie zum Deaktivieren von Audio/Video in der öffentlichen Cloud steuern, was nicht mit vordefinierten Einstellungen abgedeckt wurde. Benutzerdefinierte Richtlinien für den externen Zugriff folgen derselben Syntax wie Client-, Mobilitäts- und Konferenzrichtlinien. Weitere Informationen zu diesen Einstellungen finden Sie [hier.](https://technet.microsoft.com/library/mt228132.aspx)
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version der Skype for Business-Klick-und-Ausführen-App von 2016 verwenden, die sie unterstützt. Die folgende Mindestversion des Skype for Business 2016 Klick-und-Ausführen-Clients ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release für den aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Aktueller Kanal  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Verzögerter Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Skype for Business Windows-Apps oder Mac-Clients verwenden, können weiterhin Dateien übertragen. 
  
## <a name="start-windows-powershell"></a>Starten Windows PowerShell

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls. Wenn Sie die neueste öffentliche Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.
1. Installieren Sie [das Teams PowerShell-Modul.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Herstellen einer Verbindung mit allen [Microsoft 365- oder Office 365-Diensten in](https://technet.microsoft.com/library/dn568015.aspx) einem einzigen Windows PowerShell-Fenster oder Einrichten Ihres Computers [für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Erstellen einer benutzerdefinierten Richtlinie für den externen Zugriff für einen Benutzer

Führen Sie dazu Dies aus:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
