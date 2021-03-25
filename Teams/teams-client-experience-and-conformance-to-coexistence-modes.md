---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Erfahren Sie mehr über die Benutzererfahrung von Teams und die Konformität mit Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119254"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

<a name="about-upgrade-basic"></a>

Der Zweck der Skype for Business-Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht in der Bereitstellung einer einfachen, vorhersagbaren Benutzererfahrung, während Organisationen von Skype for Business zu Teams wechseln.  Für eine Organisation, die zu Teams wechselt, ist der **Modus "Teams** nur" das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern teams only **(oder** einem anderen Modus) gleichzeitig zugewiesen werden muss.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die nur **Teams** sind, und personen, die noch nicht sind. 

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers geroutet. Um Verwirrung zwischen Endbenutzern zu vermeiden und die ordnungsgemäße Weiterleitung sicherzustellen, werden die Funktionen für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Da Anwesenheit ein Hinweis auf die Erreichbarkeit durch Chats und Anrufe ist, wenn Chats und Anrufe deaktiviert sind, ist die Selbstpräsenz in Teams (d. h. die Anzeige der eigenen Anwesenheit im Teams-Client im Bild des Benutzers) ebenfalls ausgeblendet. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Ändern der verfügbaren Funktionen im Teams-Client basierend auf dem Modus

Die in Teams verfügbaren Funktionen hängen vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy festgelegt. In der folgenden Tabelle ist das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Erfahrung im Teams-Client|
|---|---|
|Beliebiger Skype for Business-Modus|Anrufe, Chats und Selbstpräsenz sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Die Besprechungsplanung ist nicht verfügbar|
|||

Die folgenden Screenshots veranschaulichen den Unterschied zwischen **dem Modus "Teams only"** oder **"Islands"** und allen anderen Modi. Beachten Sie, dass die Chat- und Anrufsymbole standardmäßig im **Modus "Teams Only"** oder **"Islands"** (linker Screenshot) verfügbar sind, jedoch nicht mit den anderen Modi (screenshot rechts):

![Vergleich von Teams-Modi nebeneinander](media/teams-mode-comparison.png)

Darüber hinaus ist die Selbstpräsenz in den anderen Modi nicht verfügbar, wie hier gezeigt.

![Screenshot der Selbstpräsenz in "Besprechungen zuerst"](media/meetings-first-no-self-presence-general.png)
 
**Hinweis:** 
 <sup>1</sup> Zu diesem Zeitpunkt verhalten sich SfBwithTeamsCollab und SfBOnly gleich. Die Absicht besteht jedoch im SfBOnly-Modus, die Funktionen "Kanäle und Dateien" in Teams ebenfalls zu deaktivieren. In der Zwischenzeit können Kanäle mithilfe der App-Berechtigungsrichtlinie ausgeblendet werden.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkungen des Modus auf andere Richtlinieneinstellungen
Wie oben beschrieben, wirkt sich der Koexistenzmodus eines Benutzers auf die Funktionen aus, die im Teams-Client des Benutzers verfügbar sind. Dies bedeutet, dass der Wert des Modus je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann. Insbesondere wirkt sich der Koexistenzmodus darauf aus, ob die folgenden Richtlinieneinstellungen berücksichtigt werden:

|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechungsplanung|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen *diese* Richtlinieneinstellungen nicht explizit festlegen, wenn sie den Koexistenzmodus verwenden. Es ist jedoch wichtig zu verstehen, dass sich diese Einstellungen für einen bestimmten Modus effektiv wie folgt verhalten. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Islands|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Bei Verwendung von PowerShell überprüft das Cmdlet die Konfiguration der entsprechenden Einstellungen `Grant-CsTeamsUpgradePolicy` in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt werden, und wenn ja, wird in PowerShell eine Informationsmeldung bereitgestellt.  Wie oben erwähnt, ist das Festlegen dieser anderen Richtlinieneinstellungen nicht mehr erforderlich. Das folgende Beispiel zeigt, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)