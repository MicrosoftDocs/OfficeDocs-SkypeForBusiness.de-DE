---
title: Grundlegendes Upgrade von PowerShell| Microsoft Teams| Gewähren der Richtlinie für Upgrade-Inop
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie mehr über ein Stopp-Upgrade auf Microsoft Teams, wenn das Admin Center in Ihrem Mandanten nicht ausgeleuchtet wurde.
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
ms.openlocfilehash: 61201e52eabd9a921da432ac7081329a643664c7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628217"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams

> [!Note]
> Die in diesem Artikel beschriebenen Befehle sind für die Verwendung als Teil der [Checkliste Upgrade Basic](./upgrade-start-here.md) gedacht.

Die technischen Migrationsaspekte Ihres Upgrades haben die Benachrichtigung Ihrer Benutzer darüber zur Folge, dass Skype for Business auf Teams aktualisiert und sie dann in einen **Teams-Modus** wechselt. Diese Schritte können über eine Skype for Business Remote-Windows PowerShell oder über das Microsoft Teams Admin Center durchgeführt werden.

Wir führen die Upgradetools im [](manage-teams-skypeforbusiness-admin-center.md)Admin Center Microsoft Teams ein und sollten in Kürze für Ihren Mandanten verfügbar sein. Sobald es verfügbar ist, finden Sie Informationen zum Migrieren ihrer Benutzer unter Festlegen der [Koexistenz- und Upgradeeinstellungen.](./setting-your-coexistence-and-upgrade-settings.md)

Wenn Sie zum heutigen Upgrade bereit sind, können Sie die [PowerShell-Befehle](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) verwenden, die in der folgenden Tabelle aufgeführt sind.

| Grundlegendes Upgradeschritt # | Modus | PowerShell-Befehl |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype for Business User<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **Islands-Modus** befinden (Standard)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Beispiel: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Nur + Benachrichtigen des Skype for Business Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich benutzer derzeit nur **im Skype for Business befinden.)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Nur | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |