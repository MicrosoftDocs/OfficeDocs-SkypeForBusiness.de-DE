---
title: Einrichten von Clientrichtlinien für Ihre Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240087"
---
# <a name="set-up-client-policies-for-your-organization"></a>Einrichten von Clientrichtlinien für Ihre Organisation

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
  
Clientrichtlinieneinstellungen können beim Erstellen einer Richtlinie konfiguriert werden, oder Sie können das **Set-CsClientPolicy-Cmdlet** verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-client-policies"></a>Festlegen Ihrer Clientrichtlinien

> [!NOTE]
> Für alle Clientrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="start-windows-powershell"></a>Starten Windows PowerShell

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
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deaktivieren von Emoticons und Anwesenheitsbenachrichtigungen und Verhindern der Speicherung von Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Weitere Informationen finden Sie [im New-CsClientPolicy-Cmdlet.](/powershell/module/skype/New-CsClientPolicy)
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy-Cmdlet.](/powershell/module/skype/Grant-CsClientPolicy)
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsClientPolicy-Cmdlet](/powershell/module/skype/Grant-CsClientPolicy) verwenden, um die Einstellungen auf Ihre Benutzer anzuwenden.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Aktivieren von klickbaren URLs oder Hyperlinks in Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Weitere Informationen finden Sie [im New-CsClientPolicy-Cmdlet.](/powershell/module/skype/New-CsClientPolicy)
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy-Cmdlet.](/powershell/module/skype/Grant-CsClientPolicy)
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsClientPolicy-Cmdlet](/powershell/module/skype/Grant-CsClientPolicy) verwenden, um die Einstellungen auf Ihre Benutzer anzuwenden.
  
### <a name="prevent-showing-recent-contacts"></a>Verhindern der Anzeige der letzten Kontakte

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Weitere Informationen finden Sie [im New-CsClientPolicy-Cmdlet.](/powershell/module/skype/New-CsClientPolicy)
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy-Cmdlet.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das [Cmdlet Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und dann das [Grant-CsClientPolicy-Cmdlet](/powershell/module/skype/Grant-CsClientPolicy) verwenden, um die Einstellungen auf Ihre Benutzer anzuwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Centers viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
