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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Informationen zur Verwendung von PowerShell zum Abrufen der SEFAUtil-Funktionalität in Skype for Business Server 2019 nach der Installation des kumulativen Updates 1.'
ms.openlocfilehash: fa7bccaa30b559bf694274471b1f8883e8482861
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629004"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019

SEFAUtil (Secondary Extension Feature Activation) ermöglicht es Skype for Business Server-Administratoren und Helpdesk-Agents, Die Einstellungen für das Stellvertretungsringen, die Anruf weiterleitung und die Gruppenanrufannahme im Namen eines Skype for Business Server konfigurieren. Mit diesem Tool können Administratoren auch die Anrufroutingeinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht werden. Nachdem Sie das kumulative Update Skype for Business Server 2019 Juli installiert haben, sind die folgenden Funktionen, die derzeit nur über SEFAUtil verwaltet werden können, auch über PowerShell verwaltbar:

- [Einstellungen für die Anruf weiterleitung](#call-forwarding-settings)
- [Delegierungseinstellungen](#delegation-settings)
- [Teammitglieder und zugehörige Einstellungen](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Einstellungen für die Anruf weiterleitung

Administratoren können die Einstellungen für die Anruf weiterleitung mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Dieses Cmdlet gibt die Anruf weiterleitungseinstellungen des angegebenen Benutzers als Objekt zurück und zeigt dasselbe auf dem Bildschirm an.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Mit diesem Cmdlet werden die Anruf weiterleitungseinstellungen des angegebenen Benutzers geändert. Dieses Cmdlet gibt die Anruf weiterleitungseinstellungen des angegebenen Benutzers als Objekt zurück und wird im Erfolgsfall auf dem Bildschirm angezeigt. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Dieses Cmdlet deaktiviert die Anruf weiterleitungseinstellungen des Benutzers (hier werden zwei verschiedene Parameterbeispiele angezeigt).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Mit diesem Cmdlet werden die Einstellungen für die Anruf weiterleitung des Benutzers geändert.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Dieses Cmdlet ändert die gleichzeitigen Ringeinstellungen (wiederum mit zwei Parameterbeispielen, eines für nicht beantwortete Voicemail und das zweite für nicht beantwortete).

## <a name="delegation-settings"></a>Delegierungseinstellungen

Administratoren können die Delegierungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt der Stellvertretungsliste zurück und zeigt die Stellvertretungsliste des angegebenen Benutzers an, falls dies erfolgreich ist. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Dieses Cmdlet ändert die Delegierungseinstellungen des angegebenen Benutzers, gibt ein Objekt der Delegatenliste zurück und zeigt die Liste der Stellvertreter an, falls dies erfolgreich ist. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Dieses Cmdlet fügt einen Delegaten hinzu oder entfernt ihn.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Dieses Cmdlet legt eine Delegatliste auf bestimmte Delegaten fest.

## <a name="team-members-and-related-settings"></a>Teammitglieder und zugehörige Einstellungen

Administratoren können Teammitglieder und zugehörige Einstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Dieses Cmdlet gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Dieses Cmdlet ändert die Teammitgliederliste des angegebenen Benutzers, gibt ein Objekt zurück, das die Teammitgliedsliste enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an. Bei einem Fehler wird eine entsprechende Fehlermeldung angezeigt.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Dieses Cmdlet fügt Teammitglieder hinzu oder entfernt sie.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Dieses Cmdlet legt eine Teamliste auf bestimmte Mitglieder fest.

## <a name="more-information"></a>Weitere Informationen

Bei lokalen Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen ausgeführt werden, je nach der unten angegebenen Zugriffsebene:

- CsAdministrator – Get and Set für alle Cmdlets
- CsVoiceAdministrator – Get and Set für alle Cmdlets
- CsHelpDesk – Get for all cmdlets

Weitere Informationen zu diesen Administratorrollen finden Sie unter [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). Der Administrator kann auf diese Cmdlets zugreifen, indem er sich direkt oder remote bei einem Servercomputer anmeldet.
Bei einer Hybridbereitstellung Skype for Business Administratoren get und Set für alle Cmdlets aufrufen können. Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter [Informationen zu Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> Die automatische Serverermittlung muss aktiviert sein. Es werden keine zusätzlichen Lizenzierungsanforderungen für die Verwendung der Cmdlets eingeführt.
