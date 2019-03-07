---
title: Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: 3d2bc6f253f048dc07ab99111df3bc1d47788795
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460156"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?

**Sie können nicht erstellt oder Richtlinien bearbeiten (für messaging, Besprechungen, usw.), die ein Sonderzeichen den Namen in der Microsoft-Teams, Administrator haben, zentriert**. 

Wenn ein Richtlinienname Sonderzeichen enthält, werden Sie bei der Verwaltung diese Richtlinien in der Verwaltungskonsole von Microsoft-Teams, eingeschränkt werden. **Daher wird dringend empfohlen, Richtliniennamen keine Sonderzeichen enthalten**. 

Richtliniennamen, die von PowerShell für Besprechungen und messaging in Teams können Sonderzeichen wie haben erstellt wurden @, #, $. Jedoch, wenn Sie die Richtlinie in der Verwaltungskonsole von Microsoft-Teams ändern möchte, Sie kann nicht zu werden. 

Wenn Sie eine Richtlinie mit Sonderzeichen haben, müssen Sie entweder die Richtlinie mithilfe von Windows PowerShell (unbegrenzt) bearbeiten oder erstellen Sie eine neue Richtlinie in der Microsoft-Teams-Verwaltungskonsole mit denselben Einstellungen wie die alte Richtlinie und die gleiche Gruppe von Benutzern zuweisen.

## <a name="to-remove-special-characters"></a>So entfernen Sonderzeichen

**Schritt 1: Stellen Sie eine Remoteverbindung mit PowerShell.** 
 [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , falls Sie noch nicht getan haben.
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Schritt 2 – die Einstellungen für die alte Richtlinie erhalten möchten, und erfassen Sie die Ausgabe.**

> [!NOTE]
> In diesem Beispiel wird für eine [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) -Richtlinie.  Die Schritte wäre für andere Richtlinientypen identisch, aber Sie müssen das richtige-Cmdlet verwenden. 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Schritt 3: Erstellen einer neuen Richtlinie.**

Sie können entweder die neue Richtlinie mit der gleichen Einstellung erstellen, mithilfe der Microsoft-Teams, Administrationscenter oder PowerShell.

Mit dieser wird eine neue Richtlinie für Sie erstellen, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen, und klicken Sie dann ausführen:

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4: Zuweisen der Richtlinie.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.

**Schritt 5: Löschen Sie die alte Richtlinie.**

Dadurch wird die alte Richtlinie mit Sonderzeichen gelöscht.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.

Wenn dieser Befehl erfolgreich ist wird, sind Sie fertig. Wenn Sie der oben aufgeführten Befehl einen Fehler zurückgibt, ist es, da die alte Richtlinie Benutzern zugewiesen ist, Sie ausführen, um alle zugewiesenen Benutzer aus der Richtlinie zu entfernen müssen:

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum müssen Sie Office 365 PowerShell verwenden?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Das Windows PowerShell-Modul für Skype für Business Online können Sie eine remote Windows PowerShell-Sitzung zu erstellen, die mit Skype für Business Online und Microsoft-Teams, eine Verbindung herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  

