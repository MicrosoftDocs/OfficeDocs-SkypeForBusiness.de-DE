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
description: Sehen Sie sich die Probleme mit Sonderzeichen in den Namen der Richtlinien an, und was Sie tun können, um Sie zu beheben.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814714"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?

**Sie können keine Richtlinien (für Nachrichten, Besprechungen usw.) erstellen oder bearbeiten, die im Namen des Microsoft Teams admin Centers ein Sonderzeichen enthalten**. 

Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie im Microsoft Teams Admin Center auf die Verwaltung dieser Richtlinien limitiert. Daher **wird nachdrücklich empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten**. 

Richtliniennamen, die mit PowerShell für Besprechungen und Nachrichten in Teams erstellt wurden, können Sonderzeichen wie @, #, $ aufweisen. Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, ist dies nicht möglich. 

Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie entweder die Richtlinie mit Windows PowerShell (für immer) bearbeiten oder eine neue Richtlinie im Microsoft Teams Admin Center mit den gleichen Einstellungen wie die alte Richtlinie erstellen und der gleichen Benutzergruppe zuweisen.

## <a name="to-remove-special-characters"></a>So entfernen Sie Sonderzeichen

**Schritt 1: Erstellen einer Remoteverbindung mit PowerShell**
> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**Schritt 2: Abrufen der Einstellungen für die alte Richtlinie und Aufzeichnen der Ausgabe.**

> [!NOTE]
> In diesem Beispiel handelt es sich um eine [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Richtlinie.  Die Schritte wären für andere Richtlinientypen identisch, aber Sie müssen das richtige Cmdlet verwenden. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Schritt 3 – Erstellen einer neuen Richtlinie**

Sie können entweder die neue Richtlinie mit der gleichen Einstellung erstellen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden.

Wenn Sie dies ausführen, wird eine neue Richtlinie für Sie erstellt, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen und dann ausführen:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4: Zuweisen der Richtlinie**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .

**Schritt 5: Löschen der alten Richtlinie**

Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .

Wenn dieser Befehl erfolgreich ausgeführt wird, sind Sie fertig. Wenn der obige Befehl einen Fehler zurückgibt, liegt dies daran, dass die alte Richtlinie Benutzern zugewiesen ist, damit Sie alle zugewiesenen Benutzer aus der Richtlinie entfernen müssen:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum müssen Sie Office 365 PowerShell verwenden?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, die eine Verbindung mit Skype for Business Online und Microsoft Teams herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  

