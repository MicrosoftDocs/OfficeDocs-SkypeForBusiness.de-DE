---
title: Verwalten von Benutzerkonten
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users.
ms.openlocfilehash: 973529682224231e997e3900664fb5163156dfc3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221763"
---
# <a name="manage-user-accounts"></a>Verwalten von Benutzerkonten

## <a name="manage-user-accounts"></a>Verwalten von Benutzerkonten

Dieses Thema enthält die folgenden Abschnitte:

- [Abrufen von Informationen zu allen Skype for Business Online-Benutzern](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Zurückgeben einer gefilterten Liste mit Benutzern in Skype for Business Online](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> Das Cmdlet **Set-CsUser** ist auch in den Cmdlets enthalten, die für Skype for Business Online-Administratoren zur Verfügung stehen. **Set-CsUser** kann aber zurzeit nicht zum Verwalten von Skype for Business Online verwendet werden, mit einer Ausnahme: Festlegen des Parameters _AudioVideoDisabled_. Wenn Sie versuchen, das Cmdlet mit einem anderen Parameter auszuführen, schlägt dies mit etwa dieser Fehlermeldung fehl: „‚SipAddress' kann nicht festgelegt werden. Dieser Parameter ist auf die Remotemandanten-PowerShell eingeschränkt."

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Abrufen von Informationen zu allen Lync Online-Benutzern
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Um Informationen zu allen Benutzern abzurufen, die für Skype for Business Online aktiviert sind, rufen Sie das Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) ohne zusätzliche Parameter auf.

```
Get-CsOnlineUser
```

Um Informationen zu einem einzelnen nach dem Zufallsprinzip ausgewählten Benutzer abzurufen (zum Beispiel, um dieses Konto zu Testzwecken zu verwenden), rufen Sie das Cmdlet **Get-CsOnlineUser** auf, und legen Sie den Parameter _ResultSize_ auf „1" fest.

```
Get-CsOnlineUser -ResultSize 1
```

Dies bewirkt, dass das Cmdlet **Get-CsOnlineUser** Informationen für nur einen Benutzer zurückgibt, unabhängig davon, wie viele Benutzer in der Organisation vorhanden sind. Um Informationen für fünf Benutzer abzurufen, legen Sie den Wert des Parameters _ResultSize_ auf „5" fest.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online
<a name="BKMKReturnInfoSpecificUser"> </a>

Es gibt mehrere Möglichkeiten, beim Aufruf des Cmdlets [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) auf ein bestimmtes Benutzerkonto zu verweisen. Sie können den Active Directory-Domänendienste (AD DS, Active Directory Domain Services)-Anzeigenamen des Benutzers verwenden.

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Sie können die SIP-Adresse des Benutzers verwenden.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Sie können den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers verwenden.

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online
<a name="BKMKReturninfoSpecificUsers"> </a>

Standardmäßig gibt das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) eine große Menge von Informationen zu den einzelnen Skype for Business Online-Benutzerkonten zurück. Wenn Sie sich nur für eine Teilmenge dieser Informationen interessieren, reichen Sie die zurückgegebenen Daten an das Cmdlet **Select-Object** weiter. Dieser Befehl zum Beispiel gibt alle Daten für den Benutzer Ken Myer zurück und beschränkt dann mit dem Cmdlet **Select-Object** die auf dem Bildschirm angezeigten Informationen auf Kens AD DS-Anzeigenamen und Wählplan.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Der folgende Befehl gibt die Anzeigenamen und Wählpläne für alle Benutzer zurück.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Mit dem folgenden Befehl können Sie die Eigenschaften eines Skype for Business Online-Benutzerkontos suchen.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online
<a name="BKMKReturnFilteredListofUsers"> </a>

Mit dem Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) und dem Parameter _LdapFilter_ oder _Filter_ können Sie leicht Informationen zu einer bestimmten Gruppe von Benutzern abrufen. Dieser Befehl zum Beispiel gibt alle Benutzer aus der Finanzabteilung zurück.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Skype for Business Online-Verwaltung mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


