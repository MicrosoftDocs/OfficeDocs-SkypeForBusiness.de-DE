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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Erfahren Sie, welche Probleme es bei Sonderzeichen in den Namen von Richtlinien gibt und was Sie tun können, um sie zu beheben.
ms.openlocfilehash: bc5a2fbb28e37602b21e6c519ea3b3b7cb9a0325
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569407"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?

**Sie können keine Richtlinien (für Nachrichten,** Besprechungen usw.) erstellen oder bearbeiten, die im Namen im Microsoft Teams Admin Center ein Sonderzeichen haben. 

Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie beim Verwalten dieser Richtlinien im Microsoft Teams Admin Center eingeschränkt. **Daher wird dringend empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten.** 

Richtliniennamen, die mit PowerShell für Besprechungen und Nachrichten in Teams erstellt wurden, können Sonderzeichen wie @,#,$enthalten. Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, können Sie dies nicht. 

Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie die Richtlinie entweder mit Windows PowerShell (für immer) bearbeiten oder eine neue Richtlinie im Microsoft Teams Admin Center mit den gleichen Einstellungen wie die alte Richtlinie erstellen und dieser Gruppe von Benutzern zuweisen.

## <a name="to-remove-special-characters"></a>So entfernen Sie Sonderzeichen

**Schritt 1: Herstellen einer Remoteverbindung mit PowerShell.**
> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Schritt 2: Holen Sie sich die Einstellungen für die alte Richtlinie, und erfassen Sie die Ausgabe.**

> [!NOTE]
> Dieses Beispiel gilt für eine [Messagingrichtlinie.](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)  Die Schritte wären für andere Richtlinientypen identisch, aber Sie müssen das richtige Cmdlet verwenden. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Schritt 3: Erstellen einer neuen Richtlinie.**

Sie können entweder die neue Richtlinie mit derselben Einstellung erstellen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden.

Wenn Sie dies ausführen, wird eine neue Richtlinie für Sie erstellt, Sie müssen jedoch die richtigen Einstellungen hinzufügen, indem [Sie Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) sehen und dann ausführen:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4 : Zuweisen der Richtlinie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Schritt 5 : Löschen der alten Richtlinie.**

Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Wenn dieser Befehl erfolgreich ist, sind Sie fertig. Wenn der obige Befehl einen Fehler zurückgibt, liegt dies daran, dass die alte Richtlinie Benutzern zugewiesen ist, sodass Sie ausführen müssen, um alle zugewiesenen Benutzer aus der Richtlinie zu entfernen:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzelnen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum müssen Sie Office 365 PowerShell verwenden?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Das Windows PowerShell für Skype for Business Online ermöglicht ihnen das Erstellen einer Remotesitzung Windows PowerShell die eine Verbindung mit Skype for Business Online und Microsoft Teams herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  

