---
title: Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: 4ddd6a618c42f629acd64162ad608aede6b1819f
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "20397089"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?

**Erstellen oder Bearbeiten von Richtlinien (für messaging, Besprechungen, usw.), die den Namen in der Microsoft-Teams und Skype für Business Admin Center ein Sonderzeichen aufweisen.** 

Wenn Sie ein Richtliniennamen Sonderzeichen enthält, werden Sie bei der Verwaltung diese Richtlinien in der Microsoft-Teams und Skype für Business Admin Center eingeschränkt werden. **Daher wird dringend empfohlen, Richtliniennamen keine Sonderzeichen enthalten**. 

Richtliniennamen, die von PowerShell für Besprechungen und messaging in Teams können Sonderzeichen wie haben erstellt wurden @, #, $. Jedoch, wenn Sie die Richtlinie in der Microsoft-Teams und Skype für Business Admin Center ändern möchte, Sie kann nicht zu werden. 

Wenn Sie eine Richtlinie mit Sonderzeichen haben, müssen Sie die Richtlinie mithilfe von Windows PowerShell (unbegrenzt) bearbeiten oder erstellen eine neue Richtlinie in der Microsoft-Teams und Skype für Business Admin Center mit denselben Einstellungen wie die alte Richtlinie und weisen Sie es der gleichen Grupe p von Benutzern.

## <a name="to-remove-special-characters"></a>So entfernen Sonderzeichen



**Schritt 1: Stellen Sie eine Remoteverbindung mit PowerShell.** 
 [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , falls Sie noch nicht getan haben.
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

Sie können entweder die neue Richtlinie mit der gleichen Einstellung mit dem Microsoft-Teams und Skype für Business-Verwaltungskonsole oder PowerShell erstellen.

Mit dieser wird eine neue Richtlinie für Sie erstellen, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen, und klicken Sie dann ausführen:

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4: Zuweisen der Richtlinie.**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.

**Schritt 5: Löschen Sie die alte Richtlinie.**

Dadurch wird die alte Richtlinie mit Sonderzeichen gelöscht.
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.

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
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Das Windows PowerShell-Modul für Skype für Business Online können Sie eine remote Windows PowerShell-Sitzung zu erstellen, die mit Skype für Business Online und Microsoft-Teams, eine Verbindung herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
### <a name="related-topics"></a>See Also
