---
title: Verwalten von Teams während des Übergangs auf die neue Microsoft-Teams & Skype für Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Weitere Informationen zum Verwalten von Mandanten geltende und von Einstellungen für Teams während des Übergangs von den Teams Erfahrung in der Office 365-Verwaltungskonsole auf die neue Microsoft-Teams & Skype für Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 38706497fc83cdc5eea4cafb7177d23d55879bf0
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436628"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Verwalten von Teams während des Übergangs auf die neue Microsoft-Teams & Skype für Business Admin Center
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Was ist der neue Microsoft-Teams und Skype für Business Admin Center?  

Die neue Oberfläche von Admin Center wird Ihnen ein einheitliches Benutzererlebnis zum Verwalten von Teams und Skype für Unternehmen bereitstellen. Wir sind zusätzliche Funktionalität, Einblicke in die End-to-End- und die Möglichkeit zum Verwalten von Einstellungen für Teams auf Benutzerebene übermitteln.

![Screenshot des Microsoft-Teams & Skype für Business Admin Center.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Einstellungen migriert in der neuen Microsoft-Teams & Skype für Business-Verwaltungskonsole

Die folgende Tabelle zeigt die Abschnitte der Erfahrung Teams, die migriert wurden, und zeigt die Beziehung zwischen der aktuellen Einstellungen und Richtlinien in das neue Administratorportal.

|Abschnitt Teams in Office 365 Administrationscenter  |Name der Einstellung (Mandanten Level)  |Microsoft-Teams & Skype für Business Admin Center-Richtlinie   |Stufe: Mandanten oder Benutzer   |
|---------|---------|---------|---------|
|Allgemein     |Organisatorische Chat im persönlichen Profil anzeigen        |  [TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Mandanten       |
|Allgemein     |Verwenden Sie Skype für Unternehmen für Empfänger, die nicht über Teams verfügen         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Allgemein     |T-Bot proaktiven Hilfe Nachrichten zulassen         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|E-Mail-Integration     |Zulassen, dass Benutzer das Senden von e-Mails an Kanäle         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|E-Mail-Integration     |Absender zulassen Liste         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Feld         |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Ablage        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Google-Laufwerk        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mandanten         |
|Einstellungen nach Benutzer-/Lizenztyp     |Aktivieren Sie oder deaktivieren Sie den Microsoft-Teams für alle Benutzer          |Veraltete<sup>1</sup>        |         |
|Teams und Kanäle     |         |Umleitung zur Azure Active Directory-Gruppenmanagement (identisch mit Kenntnissen).              |Benutzer         |
|Teams und Kanäle     |         |Umleitung zur Verwaltung von AAD (identisch mit Kenntnissen).             |Benutzer          |
|Anrufe und Besprechungen     |„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Benutzer          |
|Anrufe und Besprechungen     |Ad-hoc-Kanal Meetup zulassen         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Benutzer          |
|Anrufe und Besprechungen     |„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Benutzer          |
|Anrufe und Besprechungen     |Zulassen von Videos in Besprechungen         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Benutzer          |
|Anrufe und Besprechungen     |Zulassen Sie Bildschirmfreigabe an Besprechungen         |[TeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Benutzer          |
|Anrufe und Besprechungen     |Private Anrufe zulassen         |[TeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Benutzer          |
|Messaging     |Aktivieren Sie Giphy, damit Benutzer Unterhaltungen GIF-Dateien hinzufügen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Bewerten         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Aktivieren von Memes, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Aktivieren Sie Aufkleber, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Zulassen Sie Websitebesitzer für alle Nachrichten löschen         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten bearbeiten         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten löschen         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |
|Messaging     |Ermöglicht es Benutzern, privat chat         |[TeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Benutzer         |

<sup>1</sup> Gast veraltet. Aktivieren/Deaktivieren von Gast können nun im Microsoft-Teams & Skype für Business Admin Center verwaltet werden. Aktivieren/Deaktivieren von Unternehmen, Edu Student, Teams und Edu Fakultät bald unterstützt. Dies sollte durch Zuweisen von Lizenzen im Office 365 Administrationscenter verwaltet werden. Finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft-Teams](user-access.md).

> [!NOTE]
> Sie können weiterhin das Gruppen-Dashboard im Office 365 Administrationscenter für die Konfiguration im Zusammenhang mit der Teams und Kanäle verwenden. Einstellungen für Apps bleibt im Bereich Teams von Office 365 Administrationscenter und migriert werden weiter unten. 

## <a name="manage-settings-during-the-migration"></a>Verwalten von Einstellungen für während der migration

Sie können weiterhin Ändern der Einstellungen in der Office 365-Verwaltungskonsole und der Skype für Business Administrationscenter bis Migration eines Bereichs für Ihre Mandanten abgeschlossen ist. 

Die folgende Tabelle zeigt, wo Sie Features während der Migration verwalten können.

|Funktion  |Microsoft-Teams & Skype für Business Admin Center                       |Skype für Business Administrationscenter (Legacy)  |Office 365 Administrationscenter  |
|---------|:---------:|:---------:|:---------:|
|Richtlinien für Messaging, Besprechungen und Ereignisse Live-Teams     |     X    |         |         |
|Upgrade Richtlinie Teams     |    X     |         |         |
|Gast-Einstellungen für Messaging, Besprechungen und VoIP     |   X      |         |         |
|Teams Anwendungslebenszyklus-Verwaltung   |    X    |      |       |
|Einstellungen für Teams   |    X    |      |       |
|Zugriff durch externe Einstellungen     |    X    |      |       |
|Die Verwaltung von    |         |         |    X     |    
|Audiokonferenzen     |    X     |    X     |         |
|Anrufpläne     |         |    X     |         |
|Telefonsystem    |         |     X    |         |
|Telefon Nummer management     |         |   X      |         |
|Lizenzierung für Cloud VoIP-Funktionen     |         |         |    X     |
|Automatische Telefonzentralen     |         |    X     |         |
|Anrufwarteschleifen     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Verwalten von Einstellungen nach der migration

Klicken Sie nach Abschluss die Migration der diese Einstellungen werden wir sie in Office 365 Administrationscenter und die Skype für Business Administrationscenter zu deaktivieren, und können dann in der neuen Microsoft-Teams & Skype für Business Admin Center verwaltet werden.


