---
title: Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Weitere Informationen zum Verwalten von Mandanten geltende und von Einstellungen für Teams während des Übergangs von den Teams Erfahrung in der Office 365-Verwaltungskonsole zur neuen Microsoft-Teams-Verwaltungskonsole.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 9f1adb47709d3e053bb2349d8a3e548bedc58d9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199567"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Was ist der neue Microsoft-Teams-Verwaltungskonsole?  

Die neue Oberfläche von Admin Center wird Ihnen ein einheitliches Benutzererlebnis zum Verwalten von Teams und Skype für Unternehmen bereitstellen. Wir sind zusätzliche Funktionalität, Einblicke in die End-to-End- und die Möglichkeit zum Verwalten von Einstellungen für Teams auf Benutzerebene übermitteln.

![Screenshot des Teams für Microsoft-Verwaltungskonsole.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Einstellungen migriert in der neuen Microsoft-Teams-Verwaltungskonsole

Die folgende Tabelle zeigt die Abschnitte der Erfahrung Teams, die migriert wurden, und zeigt die Beziehung zwischen der aktuellen Einstellungen und Richtlinien in das neue Administratorportal.

|Abschnitt Teams in Office 365 Administrationscenter  |Name der Einstellung (Mandanten Level)  |Microsoft-Teams, Admin Center-Richtlinie   |Stufe: Mandanten oder Benutzer   |
|---------|---------|---------|---------|
|Allgemein     |Organisatorische Chat im persönlichen Profil anzeigen        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Mandanten       |
|Allgemein     |Verwenden Sie Skype für Unternehmen für Empfänger, die nicht über Teams verfügen         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|E-Mail-Integration     |Zulassen, dass Benutzer das Senden von e-Mails an Kanäle         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|E-Mail-Integration     |Absender zulassen Liste         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Feld         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Ablage        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Google-Laufwerk        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Einstellungen nach Benutzer-/Lizenztyp     |Aktivieren Sie oder deaktivieren Sie den Microsoft-Teams für alle Benutzer          |Veraltete<sup>1</sup>        |         |
|Teams und Kanäle     |         |Umleitung zur Azure Active Directory-Gruppenmanagement (identisch mit Kenntnissen).              |User         |
|Teams und Kanäle     |         |Umleitung zur Verwaltung von AAD (identisch mit Kenntnissen).             |User          |
|Apps|Standardmäßiges Aktivieren von neuen externen Apps|Org geltende app-Einstellungen|Mandanten|
|Apps|Externe apps zulassen|Org geltende app-Einstellungen|Mandanten|
|Apps|Zulassen von externen App-<sup>2</sup> sideloading|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|User|
|Apps|Standard-apps<sup>3</sup>|TeamsAppPermissionPolicy|User|
|Apps|Externe apps<sup>3</sup>|TeamsAppPermissionPolicy|User|
|Anrufe und Besprechungen     |„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Ad-hoc-Kanal Meetup zulassen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Zulassen von Videos in Besprechungen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Zulassen Sie Bildschirmfreigabe an Besprechungen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Private Anrufe zulassen         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |User          |
|Messaging     |Aktivieren Sie Giphy, damit Benutzer Unterhaltungen GIF-Dateien hinzufügen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Bewerten         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Aktivieren von Memes, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Aktivieren Sie Aufkleber, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen Sie Websitebesitzer für alle Nachrichten löschen         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten bearbeiten         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten löschen         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Ermöglicht es Benutzern, privat chat         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |

<sup>1</sup> Gast veraltet. Aktivieren/Deaktivieren von Gast können jetzt in der Verwaltungskonsole von Microsoft-Teams verwaltet werden. Aktivieren/Deaktivieren von Unternehmen, Edu Student, Teams und Edu Fakultät bald unterstützt. Dies sollte durch Zuweisen von Lizenzen im Office 365 Administrationscenter verwaltet werden. Finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft-Teams](user-access.md).
<br><br>
<sup>2</sup> Sideloading ist wie folgt aufgeteilt:

- Kann einen Benutzer Sideload-apps, die auf der Benutzerebene in [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)verwaltet werden können.
- Ermöglicht es Benutzern in einem Mandanten Interaktion mit benutzerdefinierten apps, die auf einer Ebene Mandanten in Org geltende app-Einstellungen verwaltet werden können.
 
<sup>3</sup> Standard-apps und externe apps können aktiviert und deaktiviert werden auf Benutzerebene in TeamsAppPermissionPolicy. Darüber hinaus können apps Ebene der Mandant Org geltende app-Einstellungen blockiert werden, die alle Benutzer und Einstellungen auf Mandantenebene überschrieben wird. 

> [!NOTE]
> Sie können weiterhin das Gruppen-Dashboard im Office 365 Administrationscenter für die Konfiguration im Zusammenhang mit der Teams und Kanäle verwenden. Einstellungen für Apps bleibt im Bereich Teams von Office 365 Administrationscenter und migriert werden weiter unten. 

## <a name="manage-settings-during-the-migration"></a>Verwalten von Einstellungen für während der migration

Sie können weiterhin Ändern der Einstellungen in der Office 365-Verwaltungskonsole und der Skype für Business Administrationscenter bis Migration eines Bereichs für Ihre Mandanten abgeschlossen ist. 

Die folgende Tabelle zeigt, wo Sie Features während der Migration verwalten können.

|Feature  |Microsoft-Teams, Administrationscenter                      |Skype für Business Administrationscenter (Legacy)  |Office 365 Administrationscenter  |
|---------|:---------:|:---------:|:---------:|
|Richtlinien für Messaging, Besprechungen und Ereignisse Live-Teams     |     X    |         |         |
|Upgrade Richtlinie Teams     |    X     |         |         |
|Gast-Einstellungen für Messaging, Besprechungen und VoIP     |   X      |         |         |
|Teams Anwendungslebenszyklus-Verwaltung   |    X    |      |       |
|Einstellungen für Teams   |    X    |      |       |
|Zugriff durch externe Einstellungen     |    X    |      |       |
|Die Verwaltung von    |         |         |    X     |    
|Audiokonferenzen     |    X     |    X     |         |
|Aufrufen von Plänen     |         |    X     |         |
|Telefonsystem    |         |     X    |         |
|Telefon Nummer management     |         |   X      |         |
|Lizenzierung für Cloud VoIP-Funktionen     |         |         |    X     |
|Automatische Telefonzentralen     |         |    X     |         |
|Anrufwarteschleifen     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Verwalten von Einstellungen nach der migration

Klicken Sie nach Abschluss die Migration der diese Einstellungen werden wir sie in Office 365 Administrationscenter und die Skype für Business Administrationscenter zu deaktivieren, und können dann in der neuen Microsoft-Teams-Verwaltungskonsole verwaltet werden.


