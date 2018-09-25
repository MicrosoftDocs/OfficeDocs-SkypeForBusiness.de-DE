---
title: Aktualisieren Sie grundlegende PowerShell-Befehlen - Microsoft-Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Stetig für das Upgrade auf Teams, falls noch nicht im Admin Center in Ihrem Mandanten eingeschaltet
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c46f0718bd0bcf0d18cc47d2f8fc68f0ae7792e7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012281"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Aktualisieren Ihre Benutzer von Skype für Business Online auf Microsoft-Teams

> [!Note]
> Die Befehle, die in diesem Artikel beschriebenen werden im Rahmen der [Einfachen Upgrade](https://aka.ms/UpgradeBasic) Prüfliste verwendet werden soll.

Die Migration technische Aspekte des Upgrades unterstützen könnte benachrichtigen der Benutzer, dass Skype für Unternehmen durchführen eines auf Teams Upgrades und anschließendes auf einen Modus **nur Teams verschieben** . Diese Schritte können über einen Skype für Business remote Windows PowerShell-Sitzung oder über die Microsoft-Teams & Skype für Business-Verwaltungskonsole ausgeführt werden. 
 
Wir sind aktiv Rollout Upgrade Tools für [Microsoft-Teams & Skype für Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), und es sollte bei Ihrem Mandanten bald verfügbar sein. Sobald sie verfügbar ist, finden Sie Informationen zur Migration von Benutzern in [Ihrer Koexistenz festlegen und Einstellungen zu aktualisieren](https://aka.ms/SkypeToTeams-SetCoexistence). 
 
Wenn Sie noch heute Upgrade bereit sind, können Sie die [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) -Befehle in der folgenden Tabelle aufgeführt. 
 
 |Grundlegende-Upgrade – Schritt # | Modus | PowerShell-Befehl |
|-------|--------|------|
| [5](upgrade-basic.md#step-5) |Inseln + benachrichtigen der Skype für Geschäftsbenutzer<br>(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit **Inseln** Modus (Standard) werden) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>_(beispielsweise $SipAddress = "TestUser@contoso.com")_<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5)  | Skype für Unternehmen nur + benachrichtigen der Skype für Geschäftsbenutzer <br>(Verwenden Sie diesen Befehl aus, wenn Benutzer derzeit im Modus **für Unternehmen nur Skype** sind) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Nur Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


