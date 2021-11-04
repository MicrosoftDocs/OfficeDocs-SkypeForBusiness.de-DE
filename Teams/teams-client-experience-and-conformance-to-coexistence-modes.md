---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Erfahren Sie Teams Clienterfahrung und Konformität mit Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 92bbcc1f10088b7a010d8b715f3ab24be0aca599
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774395"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

<a name="about-upgrade-basic"></a>

Der Zweck der Skype for Business-Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht in der Bereitstellung einer einfachen, vorhersagbaren Erfahrung für Endbenutzer, wenn Organisationen von Skype for Business zu Teams.  Für eine Organisation, die zu Teams wechselt, ist der **Teams Only-Modus** das endgültige Ziel für jeden Benutzer, obwohl nicht alle Benutzer gleichzeitig Teams Nur **(oder** einem anderen Modus) zugewiesen werden müssen.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern zu gewährleisten, die nur **Teams und** denen, die es noch nicht sind. 

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Client des Skype for Business des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden die Anruf- und Chatfunktionen im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im Modi SfBOnly oder SfBWithTeamsCollab befinden, und wird explizit aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Da die Anwesenheitsanzeige einen Hinweis auf die Erreichbarkeit durch Chat und Anrufe gibt, wird die Selbstpräsenz in Teams (d. h. die Anzeige der eigenen Anwesenheit im Teams-Client im Bild des Benutzers) ebenfalls ausgeblendet. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Wie sich die im Client verfügbare Teams sich je nach Modus ändert

Die verfügbaren Funktionen in Teams vom Koexistenzmodus des Benutzers abhängig, der von TeamsUpgradePolicy festgelegt wird. In der folgenden Tabelle ist das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Benutzererfahrung im Teams Clients|
|---|---|
|Beliebiger Skype for Business modus|Anrufe, Chats und Die Selbstpräsenz sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechungsplanung ist nicht verfügbar|
|||

In den folgenden Screenshots wird der Unterschied  zwischen **dem Teams "Nur** Inseln" und allen anderen Modi veranschaulicht. Beachten Sie, dass die Chat- und Anrufsymbole im **Teams Only** or **Islands-Modus** (linker Screenshot) standardmäßig verfügbar sind, jedoch nicht mit den anderen Modi (Rechtes Screenshot):

![Ein Nebeneinandervergleich der Teams Modi.](media/teams-mode-comparison.png)

Darüber hinaus ist die Selbstpräsenz in den anderen Modi nicht verfügbar, wie hier gezeigt.

![Screenshot der Selbstpräsenz in "Besprechungen zuerst".](media/meetings-first-no-self-presence-general.png)
 
**Hinweis:** 
 <sup>1</sup> Derzeit verhalten sich SfBwithTeamsCollab und SfBOnly gleich, doch sollen im SfBOnly-Modus auch die Funktionen Kanäle und Dateien in der App Teams. In der Zwischenzeit können Kanäle mithilfe der App-Berechtigungsrichtlinie ausgeblendet werden.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkungen des Modus auf andere Richtlinieneinstellungen
Wie oben beschrieben, wirkt sich der Koexistenzmodus eines Benutzers auf die Funktionen aus, die im Client des Teams sind. Dies bedeutet, dass der Wert des Modus je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann. Insbesondere wirkt sich der Koexistenzmodus darauf aus, ob die folgenden Richtlinieneinstellungen berücksichtigt werden:

|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechungsplanung|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen *diese* Richtlinieneinstellungen nicht explizit festlegen, wenn sie den Koexistenzmodus verwenden. Es ist jedoch wichtig zu wissen, dass sich diese Einstellungen für einen bestimmten Modus effektiv wie folgt verhalten. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Islands|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Bei Verwendung von PowerShell überprüft das Cmdlet die Konfiguration der entsprechenden Einstellungen `Grant-CsTeamsUpgradePolicy` in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt werden, und wenn ja, wird in PowerShell eine Informationsmeldung bereitgestellt.  Wie bereits erwähnt, ist es nicht mehr erforderlich, diese anderen Richtlinieneinstellungen zu festlegen. Das folgende Beispiel zeigt, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)