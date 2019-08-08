---
title: Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Clientumgebung für Teams und comformance in Koexistenzmodus
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243905"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen

> [!NOTE]
> Auf dieser Seite werden wichtige, kürzlich veröffentlichte Änderungen des Verhaltens des Teams-Clients beschrieben, wenn sich Benutzer in einem der Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) befinden.


Der Zweck der Koexistenz-Modi ist es, eine einfache, vorhersagbare Benutzeroberfläche für Endbenutzer bereitzustellen, während Organisationen von Skype for Business zu Teams wechseln.  Für eine Organisation, die in Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger anderer Modus) zugewiesen werden muss.  Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen alle Skype for Business-Modi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern, die TeamsOnly sind, und denjenigen, die noch nicht sind, zu gewährleisten. 

Wenn sich ein Nutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet. Um die Verwirrung des Endbenutzers zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, ist die Funktion für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Terminplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Wie sich die verfügbaren Funktionen in Teams Client basierend auf dem Modus ändern
Die verfügbare Funktionalität in Microsoft Teams hängt vom Koexistenzmodus des Benutzers ab, wie von TeamsUpgradePolicy. In der folgenden Tabelle wird das Verhalten zusammengefasst:

|Effektiver Modus des Benutzers|Erfahrung im Team-Client|
|---|---|
|Skype for Business-Modus|Anrufe und Chats sind deaktiviert.|
|SfBWithTeamsCollabAndMeetings|Besprechungsplanung steht zur Verfügung|
|SfBWithTeamsCollab oder SfBOnly<sup>1</sup>|Besprechungsplanung steht nicht zur Verfügung|
|||

Die folgenden Screenshots veranschaulichen den Unterschied zwischen TeamsOnly-oder Islands-Modus und allen anderen Modi. Beachten Sie, dass die Chat-und Anruf Symbole im TeamsOnly-oder Islands-Modus (linker Screenshot) zur Verfügung stehen, aber nicht bei den anderen Modi (rechter Screenshot):

![Ein nebeneinander angeordneter Vergleich der Modi "Teams"](media/teams-mode-comparison.png)


 
**Hinweis:**
<sup>1</sup> im Moment Verhalten sich SfBwithTeamsCollab und SfBOnly identisch, aber die Absicht ist, dass der SfBOnly-Modus auch die Kanäle und Dateien in Teams deaktiviert. Es gibt jedoch derzeit keine Einstellung, mit der diese Funktion in Teams deaktiviert werden kann.


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

Bei Verwendung von PowerShell überprüft `Grant-CsTeamsUpgradePolicy` das Cmdlet die Konfiguration der entsprechenden Einstellungen in TeamsMessagingPolicy, TeamsCallingPolicy und TeamsMeetingPolicy, um festzustellen, ob diese Einstellungen von TeamsUpgradePolicy übergegangen werden, und wenn dies der Fall ist, wird eine eine Informationsmeldung wird in PowerShell bereitgestellt.  Wie bereits erwähnt, ist es nicht mehr notwendig, diese anderen Richtlinieneinstellungen festzulegen. Nachfolgend finden Sie ein Beispiel dafür, wie die PowerShell-Warnung aussieht:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Verwandte Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




