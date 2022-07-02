---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Erfahren Sie mehr über die Teams-Clientumgebung und die Konformität mit Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605834"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

<a name="about-upgrade-basic"></a>

Der Zweck der Skype for Business Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht darin, Endbenutzern eine einfache, vorhersagbare Erfahrung zu bieten, wenn Organisationen von Skype for Business zu Teams wechseln.  Für eine Organisation, die zu Teams wechselt, ist der Modus " **Nur Teams** " das endgültige Ziel für jeden Benutzer, obwohl nicht allen Benutzern gleichzeitig **Nur Teams** (oder ein anderer Modus) zugewiesen werden muss.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen jeden der Skype for Business Koexistenzmodi verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern zu gewährleisten, die **nur Teams** sind, und denen, die noch nicht vorhanden sind. 

Wenn sich ein Benutzer in einem der Skype for Business Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business Client des Benutzers weitergeleitet. Um Verwirrung bei Endbenutzern zu vermeiden und das ordnungsgemäße Routing sicherzustellen, ist die Anruf- und Chatfunktion im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business Modi befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden, und explizit aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Da Anwesenheit ein Hinweis auf die Erreichbarkeit durch Chat und Anruf ist, wird bei deaktivierter Chat- und Anruffunktion auch die Selbstpräsenz in Teams (d. h. die Anzeige der eigenen Anwesenheit im Teams-Client im Bild des Benutzers) ausgeblendet. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Änderungen der verfügbaren Funktionen im Teams-Client basierend auf dem Modus

Die verfügbaren Funktionen in Teams hängen vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy festgelegt. In der folgenden Tabelle ist das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Erfahrung im Teams-Client|
|---|---|
|Beliebiger Skype for Business-Modus|Anrufe, Chats und Selbstanwesende sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechungsplanung ist nicht verfügbar|
|||

Die folgenden Screenshots veranschaulichen den Unterschied zwischen dem **Modus "Nur Teams** " oder " **Inseln** " und allen anderen Modi. Beachten Sie, dass die Chat- und Anrufsymbole standardmäßig im **Modus "Nur Teams** " oder " **Inseln** " (linker Screenshot), aber nicht mit den anderen Modi (rechter Screenshot) verfügbar sind:

![Ein paralleler Vergleich der Teams-Modi.](media/teams-mode-comparison.png)

Darüber hinaus ist die Selbstpräsenz in den anderen Modi nicht verfügbar, wie hier gezeigt.

![Screenshot der Selbstpräsenz in "Besprechungen zuerst".](media/meetings-first-no-self-presence-general.png)
 
**Hinweis:**
 <sup>1</sup> Zu diesem Zeitpunkt verhalten sich SfBwithTeamsCollab und SfBOnly gleich, aber die Absicht ist, dass der SfBOnly-Modus auch die Funktionen Kanäle und Dateien in Teams deaktiviert. In der Zwischenzeit können Kanäle mithilfe der App-Berechtigungsrichtlinie ausgeblendet werden.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkungen des Modus auf andere Richtlinieneinstellungen
Wie oben beschrieben, wirkt sich der Koexistenzmodus eines Benutzers darauf aus, welche Funktionalität im Teams-Client des Benutzers verfügbar ist. Dies bedeutet, dass der Wert des Modus je nach Modus Vorrang vor dem Wert anderer Richtlinieneinstellungen haben kann. Insbesondere wirkt sich der Koexistenzmodus darauf aus, ob die folgenden Richtlinieneinstellungen berücksichtigt werden:

|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechungsplanung|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen diese Richtlinieneinstellungen *nicht* explizit festlegen, wenn sie den Koexistenzmodus verwenden, aber es ist wichtig zu wissen, dass sich diese Einstellungen für einen bestimmten Modus wie folgt verhalten. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Inseln|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Bei Verwendung von PowerShell überprüft das `Grant-CsTeamsUpgradePolicy` Cmdlet die Konfiguration der entsprechenden Einstellungen in "TeamsMessagingPolicy", "TeamsCallingPolicy" und "TeamsMeetingPolicy", um zu ermitteln, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt würden, und wenn ja, wird in PowerShell eine Informationsnachricht bereitgestellt.  Wie oben erwähnt, ist es nicht mehr erforderlich, diese anderen Richtlinieneinstellungen festzulegen. Im Folgenden sehen Sie ein Beispiel dafür, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md)