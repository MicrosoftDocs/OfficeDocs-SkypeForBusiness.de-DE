---
title: Unterstützung für die Verwendung von SEFAUtil-Funktionen in PowerShell in Skype for Business Server 2019
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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie, wie Sie mithilfe von PowerShell SEFAUtil-Funktionen in Skype for Business Server 2019 nach der Installation von kumulativem Update 1 erhalten.'
ms.openlocfilehash: 24040a3da5dc2549996463078a55324f3fc03657
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232566"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019

SEFAUtil (sekundäre Erweiterung Feature Activation) ermöglicht es Skype for Business Server Administratoren und Helpdesk-Agents, Einstellungen für die Anrufannahme durch Stellvertretung, Anrufweiterleitung und Gruppenanrufe im Namen eines Skype for Business Server Benutzers zu konfigurieren. Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen Abfragen, die für einen bestimmten Benutzer veröffentlicht werden. Nachdem Sie das kumulative Update für Skype for Business Server 2019 Juli installiert haben, können die folgenden Funktionen, die derzeit nur über SEFAUtil verwaltet werden können, auch über PowerShell verwaltet werden:

- [Einstellungen für die Anrufweiterleitung](#call-forwarding-settings)
- [Stellvertretungs Einstellungen](#delegation-settings)
- [Team Mitglieder und zugehörige Einstellungen](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Einstellungen für die Anrufweiterleitung

Administratoren können die Einstellungen für die Anrufweiterleitung mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Dieses Cmdlet gibt die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurück und zeigt dasselbe auf dem Bildschirm an.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Dieses Cmdlet ändert die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers. Dieses Cmdlet gibt die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurück und zeigt die gleichen auf dem Bildschirm an, falls ein Erfolg vorliegt. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des Benutzers deaktiviert (hier werden zwei verschiedene Parameter Beispiele gezeigt).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Dieses Cmdlet ändert die Einstellungen für die Anrufweiterleitung des Benutzers.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Mit diesem Cmdlet werden die gleich-Einstellungen geändert (wiederum mit zwei Parameter Beispielen, einer für unbeantwortete Voicemail und der zweite als unbeantwortet).

## <a name="delegation-settings"></a>Stellvertretungs Einstellungen

Administratoren können die Delegierungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt der Stell Vertretungsliste zurück und zeigt die Delegate-Liste des angegebenen Benutzers an, wenn der Vorgang erfolgreich verläuft. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Mit diesem Cmdlet werden die Delegierungseinstellungen des angegebenen Benutzers geändert, ein Objekt der Stell Vertretungsliste zurückgegeben und die Liste der Stellvertretungen im Erfolgsfall angezeigt. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Mit diesem Cmdlet wird ein Delegat hinzugefügt oder entfernt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Mit diesem Cmdlet wird eine Stell Vertretungsliste auf bestimmte Delegaten festgelegt.

## <a name="team-members-and-related-settings"></a>Team Mitglieder und zugehörige Einstellungen

Administratoren können Teammitglieder und Verwandte Einstellungen ändern, indem Sie das folgende Cmdlet in PowerShell verwenden:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt auf dem Bildschirm an, falls es erfolgreich ist. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Dieses Cmdlet ändert die Liste der Teammitglieder des angegebenen Benutzers, gibt ein Objekt zurück, das die Liste der Teammitglieder enthält, und zeigt das Objekt auf dem Bildschirm an, falls es erfolgreich ist. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Mit diesem Cmdlet werden Teammitglieder hinzugefügt oder entfernt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Mit diesem Cmdlet wird eine Team Liste auf bestimmte Elemente festgelegt.

## <a name="more-information"></a>Weitere Informationen

Für lokale Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen gemäß der unten angegebenen Zugriffsebene ausgeführt werden:

- CsAdministrator – abrufen und festlegen für alle Cmdlets
- CsVoiceAdministrator-Get und festgelegt für alle Cmdlets
- "Cshelpdesk"-Get für alle Cmdlets

Weitere Informationen zu diesen Administratorrollen finden Sie unter [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Der Administrator kann auf diese Cmdlets zugreifen, indem er sich direkt oder Remote an einem Server Computer anmeldet.
Für eine hybridbereitstellung sollten Skype for Business Administratoren in der Lage sein, Get und für alle Cmdlets festzulegen aufzurufen. Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> Die automatische Server Ermittlung muss aktiviert sein. Für die Verwendung der Cmdlets werden keine zusätzlichen Lizenzierungsanforderungen eingeführt.
