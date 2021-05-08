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
> Die in diesem Artikel beschriebenen Befehle sind für die Verwendung als Teil der [Checkliste Upgrade Basic](./upgrade-start-here.md) gedacht.

Die technischen Migrationsaspekte Ihres Upgrades haben zur Folge, dass Ihre Benutzer benachrichtigt werden, dass Skype for Business ein Upgrade auf Teams durchführen wird, und sie dann in den **Teams-Modus** verschieben. Diese Schritte können über eine Skype for Business Remote-Windows PowerShell oder über das Microsoft Teams Admin Center durchgeführt werden.

Wir führen die Upgradetools im Microsoft Teams [Admin Center](manage-teams-skypeforbusiness-admin-center.md)aktiv ein und sollten in Kürze für Ihren Mandanten verfügbar sein. Sobald es verfügbar ist, finden Sie Informationen zum Migrieren ihrer Benutzer unter Festlegen der [Koexistenz- und Upgradeeinstellungen.](./setting-your-coexistence-and-upgrade-settings.md)

Wenn Sie zum heutigen Upgrade bereit sind, können Sie die [PowerShell-Befehle](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) verwenden, die in der folgenden Tabelle aufgeführt sind.

| Grundlegendes Upgradeschritt # | Modus | PowerShell-Befehl |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype for Business User<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **Islands-Modus** befinden (Standard)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Beispiel: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Nur + Benachrichtigen des Skype for Business Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit nur **im Skype for Business modus** befinden.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Nur | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |