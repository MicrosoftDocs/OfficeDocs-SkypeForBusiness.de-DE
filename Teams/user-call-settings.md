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
description: Erfahren Sie, wie Sie Benutzereinstellungen für anrufweiterleitung und -delegierung konfigurieren.
ms.openlocfilehash: 46fc88d20efb14ea130f38d9be284f8faad6f80f
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817776"
---
# <a name="configure-call-settings-for-your-users"></a>Konfigurieren von Anrufeinstellungen für Ihre Benutzer

In diesem Artikel wird beschrieben, wie Sie als Administrator die Anrufweiterleitungs- und Delegierungseinstellungen für Ihre Benutzer ändern können. Möglicherweise möchten Sie diese Einstellungen ändern, z. B.:

- Ein Benutzer ist im Krankheitsurlaub, und Sie müssen sicherstellen, dass eingehende Anrufe an den Benutzer an einen Kollegen weitergeleitet werden.

- Sie müssen die Anrufweiterleitungseinstellungen für alle Benutzer in einer Abteilung überprüfen und diese ggf. korrigieren.

- Ein neuer Assistent wurde beschäftigt, und Sie müssen den Assistenten als Stellvertretung für eine Gruppe von Mitarbeitern hinzufügen.

Sie können das Teams Admin Center oder Teams PowerShell-Cmdlets verwenden, um Anrufeinstellungen für Benutzer anzuzeigen und zu ändern.

Um Anrufeinstellungen für einen Benutzer festzulegen, muss dem Benutzer eine Microsoft-Telefon Systemlizenz zugewiesen sein.

## <a name="use-the-teams-admin-center"></a>Verwenden des Teams Admin Centers

Sie können das Teams Admin Center verwenden, um Anrufweiterleitungs- und unbeantwortete Einstellungen, Gruppenanrufannahme und Anrufdelegierung für Ihre Benutzer zu konfigurieren. 

So konfigurieren Sie die Einstellungen für die sofortige Anrufweiterleitung:

1. Wechseln Sie im Teams Admin Center zu **UsersManage-Benutzern** > , und wählen Sie einen Benutzer aus.

2. Wechseln Sie auf der Seite "Benutzerdetails" zur Registerkarte " **VoIP** ".

3. Wählen Sie unter **"Anrufbeantwortungsregeln**" die Option **"Sofort weitergeleitet werden**" aus, und wählen Sie den entsprechenden Anrufweiterleitungstyp und das entsprechende Ziel aus.

Um das gleichzeitige Klingeln zu konfigurieren, wählen Sie auf derselben Seite **"Anrufen" auf den Geräten des Benutzers** aus. Wählen Sie in der Dropdownliste **"Auch zulassen** " die entsprechende Einstellung für gleichzeitiges Klingeln aus.

Um unbeantwortete Einstellungen zu konfigurieren, wählen Sie auf derselben Seite die entsprechende Einstellung in der Dropdownliste **"Wenn unbeantwortet** " aus. Geben Sie im **Ring für diese Anzahl von Sekunden vor dem Umleiten** die Anzahl der zu wartenden Sekunden an.

Die Konfiguration der Anrufdelegierung und der Gruppenanrufannahme wird in die Einstellungen für Anrufweiterleitung und unbeantwortete Anrufe integriert, indem der entsprechende Typ ausgewählt wird. Um beispielsweise zu konfigurieren, dass Anrufe auch die Stellvertretungen des Benutzers anrufen sollen, wählen Sie auf derselben Seite unter **"Auch zulassen**" die Option **"Anrufdelegierung**" aus. Fügen Sie dann die entsprechenden Stellvertretungen hinzu, indem Sie " **Personen hinzufügen"** auswählen und auf **"Speichern"** klicken.


## <a name="use-powershell"></a>Verwenden von PowerShell

Sie können PowerShell verwenden, um Anrufweiterleitungs- und Delegierungseinstellungen für Ihre Benutzer zu konfigurieren.  Sie verwenden die folgenden Cmdlets, die in Teams PowerShell-Modul Version 4.0 oder höher verfügbar sind:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) – Zeigt Anrufweiterleitungseinstellungen, Stellvertretungen und Delegatorinformationen für einen Benutzer an.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) – Legt Anrufweiterleitungseinstellungen für einen Benutzer fest.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) – Fügt einen neuen Delegaten mit Berechtigungen für einen Benutzer hinzu.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) – Ändert berechtigungen für einen vorhandenen Delegaten.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) – Entfernt einen Delegaten von einem Benutzer.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Anzeigen von Anrufweiterleitungs- und Delegierungseinstellungen für einen Benutzer

Verwenden Sie zum Anzeigen der aktuellen Anrufweiterleitungs- und Delegierungseinstellungen für einen Benutzer das cmdlet Get-CsUserCallingSettings, wie im folgenden Beispiel gezeigt:

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

Die Ausgabe zeigt, dass benutzer1 gleichzeitiges Klingeln an Stellvertretungen konfiguriert hat. Unbeantwortete Anrufe werden nach 20 Sekunden an die Voicemail gesendet. User2 ist als Stellvertretung mit allen Stellvertretungsberechtigungen definiert.


### <a name="set-call-forward-settings-for-a-user"></a>Festlegen von Anrufweiterleitungseinstellungen für einen Benutzer

Verwenden Sie das cmdlet Set-CsUserCallingSettings, wie im folgenden Beispiel gezeigt, um alle Aufrufe für Benutzer1 an Benutzer2 weiterzuleiten: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Verwenden Sie das cmdlet Set-CsUserCallingSettings, wie im folgenden Beispiel gezeigt, um alle Stellvertretungen gleichzeitig an den Benutzer 3 zu rufen: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

Im folgenden Beispiel wird das cmdlet Set-CsUserCallingSettings verwendet, um eine Anrufgruppe für Benutzer4 mit Benutzer5 und Benutzer6 als Mitglieder zu konfigurieren. Alle Aufrufe an Mitglieder der Gruppe werden in der reihenfolge weitergeleitet, in der sie definiert sind: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Weitere Beispiele finden Sie unter [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Hinzufügen eines Anrufdelegats für einen Benutzer

Um Benutzer2 als Stellvertretung für Benutzer1 mit allen zulässigen Berechtigungen hinzuzufügen, verwenden Sie das cmdlet New-CsUserCallingDelegate, wie im folgenden Beispiel gezeigt: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Berechtigungen für anrufdelegierte Stellvertretung ändern

Verwenden Sie das cmdlet Set-CsUserCallingDelegate wie im folgenden Beispiel gezeigt, um Stellvertretungsberechtigungen zu ändern , z. B. um Benutzer2 nicht zu erlauben, Aufrufe für Benutzer1 zu tätigen: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Entfernen einer aufrufenden Stellvertretung für einen Benutzer

Um Benutzer2 als Stellvertretung für Benutzer1 zu entfernen, verwenden Sie das cmdlet Remove-CsUserCallingDelegate, wie im folgenden Beispiel gezeigt: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Verwandte Themen

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
