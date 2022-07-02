---
title: PowerShell für grundlegende Upgrades| Microsoft Teams| Upgradeinteroperabilitätsrichtlinie gewähren
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie mehr über eine Notlösung für das Upgrade auf Microsoft Teams, wenn das Admin Center in Ihrem Mandanten nicht angezeigt wurde.
ms.localizationpriority: medium
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606034"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams

> [!Note]
> Die in diesem Artikel beschriebenen Befehle sind so konzipiert, dass sie als Teil der [Upgrade Basic-Checkliste](./upgrade-start-here.md) verwendet werden.

Die technischen Migrationsaspekte Ihres Upgrades umfassen die Benachrichtigung Ihrer Benutzer, dass Skype for Business ein Upgrade auf Teams durchführen und sie dann in den **Modus "Nur Teams**" verschieben. Diese Schritte können über eine Skype for Business Remote-Windows PowerShell-Sitzung oder über das Microsoft Teams Admin Center ausgeführt werden.

Wir führen das Upgradetool im [Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md) aktiv aus, und es sollte bald auf Ihrem Mandanten verfügbar sein. Sobald es verfügbar ist, finden Sie Informationen zum Migrieren Ihrer Benutzer unter ["Festlegen Ihrer Koexistenz- und Upgradeeinstellungen"](./setting-your-coexistence-and-upgrade-settings.md).

Wenn Sie noch heute zum Upgrade bereit sind, können Sie die in der folgenden Tabelle aufgeführten [PowerShell-Befehle](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) verwenden.

| Schritt "Upgrade Basic" # | Modus | PowerShell-Befehl |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Inseln + Benachrichtigen des Skype for Business Benutzers<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **Inselmodus** befinden (Standard)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(z. B. $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | nur Skype for Business + Benachrichtigen des Skype for Business Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **modus "nur Skype for Business**" befinden.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Nur Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |