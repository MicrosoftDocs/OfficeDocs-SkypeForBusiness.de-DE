---
title: Verwalten Teams des Übergangs zum neuen Teams Admin Center
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Erfahren Sie, wie Sie mandantenweite und Benutzereinstellungen für Teams während des Übergangs von Teams im Microsoft 365 Admin Center zum neuen Teams Admin Center verwalten.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 83066f98eac9efd22558848b8ae12a06ff1e5d5b
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235310"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Was ist das neue Microsoft Teams Admin Center?  

Die neue Admin Center-Oberfläche bietet Ihnen eine einheitliche Oberfläche für die Verwaltung von Microsoft Teams und Skype for Business. Wir stellen zusätzliche Funktionen, End-to-End-Einblicke und die Möglichkeit bereit, Teams Einstellungen auf Benutzerebene zu verwalten.

![Screenshot des Microsoft Teams Admin Center.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Einstellungen, die in das neue Microsoft Teams Admin Center migriert werden

Die folgende Tabelle enthält die Abschnitte der Microsoft Teams-Oberfläche, die migriert wurden, und veranschaulicht die Beziehung zwischen den aktuellen Einstellungen und den Richtlinien im neuen Admin-Portal.

|Abschnitt von Microsoft Teams im Microsoft 365 Admin Center  |Einstellungsname (Mandantenebene)  |Microsoft Teams Admin Center-Richtlinie   |Ebene: Mandant oder Benutzer   |
|---------|---------|---------|---------|
|Allgemein     |Organigramm in persönlichem Profil anzeigen        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Mandant       |
|Allgemein     |Verwenden Skype for Business Für Empfänger, die keine E-Mail-Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|E-Mail-Integration     |Benutzern das Senden von E-Mails an Kanäle gestatten         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|E-Mail-Integration     |Absenderliste zulassen         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Mandant         |
|Benutzerdefinierter Cloudspeicher     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|Benutzerdefinierter Cloudspeicher     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|Benutzerdefinierter Cloudspeicher     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|Benutzerdefinierter Cloudspeicher     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|Benutzerdefinierter Cloudspeicher     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Mandant         |
|Einstellungen nach Benutzer-/Lizenztyp     |Microsoft Teams für alle Benutzer aktivieren oder deaktivieren          |Veraltet <sup>1</sup>        |         |
|Teams und Kanäle     |         |Weiterleitung an die Azure Active Directory-Gruppenverwaltung (identisch mit der aktuellen Benutzeroberfläche).              |Benutzer         |
|Teams und Kanäle     |         |Weiterleitung an die AAD-Gruppenverwaltung (identisch mit der aktuellen Benutzeroberfläche).             |Benutzer          |
|Apps|Neue externe Apps standardmäßig aktivieren|Organisationsweite App-Einstellungen|Mandant|
|Apps|Externe Apps zulassen|Organisationsweite App-Einstellungen|Mandant|
|Apps|Querladen von externen Apps zulassen<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Benutzer|
|Apps|Standard-Apps<sup>3</sup>|TeamsAppPermissionPolicy|Benutzer|
|Apps|Externe Apps<sup>3</sup>|TeamsAppPermissionPolicy|Benutzer|
|Anrufe und Besprechungen     |Zeitplanung für private Besprechungen zulassen         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Benutzer          |
|Anrufe und Besprechungen     |Ad-hoc-Kanal-Meetups zulassen         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Benutzer          |
|Anrufe und Besprechungen     |Zeitplanung für Kanalbesprechungen zulassen         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Benutzer          |
|Anrufe und Besprechungen     |Videos in Besprechungen zulassen         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Benutzer          |
|Anrufe und Besprechungen     |Bildschirmübertragung in Besprechungen zulassen         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Benutzer          |
|Anrufe und Besprechungen     |Private Anrufe zulassen         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Benutzer          |
|Messaging     |Aktivieren Von Giphy, damit Benutzer GIFs zu Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Inhaltsklassifikation         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Memes aktivieren, die Benutzer bearbeiten und Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Sticker aktivieren, die Benutzer bearbeiten und Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Besitzern das Löschen aller Nachrichten gestatten         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Benutzern das Bearbeiten ihrer eigenen Nachrichten gestatten         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Benutzers das Löschen ihrer eigenen Nachrichten gestatten         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |
|Messaging     |Benutzern privates Chatten gestatten         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Benutzer         |

<sup>1</sup> für Gastbenutzer veraltet. Das Aktivieren/Deaktivieren von Gastbenutzern kann jetzt im Microsoft Teams Admin Center verwaltet werden. Das Aktivieren/Deaktivieren von Teams für Business Enterprise, Edu Student und Edu Faculty wird in Kürze nicht mehr unterstützt. Dies sollte durch Zuweisen von Lizenzen im Microsoft 365 Admin Center verwaltet werden. Siehe [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Querladen wird wie folgt aufgeteilt:

- Zulassen, dass ein Benutzer Apps querlädt, die auf Benutzerebene in [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy) verwaltet werden können.
- Zulassen, dass Benutzer in einem Mandanten mit benutzerdefinierten Apps interagieren, die auf Mandantenebene in organisationsweiten App-Einstellungen verwaltet werden können.

<sup>3</sup> Standard-Apps und externe Apps können in "TeamsAppPermissionPolicy" auf Benutzerebene aktiviert bzw. deaktiviert werden. Darüber hinaus können Apps in organisationsweiten App-Einstellungen auf Mandantenebene blockiert werden, wodurch alle Einstellungen auf Benutzer- und Mandantenebene außer Kraft gesetzt werden.

> [!NOTE]
> Sie verwenden weiterhin das Dashboard "Gruppen" im Microsoft 365 Admin Center für die Konfiguration im Zusammenhang mit Teams Kanälen. Einstellungen für Apps verbleiben im Microsoft 365 Admin Center im Microsoft Teams-Bereich und werden später migriert.

## <a name="manage-settings-during-the-migration"></a>Verwalten von Einstellungen während der Migration

Sie können die Einstellungen weiterhin im Microsoft 365 Admin Center und im Skype for Business Admin Center ändern, bis die Migration für einen Abschnitt für Ihren Mandanten abgeschlossen ist.

Die folgende Tabelle zeigt, wo Sie die Features während der Migration verwalten können.

|Feature  |Microsoft Teams Admin Center                      |Skype for Business Admin Center (Legacy)  |Microsoft 365 Admin Center  |
|---------|:---------:|:---------:|:---------:|
|Nachrichten-, Besprechungs- und Liveereignisrichtlinien für Teams     |     X    |         |         |
|Teams-Upgraderichtlinie     |    X     |         |         |
|Gasteinstellungen für Nachrichten, Besprechungen und Sprachausgabe     |   X      |         |         |
|Teams-Lebenszyklusverwaltung   |    X    |      |       |
|Teams-Einstellungen   |    X    |      |       |
|Einstellungen für externen Zugriff     |    X    |      |       |
|Benutzerverwaltung    |         |         |    X     |
|Audiokonferenz     |    X     |    X     |         |
|Anrufpläne     |    X    |    X     |         |
|Telefonsystem    |    X    |     X    |         |
|Telefonnummernverwaltung     |    X    |   X      |         |
|Lizenzierung für Cloud Voice-Funktionen     |         |         |    X     |
|Automatische Telefonzentralen     |    X    |          |         |
|Anrufwarteschleifen     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Verwalten von Einstellungen nach der Migration

Nach Abschluss der Migration dieser Einstellungen werden sie im Microsoft 365 Admin Center und Skype for Business Admin Center deaktiviert, und sie können dann im neuen Microsoft Teams Admin Center verwaltet werden.
