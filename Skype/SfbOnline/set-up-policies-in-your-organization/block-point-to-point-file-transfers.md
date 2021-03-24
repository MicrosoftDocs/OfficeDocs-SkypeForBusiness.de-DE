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
description: In Skype for Business Online können Sie die Punkt-zu-Punkt-Dateiübertragung (P2P) als Teil der vorhandenen Richtlinieneinstellungen für Konferenzen steuern. Dies ermöglicht oder blockiert jedoch Dateiübertragungen für Benutzer, unabhängig davon, ob sie Dateien an einen Benutzer übertragen, der sich innerhalb derselben Organisation befindet, oder an einen Verbundbenutzer aus einer anderen Organisation. Mit den nachstehenden Schritten können Sie P2P-Dateiübertragungen mit Verbundorganisationen oder Partnern blockieren.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100621"
---
# <a name="block-point-to-point-file-transfers"></a>Blockieren von Punkt-zu-Punkt-Dateiübertragungen

In Skype for Business Online können Sie die Punkt-zu-Punkt-Dateiübertragung (P2P) als Teil der vorhandenen Richtlinieneinstellungen für Konferenzen steuern. Dies ermöglicht oder blockiert jedoch Dateiübertragungen für Benutzer, unabhängig davon, ob sie Dateien an einen Benutzer übertragen, der sich innerhalb derselben Organisation befindet, oder an einen Verbundbenutzer aus einer anderen Organisation. Mit den nachstehenden Schritten können Sie P2P-Dateiübertragungen mit Verbundorganisationen oder Partnern blockieren.
  
 Ein sehr häufiges Szenario ist, wenn Sie internen Benutzern erlauben möchten, die P2P-Dateiübertragung zu verwenden, aber die Dateiübertragung mit Partnerpartnern zu blockieren. Für dieses Szenario müssten Sie dies tun:
  
- Weisen Sie Benutzern in Ihrer Organisation eine Konferenzrichtlinie mit aktivierter P2P-Dateiübertragung zu (_EnableP2PFileTransfer_ auf _True_ festgelegt).
    
- Erstellen Sie eine globale Externe Benutzerkommunikationsrichtlinie, die so festgelegt ist, dass externe P2P-Dateiübertragungen blockiert werden _(EnableP2PFileTransfer_ auf _False_ festgelegt), und weisen Sie sie einem Benutzer in Ihrer Organisation zu. 
    
Weitere Informationen zu diesen Einstellungen finden Sie [hier.](/previous-versions//mt228132(v=technet.10))
  
Wenn ein Verbundbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer zu  senden, bei dem die Richtlinie angewendet wurde, erhält er einen Übertragungsfehler. Und wenn ein Benutzer versucht, eine Datei  zu senden, erhält er einen Fehler beim Deaktivieren der Dateiübertragung.
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version einer Skype for Business-Klick-und-Ausführen-App von 2016 verwenden, die sie unterstützt. Die folgende Mindestversion des Skype for Business 2016 Klick-und-Ausführen-Clients ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release für den aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Aktueller Kanal  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Verzögerter Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Skype for Business Windows-Apps oder Mac-Clients verwenden, können weiterhin Dateien übertragen. 
  
## <a name="start-windows-powershell"></a>Starten Windows PowerShell

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
1. Installieren Sie [das Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Herstellen einer Verbindung mit allen [Microsoft 365- oder Office 365-Diensten in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) einem einzigen Windows PowerShell-Fenster oder Einrichten Ihres Computers [für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deaktivieren von P2P-Dateiübertragungen für Ihre Organisation

Standardmäßig ist _EnableP2PFileTransfer_ für die globale Richtlinie der Organisation aktiviert. Beim Erstellen wurde Den Benutzern die _Richtlinie "BposSAllModality"_ zugewiesen.
  
Wenn Sie P2P-Übertragungen innerhalb Ihrer Organisation zulassen, aber externe Dateiübertragungen an eine andere Organisation blockieren möchten, müssen Sie sie nur auf globaler Ebene ändern. Führen Sie dazu aus:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deaktivieren von P2P-Dateiübertragungen für einen Benutzer

Sie können dies auf einen Benutzer anwenden, indem Sie eine neue Richtlinie erstellen und diesem Benutzer gewähren. Führen Sie dazu aus: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
