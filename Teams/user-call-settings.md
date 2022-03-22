---
title: Konfigurieren von Anrufeinstellungen für Benutzer
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie Benutzereinstellungen für Anruf weiterleiten und Delegierung konfigurieren.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689123"
---
# <a name="configure-call-settings-for-your-users"></a>Konfigurieren von Anrufeinstellungen für Ihre Benutzer

In diesem Artikel wird beschrieben, wie Sie, der Administrator, die Anruf weiterleitungs- und Delegierungseinstellungen für Ihre Benutzer ändern können. Diese Einstellungen können Sie beispielsweise ändern, wenn:

- Ein Benutzer ist krank, und Sie müssen sicherstellen, dass eingehende Anrufe an den Benutzer an einen Kollegen weitergeleitet werden.

- Sie müssen die Anruf weiterleiten-Einstellungen für alle Benutzer in einer Abteilung prüfen und potenziell nach Bedarf korrigieren.

- Ein neuer Assistent wurde eingestellt, und Sie müssen den Assistenten als Stellvertreter für eine Gruppe von Mitarbeitern hinzufügen.

Sie können Teams Admin Center oder Teams PowerShell-Cmdlets zum Anzeigen und Ändern von Anrufeinstellungen für Benutzer verwenden.

Um Anrufeinstellungen für einen Benutzer festlegen zu können, muss dem Benutzer eine Microsoft-Telefon Systemlizenz zugewiesen sein.

## <a name="use-the-teams-admin-center"></a>Verwenden des Teams Admin Centers

Sie können das Teams Admin Center verwenden, um Gruppenanrufabrufabrufe und Anrufdelegierung für Ihre Benutzer zu konfigurieren. 

> [!NOTE]
> Die Option zum Konfigurieren der Anrufanrufeinstellungen ist derzeit nicht im Teams Admin Center verfügbar.

So konfigurieren Sie das Abholen von Gruppenanrufen:

1. Wechseln Sie Teams Admin Center zu **Benutzer** >  **Verwalten von Benutzern**, und wählen Sie einen Benutzer aus.

2. Wechseln Sie auf der Seite mit den Benutzerdetails zur **Registerkarte Sprache** .

3. Wählen Sie **unter Gruppenanrufabrufabruf** die **Option Personen hinzufügen aus**. 

4. Geben Sie Einstellungen für **Anrufverzögerung und -reihenfolge an**.

Um Delegierung zu konfigurieren, wechseln Sie auf derselben Seite zu **Anrufdelegierung** , und wählen Sie **Personen hinzufügen aus**.

## <a name="use-powershell"></a>Verwenden von PowerShell

Sie können PowerShell verwenden, um Anruf weiterleiten und Delegierungseinstellungen für Ihre Benutzer zu konfigurieren.  Sie verwenden die folgenden Cmdlets, die in der PowerShell Teams 4.0 oder höher verfügbar sind:

- [Get-CsUserCallingSettings – Zeigt Anruf weiterleitungseinstellungen](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) , Stellvertretung und Delegatorinformationen für einen Benutzer an.

- [Set-CsUserCallingSettings – Legt Anruf weiterleitungseinstellungen](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) für einen Benutzer fest.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) – Fügt eine neue Stellvertretung mit Berechtigungen für einen Benutzer hinzu.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) – Ändert die Berechtigungen für eine vorhandene Stellvertretung.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) – Entfernt eine Stellvertretung von einem Benutzer.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Anzeigen von Anruf weiterleiten- und Delegierungseinstellungen für einen Benutzer

Zum Anzeigen der aktuellen Anruf weiterleiten- und Delegierungseinstellungen für einen Benutzer verwenden Sie das Get-CsUserCallingSettings-Cmdlet, wie im folgenden Beispiel dargestellt:

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

Die Ausgabe zeigt, dass Benutzer1 gleichzeitiges Klingeln bei Stellvertretung konfiguriert hat. Nicht beantwortete Anrufe werden nach 20 Sekunden an die Voicemail gesendet. Benutzer2 ist als Stellvertretung mit allen Stellvertretungsberechtigungen definiert.


### <a name="set-call-forward-settings-for-a-user"></a>Festlegen von Anruf weiterleitungseinstellungen für einen Benutzer

Wenn Sie alle Aufrufe von Benutzer1 an Benutzer2 weiterleiten möchten, verwenden Sie das Set-CsUserCallingSettings-Cmdlet, wie im folgenden Beispiel dargestellt: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Um gleichzeitig an alle Delegaten für Benutzer3 zu klingeln, verwenden Sie das Set-CsUserCallingSettings-Cmdlet, wie im folgenden Beispiel dargestellt: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

Im folgenden Beispiel wird das Set-CsUserCallingSettings-Cmdlet verwendet, um eine Anrufgruppe für Benutzer4 mit "user5" und "user6" als Mitglieder zu konfigurieren. Alle Anrufe an Mitglieder der Gruppe werden in der Reihenfolge weitergeleitet, in der sie definiert sind: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Weitere Beispiele finden Sie unter [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Hinzufügen einer Anrufstellvertretung für einen Benutzer

Wenn Sie Benutzer2 als Stellvertretung für Benutzer1 mit allen zulässigen Berechtigungen hinzufügen möchten, verwenden Sie das New-CsUserCallingDelegate-Cmdlet, wie im folgenden Beispiel dargestellt: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Ändern der Berechtigungen einer Anrufstellvertretung

Wenn Sie die Stellvertretungsberechtigungen ändern möchten , um beispielsweise nicht zu erlauben, dass Benutzer2 Anrufe für Benutzer1 macht, verwenden Sie das Set-CsUserCallingDelegate-Cmdlet, wie im folgenden Beispiel dargestellt: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Entfernen einer Anrufstellvertretung für einen Benutzer

Wenn Sie Benutzer2 als Delegat für Benutzer1 entfernen möchten, verwenden Sie das Remove-CsUserCallingDelegate-Cmdlet, wie im folgenden Beispiel dargestellt: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Verwandte Themen

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
