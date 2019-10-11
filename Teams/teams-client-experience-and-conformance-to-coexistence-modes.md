---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e05a95871dbe36f969c048f32d9bca99fec5d45
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435239"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen


Der Zweck der Koexistenz-Modi von Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht darin, den Endbenutzern eine einfache, vorhersagbare Erfahrung zu bieten, wenn Organisationen von Skype for Business zu Teams wechseln.  Für eine Organisation, die in Teams wechselt, ist der Modus **nur für Teams** das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig **nur Teams** (oder ein beliebiger anderer Modus) zugewiesen werden müssen.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Koexistenzmodus verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die **nur Teams** sind und die noch nicht sind. 

Wenn sich ein Nutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet. Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, ist die Funktion für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Terminplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Da Anwesenheitsinformationen durch Chats und Anrufe eine Erreichbarkeit darstellen, wenn Chats und Anrufe deaktiviert sind, ist die selbst Anwesenheit in Teams (also die Anzeige der eigenen Anwesenheit im Team-Client im Bild des Benutzers) ebenfalls verborgen. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Wie sich die verfügbaren Funktionen in Teams Client basierend auf dem Modus ändern

Die verfügbare Funktionalität in Microsoft Teams hängt vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy. In der folgenden Tabelle wird das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Erfahrung im Team-Client|
|---|---|
|Skype for Business-Modus|Anrufe, Chats und selbst Anwesenheit sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung steht zur Verfügung|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechungsplanung steht nicht zur Verfügung|
|||

Die folgenden Screenshots veranschaulichen den Unterschied zwischen dem **nur für Teams** oder dem **Inseln** -Modus und allen anderen Modi. Beachten Sie, dass die Symbole für Chats und Anrufe standardmäßig im Modus " **nur für Teams** " oder " **Inseln** " verfügbar sind (Screenshot Links), aber nicht mit den anderen Modi (rechter Screenshot):

![Ein nebeneinander angeordneter Vergleich der Modi "Teams"](media/teams-mode-comparison.png)

Darüber hinaus steht die selbst Anwesenheit in den anderen Modi nicht zur Verfügung, wie hier gezeigt.

![Screenshot der selbst Anwesenheit in Besprechungen zuerst](media/meetings-first-no-self-presence-general.png)
 
**Hinweis:**
<sup>1</sup> zu diesem Zeitpunkt Verhalten sich SfBwithTeamsCollab und SfBOnly identisch, aber die Absicht ist, dass der SfBOnly-Modus auch Kanäle und Dateien in Teams deaktiviert. In der Zwischenzeit können Kanäle mithilfe der APP-Berechtigungsrichtlinie ausgeblendet werden.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkungen des Modus auf andere Richtlinieneinstellungen
Wie oben beschrieben, hat der Koexistenzmodus des Benutzers Auswirkungen auf die Funktionalität, die im Team Client des Benutzers zur Verfügung steht. Dies bedeutet, dass der Wert von Mode je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann. Insbesondere beeinflusst der Koexistenzmodus, ob die folgenden Richtlinieneinstellungen beachtet werden:

|**Modalität (app)**|**Richtlinie. Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechungsplanung|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen diese Richtlinieneinstellungen *nicht* explizit festlegen, wenn Sie den Koexistenzmodus verwenden, doch es ist wichtig zu wissen, dass sich diese Einstellungen für einen bestimmten Modus wie folgt Verhalten. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder-Inseln|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Bei Verwendung von PowerShell überprüft `Grant-CsTeamsUpgradePolicy` das Cmdlet die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt würden, und wenn dies der Fall ist, wird eine eine Informationsmeldung wird in PowerShell bereitgestellt.  Wie bereits erwähnt, ist es nicht mehr notwendig, diese anderen Richtlinieneinstellungen festzulegen. Im folgenden sehen Sie ein Beispiel dafür, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




