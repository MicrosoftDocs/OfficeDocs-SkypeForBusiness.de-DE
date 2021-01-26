---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Erfahren Sie mehr über die Clienterfahrung von Teams und die Konformität mit koexistenten Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821025"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

<a name="about-upgrade-basic"></a>

Der Zweck der Koexistenzmodi von Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht in der Bereitstellung einer einfachen, vorhersagbaren Erfahrung für Endbenutzer, wenn Organisationen von Skype for Business zu Teams wechseln.  Für eine Organisation, die zu Teams wechselt, ist der **Nur-Teams-Modus** das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern gleichzeitig nur **Teams** (oder ein anderer Modus) zugewiesen werden muss.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern sicherzustellen, die nur **Teams** sind, und solchen, die es noch nicht sind. 

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden die Anruf- und Chatfunktionen im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer in den Modi SfBOnly oder SfBWithTeamsCollab befinden, und explizit aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Da die Anwesenheit einen Hinweis auf die Erreichbarkeit durch Chat und Anrufe gibt, wenn Chats und Anrufe deaktiviert sind, wird auch die Selbstpräsenz in Teams (d. h. die Anzeige der eigenen Anwesenheit im Teams-Client im Bild des Benutzers) ausgeblendet. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Wie sich die verfügbare Funktionalität im Teamclient je nach Modus ändert

Die in Teams verfügbaren Funktionen hängen vom Koexistenzmodus des Benutzers ab, der von TeamsUpgradePolicy festgelegt wird. In der folgenden Tabelle ist das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Erfahrung im Teams-Client|
|---|---|
|Beliebiger Skype for Business-Modus|Anrufe, Chats und Die Selbstpräsenz sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechungsplanung ist nicht verfügbar|
|||

Die folgenden Screenshots veranschaulichen den Unterschied zwischen dem **Modus "Teams Nur** oder **Islands"** und allen anderen Modi. Beachten Sie, dass die Chat- und Anrufsymbole standardmäßig im **Teams Only** or **Islands-Modus** (linker Screenshot) verfügbar sind, jedoch nicht in den anderen Modi (rechtes Screenshot):

![Vergleich der Modi in Teams nebeneinander](media/teams-mode-comparison.png)

Darüber hinaus ist die Selbstpräsenz in den anderen Modi nicht verfügbar, wie hier gezeigt.

![Screenshot der Selbstpräsenz in "Besprechungen zuerst"](media/meetings-first-no-self-presence-general.png)
 
**Hinweis:** 
 <sup>1</sup> Zu diesem Zeitpunkt verhalten sich SfBwithTeamsCollab und SfBOnly gleich, der SfBOnly-Modus soll jedoch auch die Funktionen "Kanäle und Dateien" in Teams deaktivieren. In der Zwischenzeit können Kanäle mithilfe der Richtlinie für App-Berechtigungen ausgeblendet werden.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkungen des Modus auf andere Richtlinieneinstellungen
Wie oben beschrieben, wirkt sich die Koexistenzmodus eines Benutzers auf die Funktionen aus, die im Teamclient des Benutzers verfügbar sind. Dies bedeutet, dass der Wert des Modus je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann. Insbesondere wirkt sich der Koexistenzmodus darauf aus, ob die folgenden Richtlinieneinstellungen berücksichtigt werden:

|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechungsplanung|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen *diese* Richtlinieneinstellungen nicht explizit festlegen, wenn sie den Modus "Koexistenz" verwenden. Es ist jedoch wichtig zu wissen, dass sich diese Einstellungen in einem bestimmten Modus effektiv wie folgt verhalten. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Islands|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Bei Verwendung von PowerShell überprüft das Cmdlet die Konfiguration der entsprechenden Einstellungen `Grant-CsTeamsUpgradePolicy` in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt werden, und wenn ja, wird in PowerShell eine Informationsmeldung bereitgestellt.  Wie oben erwähnt, ist es nicht mehr erforderlich, diese anderen Richtlinieneinstellungen zu festlegen. Das folgende Beispiel zeigt, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




