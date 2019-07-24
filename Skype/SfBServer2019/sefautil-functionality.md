---
title: Unterstützung für die Verwendung der SEFAUtil-Funktion in PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie, wie Sie mithilfe von PowerShell SEFAUtil-Funktionen in Skype for Business Server 2019 nach der Installation des kumulativen Updates 1 erhalten.'
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821327"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019

SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht es Skype for Business Server-Administratoren und Helpdesk-Agents, die Einstellungen für Stellvertretung, Anrufweiterleitung und Gruppenanruf-Abholung im Auftrag eines Skype for Business Server-Benutzers zu konfigurieren. Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind. Nachdem Sie dieses Update installiert haben, sind die folgenden Funktionen, die derzeit nur über SEFAUtil verwaltet werden können, auch über PowerShell verwaltbar:

- [Einstellungen für die Anrufweiterleitung](#call-forwarding-settings)
- [Delegierungseinstellungen](#delegation-settings)
- [Team Mitglieder und Verwandte Einstellungen](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Einstellungen für die Anrufweiterleitung

Administratoren können die Einstellungen für die Anrufweiterleitung mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurückgegeben und auf dem Bildschirm angezeigt.

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers geändert. Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurückgegeben und im Erfolgsfall auf dem Bildschirm angezeigt. Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Dieses Cmdlet deaktiviert die Einstellungen für die Anrufweiterleitung des Benutzers (hier werden zwei verschiedene Parameter Beispiele gezeigt).

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Dieses Cmdlet ändert die Einstellungen für die Anrufweiterleitung des Benutzers.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Mit diesem Cmdlet werden die SimulRing-Einstellungen geändert (erneut mit zwei Parameter Beispielen: eine für unbeantwortete Voicemail und die zweite für andere nicht beantwortet).

## <a name="delegation-settings"></a>Delegierungseinstellungen

Administratoren können Delegierungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt der Stell Vertretungsliste zurück und zeigt die Delegatliste des angegebenen Benutzers im Erfolgsfall an. Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Dieses Cmdlet ändert die Delegierungseinstellungen des angegebenen Benutzers, gibt ein Objekt einer Stell Vertretungsliste zurück und zeigt die Liste der Stellvertretungen im Erfolgsfall an. Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Mit diesem Cmdlet wird eine Stellvertretung hinzugefügt oder entfernt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Mit diesem Cmdlet wird eine Delegate-Liste auf bestimmte Stellvertretungen festgelegt.

## <a name="team-members-and-related-settings"></a>Team Mitglieder und Verwandte Einstellungen

Administratoren können Teammitglieder und Verwandte Einstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Dieses Cmdlet ändert die Liste der Teammitglieder des angegebenen Benutzers, gibt ein Objekt zurück, das die Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Mit diesem Cmdlet werden Teammitglieder hinzugefügt oder entfernt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Dieses Cmdlet legt eine Teamliste auf bestimmte Mitglieder fest.

## <a name="more-information"></a>Weitere Informationen

Bei lokalen Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen pro der unten angegebenen Zugriffsebene ausgeführt werden:

- CsAdministrator – abrufen und einstellen für alle Cmdlets
- CsVoiceAdministrator-abrufen und einstellen für alle Cmdlets
- CsHelpDesk-Get für alle Cmdlets

Weitere Informationen zu diesen Administratorrollen finden Sie unter [Erstellen von Administratoren für Skype for Business Server Control Panel](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Der Administrator kann über direkte oder Remoteanmeldung an einem Server Computer auf diese Cmdlets zugreifen.
Für eine hybridbereitstellung sollten Skype for Business-Administratoren in der Lage sein, Get und für alle Cmdlets festzulegen. Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter Informationen [zu Office 365-Administratorrollen](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles) .

> [!NOTE]
> Die automatische Server Ermittlung muss aktiviert sein. Für die Verwendung der Cmdlets werden keine zusätzlichen Lizenzierungsanforderungen eingeführt.
