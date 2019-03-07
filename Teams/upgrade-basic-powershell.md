---
title: Grundlegende Upgrade PowerShell | Microsoft-Teams | Interop-Richtlinie GRANT-Upgrade
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Stetig für das Upgrade auf Teams, falls noch nicht im Admin Center in Ihrem Mandanten eingeschaltet
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f81e796d893ef17138398c8a5739a4284bcfc4a3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459740"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihre Benutzer von Skype für Business Online auf Microsoft-Teams

> [!Note]
> Die Befehle, die in diesem Artikel beschriebenen werden im Rahmen der [Einfachen Upgrade](https://aka.ms/UpgradeBasic) Prüfliste verwendet werden soll.

Die Migration technische Aspekte des Upgrades unterstützen könnte benachrichtigen der Benutzer, dass Skype für Unternehmen durchführen eines auf Teams Upgrades und anschließendes auf einen Modus **nur Teams verschieben** . Diese Schritte können über einen Skype für Business remote Windows PowerShell-Sitzung oder über das Microsoft-Teams, Administrationscenter ausgeführt werden.

Wir sind in der [Microsoft-Teams, Administrationscenter](manage-teams-skypeforbusiness-admin-center.md)tooling Upgrade aktiv Rollout, und es sollte bei Ihrem Mandanten bald verfügbar sein. Sobald sie verfügbar ist, finden Sie Informationen zur Migration von Benutzern in [Ihrer Koexistenz festlegen und Einstellungen zu aktualisieren](https://aka.ms/SkypeToTeams-SetCoexistence).

Wenn Sie noch heute Upgrade bereit sind, können Sie die [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle in der folgenden Tabelle aufgeführt.

| Grundlegende-Upgrade – Schritt # | Modus | PowerShell-Befehl |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Inseln + benachrichtigen der Skype für Geschäftsbenutzer<br>(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit **Inseln** Modus (Standard) werden) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(beispielsweise $SipAddress = "TestUser@contoso.com")*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype für Unternehmen nur + benachrichtigen der Skype für Geschäftsbenutzer <br>(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit im Modus **für Unternehmen nur Skype** sind) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Nur Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |