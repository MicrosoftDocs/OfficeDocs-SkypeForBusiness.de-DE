---
title: Einrichten von Richtlinien für mobile Geräte für Ihre Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können.
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569197"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Einrichten von Richtlinien für mobile Geräte für Ihre Organisation

Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können.
  
Richtlinieneinstellungen für mobile Geräte können Sie bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsMobilityPolicy** -Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-mobile-policies"></a>Festlegen Ihrer Richtlinien für mobile Geräte

> [!NOTE]
> Für alle Richtlinieneinstellungen für mobile Geräte in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="start-windows-powershell"></a>Starten Windows PowerShell

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
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Festlegen einer WLAN-Verbindung als erforderlich für Video für einen Benutzer

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Weitere Informationen finden Sie im [Cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Weitere Informationen finden Sie im [Grant-CsMobilityPolicy-Cmdlet.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Verhindern, dass ein Benutzer die Skype for Business-App verwendet

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Weitere Informationen finden Sie im [Cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Weitere Informationen finden Sie im [Grant-CsMobilityPolicy-Cmdlet.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsMobilityPolicy-Cmdlet](https://technet.microsoft.com/library/mt779149.aspx) verwenden, um die Einstellung auf Ihre Benutzer anzuwenden.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Verhindern, dass ein Benutzer Voice over IP-Anrufe über ein mobiles Gerät tätigt

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Weitere Informationen finden Sie im [Cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Weitere Informationen finden Sie im [Grant-CsMobilityPolicy-Cmdlet.](https://technet.microsoft.com/library/mt779149.aspx)
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe, warum Sie microsoft Windows PowerShell Office 365 oder Office 365 verwalten möchten](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
