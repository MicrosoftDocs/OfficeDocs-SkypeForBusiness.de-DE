---
title: Standard-Upgrade-PowerShell | Microsoft Teams | Grant Upgrade-Interop-Richtlinie
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Notlösung für das Upgrade auf Teams, wenn das Admin Center nicht in Ihrem Mandanten leuchtet
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397cabcbba35c153d234bc4355d12e4eb44b5c57
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435089"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams

> [!Note]
> Die in diesem Artikel beschriebenen Befehle sind so konzipiert, dass Sie als Teil der [Upgrade Basic](https://aka.ms/UpgradeBasic) -Checkliste verwendet werden.

Die technischen Migrationsaspekte Ihres Upgrades führen dazu, dass Ihre Nutzer benachrichtigt werden, dass Skype for Business ein Upgrade auf Teams durchführt und diese dann in den Modus **nur für Teams** verschiebt. Diese Schritte können über eine Skype for Business-Remote-Windows PowerShell-Sitzung oder über das Microsoft Teams Admin Center durchgeführt werden.

Wir arbeiten aktiv am Upgrade-Tool im [Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md)und sollten in Kürze für Ihren Mandanten verfügbar sein. Sobald es verfügbar ist, finden Sie Informationen zum Migrieren Ihrer Benutzer beim [Festlegen ihrer Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence).

Wenn Sie zum heutigen Upgrade bereit sind, können Sie die in der folgenden Tabelle aufgelisteten [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle verwenden.

| Upgrade grundlegender Schritt # | Modus | PowerShell-Befehl |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Inseln + Benachrichtigung des Skype for Business-Benutzers<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im Modus " **Inseln** " (Standard) befinden) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Beispiel: $SipAddress = "testuser@contoso.com")* |
| [5](upgrade-basic.md#step-5) | Nur Skype for Business + Benachrichtigung des Skype for Business-Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit **nur im Skype for Business** -Modus befinden) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Nur für Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
