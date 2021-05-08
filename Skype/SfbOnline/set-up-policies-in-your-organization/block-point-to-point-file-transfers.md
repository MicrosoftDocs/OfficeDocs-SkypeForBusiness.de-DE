---
title: Blockieren von Punkt-zu-Punkt-Dateiübertragungen
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: In Skype for Business Online haben Sie die Möglichkeit, die Übertragungen von P2P-Dateien (Point-to-Point) als Teil der vorhandenen Konferenzrichtlinieneinstellungen zu steuern. Dies ermöglicht oder blockiert Dateiübertragungen für Benutzer unabhängig davon, ob sie Dateien an einen Benutzer innerhalb derselben Organisation oder an einen Partnerbenutzer aus einer anderen Organisation übertragen. Mit den nachstehenden Schritten können Sie die Übertragung von P2P-Dateien an Partnerorganisationen oder Partner blockieren.
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240174"
---
# <a name="block-point-to-point-file-transfers"></a>Blockieren von Punkt-zu-Punkt-Dateiübertragungen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In Skype for Business Online haben Sie die Möglichkeit, die Übertragungen von P2P-Dateien (Point-to-Point) als Teil der vorhandenen Konferenzrichtlinieneinstellungen zu steuern. Dies ermöglicht oder blockiert Dateiübertragungen für Benutzer unabhängig davon, ob sie Dateien an einen Benutzer innerhalb derselben Organisation oder an einen Partnerbenutzer aus einer anderen Organisation übertragen. Mit den nachstehenden Schritten können Sie die Übertragung von P2P-Dateien an Partnerorganisationen oder Partner blockieren.
  
 Ein sehr häufiges Szenario ist, dass Sie internen Benutzern die Verwendung von P2P-Dateiübertragungen gestatten möchten, aber die Dateiübertragung mit Partnerpartnern blockieren. In diesem Szenario müssten Sie wie hier beschrieben vor gehen:
  
- Weisen Sie Benutzern in Ihrer Organisation eine Konferenzrichtlinie mit aktivierter P2P-Dateiübertragung _(EnableP2PFileTransfer_ auf _True)_ zu.
    
- Erstellen Sie eine globale Kommunikationsrichtlinie für externe Benutzer, um externe P2P-Dateiübertragungen zu blockieren _(EnableP2PFileTransfer_ auf _False_ festgelegt), und weisen Sie sie einem Benutzer in Ihrer Organisation zu. 
    
Weitere Informationen zu diesen Einstellungen finden Sie [hier.](/previous-versions//mt228132(v=technet.10))
  
Wenn ein Partnerbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer zu senden, für den die Richtlinie angewendet wurde, wird ein Fehler bei der Übertragung **angezeigt.** Und wenn ein Benutzer versucht, eine Datei zu senden, erhält er einen Fehler **"Dateiübertragung ist deaktiviert".**
  
Dazu muss der Benutzer eine unterstützte Version einer Klick-und-Ausführen-App der Version 2016 Skype for Business verwenden, die dies unterstützt. Die folgende Mindestversion des Skype for Business 2016 Klick-und-Ausführen-Clients ist erforderlich:
  
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
1. Installieren Sie [Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Verbinden für alle [Microsoft 365-](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) oder Office 365-Dienste in einem einzigen Windows PowerShell-Fenster oder Einrichten des Computers [für Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deaktivieren von P2P-Dateiübertragungen für Ihre Organisation

Standardmäßig ist _EnableP2PFileTransfer_ für die globale Richtlinie der Organisation aktiviert. Beim Erstellen der Richtlinie wurde Ihren Benutzern die _Richtlinie "BposSAllModality"_ zugewiesen.
  
Wenn Sie P2P-Übertragungen für innerhalb Ihrer Organisation zulassen, externe Dateiübertragungen an eine andere Organisation jedoch blockieren möchten, müssen Sie dies nur auf globaler Ebene ändern. Führen Sie dazu dies aus:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deaktivieren von P2P-Dateiübertragungen für einen Benutzer

Sie können dies auf einen Benutzer anwenden, indem Sie eine neue Richtlinie erstellen und für diesen Benutzer gewähren. Führen Sie dazu dies aus: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Centers viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
