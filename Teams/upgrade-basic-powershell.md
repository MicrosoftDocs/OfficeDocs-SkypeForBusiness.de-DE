---
title: Grundlegendes Upgrade von PowerShell| Microsoft Teams| Gewähren der Inoprichtlinie für Upgrade
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie mehr über ein Stoppgap für das Upgrade auf Microsoft Teams, wenn das Admin Center in Ihrem Mandanten nicht ausgebündet wurde.
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809095"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihrer Benutzer von Skype for Business Online auf Microsoft Teams

> [!Note]
> Die in diesem Artikel beschriebenen Befehle sind für die Verwendung als Teil der [Checkliste "Upgrade Basic"](https://aka.ms/UpgradeBasic) gedacht.

Die technischen Migrationsaspekte Ihres Upgrades führen dazu, dass Ihre Benutzer benachrichtigt werden, dass Skype for Business ein Upgrade auf Teams durchführen wird, und sie dann in den Modus **"Nur Teams"** verschieben. Diese Schritte können über eine Skype for Business-Remote-Windows PowerShell oder über das Microsoft Teams Admin Center durchgeführt werden.

Wir führen im [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)Admin Center derzeit ein aktives Upgradetool ein, das in Kürze für Ihren Mandanten verfügbar sein sollte. Sobald es verfügbar ist, finden Sie Informationen zum Migrieren ihrer Benutzer unter "Festlegen der [Koexistenz- und Upgradeeinstellungen".](https://aka.ms/SkypeToTeams-SetCoexistence)

Wenn Sie zum heutigen Upgrade bereit sind, können Sie die in der folgenden Tabelle aufgeführten [PowerShell-Befehle](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) verwenden.

| Grundlegendes Upgrade (Schritt) # | Modus | Befehl 'PowerShell' |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Benachrichtigen des Skype for Business-Benutzers<br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit im **Islands-Modus** befinden (Standard)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(Beispiel: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Nur Skype for Business + Benachrichtigen des Skype for Business-Benutzers <br>(Verwenden Sie diesen Befehl, wenn sich Benutzer derzeit nur im **Skype for Business-Modus** befinden.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Nur Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
