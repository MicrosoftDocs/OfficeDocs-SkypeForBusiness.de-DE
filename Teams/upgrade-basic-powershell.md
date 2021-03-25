---
title: Grundlegendes Upgrade von PowerShell| Microsoft Teams| Inopop-Richtlinie für Upgrade gewähren
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie mehr über ein Stoppgap für ein Upgrade auf Microsoft Teams, wenn das Admin Center nicht in Ihrem Mandanten leuchtet.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120540"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams

> [!Note]
> Die in diesem Artikel beschriebenen Befehle sind so konzipiert, dass sie als Teil der [Checkliste Upgrade Basic verwendet](./upgrade-start-here.md) werden.

Die technischen Migrationsaspekte Ihres Upgrades müssen Ihre Benutzer darüber informieren, dass Skype for Business ein Upgrade auf Teams vor sich hat, und sie dann in einen **Modus mit nur Teams** verschieben. Diese Schritte können über eine Skype for Business-Remotesitzung Windows PowerShell oder über das Microsoft Teams Admin Center durchgeführt werden.

Wir bereiten das Upgradetool im [Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md)aktiv vor, und es sollte in Kürze für Ihren Mandanten verfügbar sein. Sobald sie verfügbar ist, finden Sie Informationen zum Migrieren Ihrer Benutzer unter [Festlegen ihrer Koexistenz- und Upgradeeinstellungen.](./setting-your-coexistence-and-upgrade-settings.md)

Wenn Sie heute ein Upgrade durchführen möchten, können Sie die in der folgenden Tabelle aufgeführten [PowerShell-Befehle](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) verwenden.

| Upgrade basic step # | Modus | Befehl "PowerShell" |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Inseln + Benachrichtigen des Skype for Business-Benutzers<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **Inselmodus** befinden (Standard)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(z. B. $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Only + Benachrichtigen des Skype for Business-Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit nur im **Skype for Business-Modus** befinden.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Nur Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |