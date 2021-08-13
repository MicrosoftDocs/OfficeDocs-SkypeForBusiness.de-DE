---
title: Verwalten von Benutzerkonten mithilfe von Online Connector
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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Verwenden Sie Get-CsOnlineUser-Cmdlet in Windows PowerShell, um Informationen über die Onlinebenutzer Ihrer Skype for Business Organisation zu erhalten.
ms.openlocfilehash: 943a3030c8012d56fb5082c5d85cf58aafa228b662f2b045d90c9d3ba97d80aa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323547"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Verwalten von Benutzerkonten mithilfe von Online Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>Verwalten von Benutzerkonten

Dieses Thema enthält die folgenden Abschnitte:

- [Abrufen von Informationen zu allen Skype for Business Online-Benutzern](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Zurückgeben einer gefilterten Liste von Benutzern in Skype for Business Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> Das Cmdlet **Set-CsUser** ist auch in den Cmdlets enthalten, die für Skype for Business Online-Administratoren zur Verfügung stehen. **Set-CsUser** kann aber zurzeit nicht zum Verwalten von Skype for Business Online verwendet werden, mit einer Ausnahme: Festlegen des Parameters _AudioVideoDisabled_. Wenn Sie versuchen, das Cmdlet mit einem anderen Parameter auszuführen, schlägt dies mit etwa dieser Fehlermeldung fehl: „‚SipAddress' kann nicht festgelegt werden. Dieser Parameter ist auf die Remotemandanten-PowerShell eingeschränkt."

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Abrufen von Informationen zu allen Lync Online-Benutzern
<a name="BKAllUsers"> </a>

Um Informationen zu allen Benutzern abzurufen, die für Skype for Business Online aktiviert sind, rufen Sie das Cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) ohne zusätzliche Parameter auf.

```PowerShell
Get-CsOnlineUser
```

Um Informationen zu einem einzelnen nach dem Zufallsprinzip ausgewählten Benutzer abzurufen (zum Beispiel, um dieses Konto zu Testzwecken zu verwenden), rufen Sie das Cmdlet **Get-CsOnlineUser** auf, und legen Sie den Parameter _ResultSize_ auf „1" fest.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

Dies bewirkt, dass das Cmdlet **Get-CsOnlineUser** Informationen für nur einen Benutzer zurückgibt, unabhängig davon, wie viele Benutzer in der Organisation vorhanden sind. Um Informationen für fünf Benutzer abzurufen, legen Sie den Wert des Parameters _ResultSize_ auf „5" fest.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online
<a name="BKSpecificUser"> </a>

Es gibt mehrere Möglichkeiten, beim Aufruf des Cmdlets [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) auf ein bestimmtes Benutzerkonto zu verweisen. Sie können den Active Directory-Domänendienste (AD DS, Active Directory Domain Services)-Anzeigenamen des Benutzers verwenden.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Sie können die SIP-Adresse des Benutzers verwenden.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Sie können den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers verwenden.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online
<a name="BKSpecificUsers"> </a>

Standardmäßig gibt das Cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) eine große Menge von Informationen zu den einzelnen Skype for Business Online-Benutzerkonten zurück. Wenn Sie sich nur für eine Teilmenge dieser Informationen interessieren, reichen Sie die zurückgegebenen Daten an das Cmdlet **Select-Object** weiter. Dieser Befehl zum Beispiel gibt alle Daten für den Benutzer Ken Myer zurück und beschränkt dann mit dem Cmdlet **Select-Object** die auf dem Bildschirm angezeigten Informationen auf Kens AD DS-Anzeigenamen und Wählplan.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

Der folgende Befehl gibt die Anzeigenamen und Wählpläne für alle Benutzer zurück.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Mit dem folgenden Befehl können Sie die Eigenschaften eines Skype for Business Online-Benutzerkontos suchen.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online
<a name="BKListofUsers"> </a>

Mit dem Cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) und dem Parameter _LdapFilter_ oder _Filter_ können Sie leicht Informationen zu einer bestimmten Gruppe von Benutzern abrufen. Dieser Befehl zum Beispiel gibt alle Benutzer aus der Finanzabteilung zurück.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für die Onlineverwaltung in Skype for Business mithilfe Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
