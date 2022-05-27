---
title: Unterstützung der Verwendung von SEFAUtil-Funktionen in Skype PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Zusammenfassung: Erfahren Sie, wie Sie nach der Installation von kumulativem Update 1 mithilfe von PowerShell seFAUtil-Funktionen in Skype for Business Server 2019 abrufen.'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676537"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019

SEFAUtil (Secondary Extension Feature Activation) ermöglicht es Skype for Business Server Administratoren und Helpdesk-Agents, Einstellungen für Stellvertretungs-Klingeln, Anrufweiterleitung und Gruppenanrufannahme im Namen von Skype for Business Server Benutzern zu konfigurieren. MIT SEFAUtil können Administratoren auch die Anrufweiterleitungseinstellungen für einen bestimmten Benutzer abfragen.

Nachdem Sie das kumulative Update für Skype for Business Server 2019 vom Juli 2019 installiert haben, sind die folgenden Funktionen, die nur über SEFAUtil verfügbar waren, auch in Skype PowerShell verfügbar:

- [Anrufweiterleitungseinstellungen](#call-forwarding-settings)
- [Delegierungseinstellungen](#delegation-settings)
- [Teammitglieder und zugehörige Einstellungen](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Anrufweiterleitungseinstellungen

Administratoren können die Anrufweiterleitungseinstellungen mithilfe der folgenden Befehle in PowerShell ändern:

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Mit diesem Befehl werden die Anrufweiterleitungseinstellungen des angegebenen Benutzers als Objekt zurückgegeben und auf dem Bildschirm angezeigt.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Mit diesem Befehl werden die Anrufweiterleitungseinstellungen des angegebenen Benutzers geändert. Mit diesem Befehl werden die Anrufweiterleitungseinstellungen des angegebenen Benutzers als Objekt zurückgegeben und auf dem Bildschirm angezeigt. Wenn der Befehl nicht erfolgreich ist, wird eine entsprechende Fehlermeldung angezeigt.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Mit diesem Befehl werden die Anrufweiterleitungseinstellungen des Benutzers deaktiviert (hier werden zwei verschiedene Parameterbeispiele gezeigt).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Mit diesem Befehl werden die Anrufweiterleitungseinstellungen des Benutzers geändert.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Mit diesem Befehl werden die Einstellungen für das gleichzeitige Klingeln geändert (wiederum mit zwei Parameterbeispielen, eines für "Nicht beantwortet" für Voicemail und das zweite für "Unbeantwortet" für andere).

## <a name="delegation-settings"></a>Delegierungseinstellungen

Administratoren können Delegierungseinstellungen mithilfe des folgenden Befehls in PowerShell ändern:

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Dieser Befehl gibt ein Objekt der Delegatliste zurück und zeigt die Delegatliste des angegebenen Benutzers an. Wenn der Befehl nicht erfolgreich ist, wird eine entsprechende Fehlermeldung angezeigt.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Dieser Befehl ändert die Delegierungseinstellungen des angegebenen Benutzers, gibt ein Objekt der Delegatliste zurück und zeigt die Liste der Stellvertretungen an. Wenn der Befehl nicht erfolgreich ist, wird eine entsprechende Fehlermeldung angezeigt.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Mit diesem Befehl wird ein Delegat hinzugefügt oder entfernt.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Mit diesem Befehl wird eine Delegatliste auf bestimmte Stellvertretungen festgelegt.

## <a name="team-members-and-related-settings"></a>Teammitglieder und zugehörige Einstellungen

Administratoren können Teammitglieder und zugehörige Einstellungen mithilfe des folgenden Befehls in PowerShell ändern:

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Dieser Befehl gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt auf dem Bildschirm an. Wenn der Befehl nicht erfolgreich ist, wird eine entsprechende Fehlermeldung angezeigt.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Dieser Befehl ändert die Liste der Teammitglieder des angegebenen Benutzers, gibt ein Objekt zurück, das die Teammitgliedsliste enthält, und zeigt das Objekt auf dem Bildschirm an. Wenn der Befehl nicht erfolgreich ist, wird eine entsprechende Fehlermeldung angezeigt.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Mit diesem Befehl werden Teammitglieder hinzugefügt oder entfernt.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Mit diesem Befehl wird eine Teamliste auf bestimmte Mitglieder festgelegt.

## <a name="more-information"></a>Weitere Informationen

Bei lokalen Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen gemäß der unten angegebenen Zugriffsebene ausgeführt werden:

- CsAdministrator – Abrufen und Festlegen für alle Cmdlets
- CsVoiceAdministrator – Abrufen und Festlegen für alle Cmdlets
- CsHelpDesk – Abrufen für alle Cmdlets

Weitere Informationen zu diesen Administratorrollen finden Sie unter ["Erstellen von Skype for Business Server Systemsteuerung Administratoren](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)". Der Administrator kann auf diese Cmdlets zugreifen, indem er sich direkt oder remote bei einem Servercomputer anmeldet.
Für eine Hybridbereitstellung sollten Skype for Business Administratoren in der Lage sein, Get und Set für alle Cmdlets aufzurufen. Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter ["Informationen zu Administratorrollen"](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> Die automatische Serverermittlung muss aktiviert sein. Für die Verwendung der Cmdlets werden keine zusätzlichen Lizenzierungsanforderungen eingeführt.
