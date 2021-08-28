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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype for Business Online ermöglicht es Ihnen, zusätzliche Richtlinien für externen Zugriff zu erstellen. Im Gegensatz zu Client- oder Konferenzrichtlinien, bei denen sie über mehrere Kombinationen verfügen können, gibt es drei vordefinierte Richtlinien für externen Zugriff, die die meisten Szenarien abdecken können.
ms.openlocfilehash: d0ecf5051de17f923983e16f35eb22b66c41571e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619271"
---
# <a name="create-custom-external-access-policies"></a>Erstellen von benutzerdefinierten externen Zugriffsrichtlinien

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online ermöglicht es Ihnen, zusätzliche Richtlinien für externen Zugriff zu erstellen. Im Gegensatz zu Client- oder Konferenzrichtlinien, bei denen sie über mehrere Kombinationen verfügen können, gibt es drei vordefinierte Richtlinien für externen Zugriff, die die meisten Szenarien abdecken können. Dies sind:
  
- Kein Verbund- oder Skype Consumer Access (_Tag:NoFederationAndPIC)_
    
- Nur Partnerverbundzugriff (_Tag:VerbundOnly)_
    
- Verbund- und Verbraucherzugriff _(FederationAndPICDefault)_
    
Mit benutzerdefinierten externen Richtlinien können Sie zusätzliche Richtlinien erstellen, die von den oben genannten Einstellungen nicht abgedeckt werden. Beim Erstellen der Richtlinie mussten Sie alle erforderlichen Parameter festlegen und können sie später nicht mehr ändern. Das Erstellen neuer benutzerdefinierter Richtlinien ermöglicht es Ihnen, Features wie Skype-Verbraucherzugriff oder eine Richtlinie zum Deaktivieren von Audio/Video in der öffentlichen Cloud zu steuern, was von vordefinierten Einstellungen nicht abgedeckt wurde. Benutzerdefinierte Richtlinien für externen Zugriff folgen derselben Syntax wie Client-, Mobilitäts- und Konferenzrichtlinien. Weitere Informationen zu diesen Einstellungen finden Sie [hier.](/previous-versions//mt228132(v=technet.10))
  
Dazu muss der Benutzer eine unterstützte Version der Klick-und-Ausführen-App von 2016 Skype for Business verwenden, die dies unterstützt. Die folgende Mindestversion des Skype for Business 2016 Klick-und-Ausführen-Clients ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release für aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Aktueller Kanal  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Verzögerter Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Skype for Business Windows oder Mac-Clients verwenden, können weiterhin Dateien übertragen. 
  
## <a name="start-windows-powershell"></a>Starten Windows PowerShell

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
1. Installieren Sie [Teams PowerShell-Modul .](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Verbinden aller [Microsoft 365-](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) oder Office 365-Dienste in einem einzigen Windows PowerShell-Fenster oder Einrichten ihres Computers [für Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Erstellen einer benutzerdefinierten Richtlinie für externen Zugriff für einen Benutzer

Führen Sie dazu dies aus:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365, Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Center beispielsweise, wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen, viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen
[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
