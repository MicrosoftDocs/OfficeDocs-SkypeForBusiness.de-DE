---
title: Unterstützung für die Verwendung der SEFAUtil-Funktionalität in PowerShell in Skype for Business Server 2019
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie PowerShell verwenden, um SEFAUtil-Funktionen in Skype for Business Server 2019 nach der Installation des kumulativen Updates 1 abzurufen.'
ms.openlocfilehash: 88e62543f41d9a497b9b0ca28c55322fbe5f5be7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578179"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019

SEFAUtil (Secondary Extension Feature Activation) ermöglicht Skype for Business Server Administratoren und Helpdesk-Agents die Konfiguration der Einstellungen für Stellvertretungsringe, Anrufweiterleitung und Gruppenanrufannahme im Namen eines Skype for Business Server Benutzers. Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht wurden. Nach der Installation des kumulativen Updates vom Skype for Business Server. Juli 2019 können die folgenden Funktionen, die derzeit nur über SEFAUtil verwaltet werden können, auch über PowerShell verwaltet werden:

- [Anrufweiterleitungseinstellungen](#call-forwarding-settings)
- [Delegierungseinstellungen](#delegation-settings)
- [Teammitglieder und verwandte Einstellungen](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Anrufweiterleitungseinstellungen

Administratoren können die Anrufweiterleitungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Dieses Cmdlet gibt die Anrufweiterleitungseinstellungen des angegebenen Benutzers als Objekt zurück und zeigt dasselbe auf dem Bildschirm an.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Mit diesem Cmdlet werden die Anrufweiterleitungseinstellungen des angegebenen Benutzers geändert. Dieses Cmdlet gibt die Anrufweiterleitungseinstellungen des angegebenen Benutzers als Objekt zurück und zeigt diese im Erfolgsfall auf dem Bildschirm an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Dieses Cmdlet deaktiviert die Anrufweiterleitungseinstellungen des Benutzers (hier zeigen wir zwei verschiedene Parameterbeispiele).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Mit diesem Cmdlet werden die Anrufweiterleitungseinstellungen des Benutzers geändert.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Dieses Cmdlet ändert die Einstellungen für gleichzeitiges Klingeln (wiederum mit zwei Parameterbeispielen, eines für nicht beantwortete Voicemail und das zweite für andere nicht beantwortet).

## <a name="delegation-settings"></a>Delegierungseinstellungen

Administratoren können delegierungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt der Delegatenliste zurück und zeigt im Erfolgsfall die Stellvertretungsliste des angegebenen Benutzers an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Dieses Cmdlet ändert die Delegierungseinstellungen des angegebenen Benutzers, gibt ein Objekt der Delegatenliste zurück und zeigt im Erfolgsfall die Liste der Delegaten an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Mit diesem Cmdlet wird ein Delegat hinzugefügt oder entfernt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Mit diesem Cmdlet wird eine Stellvertretungsliste auf bestimmte Delegaten festgelegt.

## <a name="team-members-and-related-settings"></a>Teammitglieder und verwandte Einstellungen

Administratoren können Teammitglieder und zugehörige Einstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Dieses Cmdlet ändert die Liste der Teammitglieder des angegebenen Benutzers, gibt ein Objekt zurück, das die Teammitgliedsliste enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Mit diesem Cmdlet werden Teammitglieder hinzugefügt oder entfernt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Mit diesem Cmdlet wird eine Teamliste auf bestimmte Mitglieder festgelegt.

## <a name="more-information"></a>Weitere Informationen

Bei lokalen Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen gemäß der unten angegebenen Zugriffsebene ausgeführt werden:

- CsAdministrator – Abrufen und Festlegen für alle Cmdlets
- CsVoiceAdministrator – Abrufen und Festlegen für alle Cmdlets
- CsHelpDesk – Abrufen für alle Cmdlets

Weitere Informationen zu diesen Administratorrollen finden Sie unter [Erstellen Skype for Business Server Systemsteuerungsadministratoren.](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) Der Administrator kann auf diese Cmdlets zugreifen, indem er sich direkt oder remote bei einem Servercomputer anmeldet.
Bei einer Hybridbereitstellung sollten Skype for Business Administratoren für alle Cmdlets "Get" und "Set" aufrufen können. Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter ["Informationen zu Administratorrollen".](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> Die automatische Serverermittlung muss aktiviert sein. Für die Verwendung der Cmdlets werden keine zusätzlichen Lizenzierungsanforderungen eingeführt.
