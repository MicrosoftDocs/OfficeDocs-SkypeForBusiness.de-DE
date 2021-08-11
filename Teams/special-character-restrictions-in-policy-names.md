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
description: Sehen Sie sich an, welche Probleme mit Sonderzeichen in den Namen von Richtlinien bestehen und wie Sie das Problem beheben können.
ms.openlocfilehash: b8a628ee261ba813b50d58531ab1255a2f121dc4e4719ff4249de70517215cc3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292972"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?

**Sie können keine Richtlinien (für Nachrichten,** Besprechungen usw.) erstellen oder bearbeiten, die ein Sonderzeichen im Namen im Microsoft Teams Admin Center haben. 

Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie bei der Verwaltung dieser Richtlinien im Microsoft Teams Admin Center eingeschränkt. **Daher wird dringend empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten.** 

Richtliniennamen, die mithilfe von PowerShell für Besprechungen und Messaging in Teams erstellt wurden, können Sonderzeichen wie "@,#,$" enthalten. Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, ist dies nicht möglich. 

Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie die Richtlinie entweder mit Windows PowerShell (für immer) bearbeiten oder im Microsoft Teams Admin Center eine neue Richtlinie mit den gleichen Einstellungen wie die alte Richtlinie erstellen und sie derselben Gruppe von Benutzern zuweisen.

## <a name="to-remove-special-characters"></a>So entfernen Sie Sonderzeichen

**Schritt 1: Herstellen einer Remoteverbindung mit PowerShell.**
> [!NOTE]
> Skype for Business Der Online-Connector ist derzeit Bestandteil des Teams PowerShell-Moduls.
>
> Wenn Sie die neueste Version Teams [PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**Schritt 2: Sie können die Einstellungen für die alte Richtlinie erhalten und die Ausgabe erfassen.**

> [!NOTE]
> Dieses Beispiel gilt für eine [Messagingrichtlinie.](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)  Die Schritte sind für andere Richtlinientypen identisch, aber Sie müssen das richtige Cmdlet verwenden. 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**Schritt 3– Erstellen einer neuen Richtlinie.**

Sie können entweder die neue Richtlinie mit derselben Einstellung erstellen, indem Sie Microsoft Teams Admin Center oder PowerShell verwenden.

Wenn Sie diese Richtlinie ausführen, wird eine neue Richtlinie für Sie erstellt. Sie müssen jedoch die richtigen Einstellungen hinzufügen, indem Sie [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) sehen und dann ausführen:

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**Schritt 4– Zuweisen der Richtlinie.**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)

**Schritt 5: Löschen Sie die alte Richtlinie.**

Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)

Wenn dieser Befehl erfolgreich ist, sind Sie fertig. Wenn der oben aufgeführte Befehl einen Fehler zurückgibt, liegt das daran, dass die alte Richtlinie Benutzern zugewiesen wurde, sodass Sie ausführen müssen, um alle zugewiesenen Benutzer aus der Richtlinie zu entfernen:

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum sollten Sie Office 365 PowerShell verwenden?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Mit Windows PowerShell Modul für Skype for Business Online können Sie eine Remote-Windows PowerShell-Sitzung erstellen, die eine Verbindung mit Skype for Business Online und Microsoft Teams. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
