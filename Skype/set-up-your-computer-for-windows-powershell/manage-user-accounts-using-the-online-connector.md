---
title: "Verwalten von Benutzerkonten mithilfe der Skype für Online Business-Connector"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Verwalten von Benutzerkonten mithilfe der Skype für Online Business-Connector

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer).  
  
## Verwalten von Benutzerkonten

Dieses Thema enthält die folgenden Abschnitte:
  
- [Abrufen von Informationen zu allen Skype for Business Online-Benutzern](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online ](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> Das Cmdlet **Set-CsUser** ist auch in den Cmdlets enthalten, die für Skype for Business Online-Administratoren zur Verfügung stehen. **Set-CsUser** kann aber zurzeit nicht zum Verwalten von Skype for Business Online verwendet werden, mit einer Ausnahme: Festlegen des Parameters _AudioVideoDisabled_. Wenn Sie versuchen, das Cmdlet mit einem anderen Parameter auszuführen, schlägt dies mit etwa dieser Fehlermeldung fehl: „‚SipAddress' kann nicht festgelegt werden. Dieser Parameter ist auf die Remotemandanten-PowerShell eingeschränkt." 
  
### Abrufen von Informationen zu allen Skype for Business Online-Benutzern
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

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

### Abrufen von Informationen zu einem bestimmten Benutzer in Skype for Business Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Es gibt mehrere Möglichkeiten, beim Aufruf des Cmdlets [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) auf ein bestimmtes Benutzerkonto zu verweisen. Sie können den Active Directory Domain Services (AD DS)-Anzeigenamen des Benutzers verwenden.
  
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

### Abrufen von bestimmten Informationen zu bestimmten Benutzern in Skype for Business Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

Standardmäßig gibt das Cmdlet [Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) eine große Menge von Informationen zu den einzelnen Skype for Business Online-Benutzerkonten zurück. Wenn Sie sich nur für eine Teilmenge dieser Informationen interessieren, reichen Sie die zurückgegebenen Daten an das Cmdlet **Select-Object** weiter. Dieser Befehl zum Beispiel gibt alle Daten für den Benutzer Ken Myer zurück und beschränkt dann mit dem Cmdlet **Select-Object** die auf dem Bildschirm angezeigten Informationen auf Kens AD DS-Anzeigenamen und Wählplan.
  
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

### Abrufen einer gefilterten Liste mit Benutzern in Skype for Business Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

Mit dem Cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) und dem Parameter _LdapFilter_ oder _Filter_ können Sie leicht Informationen zu einer bestimmten Gruppe von Benutzern abrufen. Dieser Befehl zum Beispiel gibt alle Benutzer aus der Finanzabteilung zurück.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

