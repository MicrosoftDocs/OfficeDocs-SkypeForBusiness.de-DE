---
title: Einschränkungen für Sonderzeichen in Teams-Richtlinien
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Sehen Sie, welche Probleme es mit Sonderzeichen in den Namen von Richtlinien gibt und was Sie tun können, um es zu beheben.
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860078"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?

**Sie können keine Richtlinien (für Messaging, Besprechungen usw.) erstellen oder bearbeiten, die im Namen im Microsoft Teams Admin Center ein Sonderzeichen aufweisen**. 

Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie bei der Verwaltung dieser Richtlinien im Microsoft Teams Admin Center eingeschränkt. **Daher wird dringend empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten**. 

Richtliniennamen, die mithilfe von PowerShell für Besprechungen und Nachrichten in Teams erstellt wurden, können Sonderzeichen wie "@,#"$" aufweisen. Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, können Sie dies nicht. 

Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie die Richtlinie entweder mit Windows PowerShell (für immer) bearbeiten oder eine neue Richtlinie im Microsoft Teams Admin Center mit den gleichen Einstellungen wie die alte Richtlinie erstellen und derselben Benutzergruppe zuweisen.

## <a name="to-remove-special-characters"></a>So entfernen Sie Sonderzeichen

**Schritt 1: Herstellen einer Remoteverbindung mit PowerShell.**
> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste [Teams öffentlichen PowerShell-Version](https://www.powershellgallery.com/packages/MicrosoftTeams/) verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Schritt 2: Abrufen der Einstellungen für die alte Richtlinie und Erfassen der Ausgabe.**

> [!NOTE]
> Dieses Beispiel betrifft eine [Messagingrichtlinie](/powershell/module/skype/get-csteamsmessagingpolicy) .  Die Schritte sind für andere Richtlinientypen identisch, Sie müssen jedoch das richtige Cmdlet verwenden. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Schritt 3: Erstellen einer neuen Richtlinie.**

Sie können entweder die neue Richtlinie mit derselben Einstellung erstellen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden.

Wenn Sie dies ausführen, wird eine neue Richtlinie für Sie erstellt, Sie müssen jedoch die richtigen Einstellungen hinzufügen, indem [Sie "Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) " anzeigen und dann ausführen:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4 : Zuweisen der Richtlinie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) .

**Schritt 5: Löschen der alten Richtlinie.**

Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) .

Wenn dieser Befehl erfolgreich ist, sind Sie fertig. Wenn der obige Befehl einen Fehler zurückgibt, liegt dies daran, dass die alte Richtlinie Benutzern zugewiesen ist, sodass Sie ausführen müssen, um alle zugewiesenen Benutzer aus der Richtlinie zu entfernen:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum müssen Sie Office 365 PowerShell verwenden?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat viele Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Remote-Windows PowerShell-Sitzung erstellen, die eine Verbindung mit Skype for Business Online und Microsoft Teams herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) heruntergeladen werden.
