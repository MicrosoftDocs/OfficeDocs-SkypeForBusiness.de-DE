---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Clientumgebung Teams und ASP.NET-Features, Koexistenz Modi
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91a67c7fb9afb5633494815129d141d5a08708d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930342"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

> [!NOTE]
> Auf dieser Seite werden wichtige, kürzlich veröffentlichte Änderungen in das Verhalten des Teams-Clients beschrieben, wenn Benutzer in einer der der Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) sind.


Der Zweck der Koexistenz Modi darin eine einfache und vorhersehbare Erfahrung für Endbenutzer als Organisationen Übergang von Skype für Business Teams bereitzustellen.  Für eine Organisation verschieben, Teams ist der TeamsOnly-Modus der endgültigen Ziel für jeden Benutzer, wenn nicht alle Benutzer sich TeamsOnly (oder einem anderen Modus) zugewiesen werden zur gleichen Zeit müssen.  Vor dem Benutzer TeamsOnly Modus erreichen können Organisationen verwenden die Skype für Business Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), um sicherzustellen, dass vorhersehbare Kommunikation zwischen Benutzern, die TeamsOnly sind und Personen, die noch nicht. 

Wenn ein Benutzer in einer der der Skype für Business Modi ist, werden alle eingehenden Chats und Anrufe an Skype für Business-Client des Benutzers weitergeleitet. Endbenutzer Verwechslungen und die Sicherstellung ordnungsgemäßes routing, ist Anruf- und Chat Funktionalität in der Teams-Client deaktiviert, wenn ein Benutzer in einer der der Skype für Business Modi ist. In ähnlicher Weise ist Besprechung planen in Teams explizit deaktiviert, wenn Benutzer in den SfBOnly oder SfBWithTeamsCollab Modi sind und explizit aktiviert, wenn ein Benutzer in den Modus SfBWithTeamsCollabAndMeetings ist.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Die verfügbare Funktionalität in Teams Client wie ändert basierend auf Modus
Die verfügbare Funktionalität in Teams hängt die Benutzermodus Koexistenz von TeamsUpgradePolicy festgelegt wurde. In der folgenden Tabelle wird das Verhalten zusammengefasst:

|Eine effektive Benutzermodus|Erleben Sie die Teams-Client|
|---|---|
|Skype für Business-Modus|Anruf- und Chat sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechung planen, ist verfügbar|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechung planen ist nicht verfügbar|
|||

Die folgenden Screenshots sehen Sie den Unterschied zwischen TeamsOnly oder Inseln-Modus und alle anderen Modi. Beachten Sie, dass die Symbole Chat und Aufrufen von TeamsOnly oder Inseln-Modus (links Screenshot), aber nicht mit den anderen Modi (rechts Screenshot) zur Verfügung stehen:

![Zeigt Teams Modus Vergleiche](media/teams-mode-comparison.png)


 
**Hinweis:**
<sup>1</sup> für den Moment SfBwithTeamsCollab und SfBOnly Verhalten identisch, aber die Absicht für SfBOnly Modus auch deaktivieren, Kanäle und Dateien Funktonalität Teams; Es ist derzeit keine Einstellung, die mit dieser Funktionalität in Teams deaktiviert werden kann.


## <a name="impact-of-mode-on-other-policy-settings"></a>Auswirkung von Modus auf anderen Einstellungen für die Informationsverwaltungsrichtlinie
Wie oben, eines Benutzers Koexistenz Modus Auswirkungen beschrieben ist welche Funktionalität in der Client des Benutzers Teams verfügbar. Dies bedeutet, dass der Wert der Modus Vorrang gegenüber dem Wert der anderen Richtlinieneinstellungen, je nach den Modus haben kann. Wirkt sich insbesondere auf Koexistenzmodus, ob die folgenden Richtlinieneinstellungen beachtet werden:

|**Modalität (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Anrufe|TeamsCallingPolicy.AllowPrivateCalling|
|Besprechung planen|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Administratoren müssen *nicht* mit diesen Richtlinien explizit festlegen, wenn mit Koexistenz Modus, aber es wichtig ist zu verstehen, dass diese Einstellungen wie folgt effektiv für einen bestimmten Modus verhält. 

|Modus|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly oder Inseln|Aktiviert|Aktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollabAndMeetings|Deaktiviert|Deaktiviert|Aktiviert|Aktiviert|
|SfBWithTeamsCollab oder SfBOnly|Deaktiviert|Deaktiviert|Deaktiviert|Deaktiviert|
||||||

Beim Verwenden von PowerShell, die `Grant-CsTeamsUpgradePolicy` Cmdlet überprüft die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen durch TeamsUpgradePolicy ersetzt werden würde und ein Meldung wird in PowerShell bereitgestellt.  Wie bereits erwähnt, ist nicht mehr erforderlich, diese anderen Richtlinieneinstellungen festzulegen. Es folgt ein Beispiel für welche die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




