---
title: Verwalten von Teams während des Übergangs auf die neuen Microsoft-Teams und Skype für Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Weitere Informationen zum Verwalten von Mandanten geltende und von Einstellungen für Teams während des Übergangs von den Teams Erfahrung in der Office 365-Verwaltungskonsole auf die neue Microsoft-Teams & Skype für Business Admin Center.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0f660130ce9fe2973178385e87433cac29fa8733
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>Verwalten von Teams während des Übergangs auf die neuen Microsoft-Teams und Skype für Business Admin Center
======================================================

Das neue Admin Center für Microsoft Teams und Skype for Business ist in Kürze verfügbar! 

Starten im März 2018, wir sind schrittweise Einstellungen auf die Microsoft-Teams & Skype für Business Admin Center migrieren, aus sowohl der aktuelle Skype für Business Admin Center und die Microsoft-Teams Erfahrung in der Office 365-Verwaltungskonsole. Wenn eine Einstellung migriert wurde, sehen Sie eine Benachrichtigung und werden zu der entsprechenden Stelle im neuen Admin Center für Microsoft Teams und Skype for Business geleitet.

Wir uns weiterhin andere Funktionen von der Skype für Business Admin Center in den nächsten Monaten zu migrieren. Sie können über unsere öffentliche [Roadmap](https://aka.ms/Office365Roadmap)Stand bleiben.

> [!NOTE]
> Wir sind in Phasen müssen Sie die neue Microsoft-Teams & Skype für Business Admin Center parallelen. Alle Kunden werden daher nicht das neue Admin Center zur selben Zeit angezeigt. Wir werden Sie benachrichtigen, wenn Sie mit dem neuen Admin Center starten können.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>Was ist der neue Microsoft-Teams und Skype für Business Admin Center?  

Die neue Oberfläche Admin Center wird Ihnen ein einheitliches Benutzererlebnis zum Verwalten von Teams und Skype für Unternehmen bereitstellen. Wir sind zusätzliche Funktionalität, Einblicke in die End-to-End- und die Möglichkeit zum Verwalten von Einstellungen für Teams auf Benutzerebene übermitteln.

![Screenshot des Microsoft-Teams & Skype für Business Admin Center.](media/manage-teams-skype-for-business-admin-center-portal.png)


Starten in der Mitte März 2018, werden die folgenden Funktionen in der neuen Microsoft-Teams & Skype für Business Admin Center verfügbar sein: 

- **Microsoft-Teams, messaging-Richtlinie**: Erstellen der Richtlinie für die Verwaltung auf Benutzerebene, die Erfahrung in der Microsoft-Teams, Client für Messaging Szenarien.
- **Interop-Richtlinie von Microsoft-Teams**: konfigurieren die Erfahrung Interoperabilität zwischen Skype für Unternehmen und die Microsoft-Teams.
- **Microsoft-Teams Gast messaging-Einstellungen**: steuern die messaging-Funktionen für Gastkonten in Microsoft-Teams. 
- **Verbundeinstellungen**: den Verbund zwischen Mandanten für Microsoft-Teams und Skype für Unternehmen zu verwalten. 
- **Die Verwaltung von**: Zuweisen von Richtlinien und Konfigurieren von Benutzerkonten. 
- **Audiokonferenzen**: Konfigurieren von Einwahlnummern und Einstellungen für Skype für Geschäfts- und Microsoft-Teams. 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Einstellungen migriert in der neuen Microsoft-Teams & Skype für Business-Verwaltungskonsole

Die vorhandenen Einstellungen für allgemeine, e-Mail-Integration, benutzerdefinierte cloudspeicher, Anrufe und Besprechungen und Messaging in Microsoft-Teams werden (siehe Abbildung unten) in der neuen Microsoft-Teams & Skype für Business Admin Center (auch bekannt als das neue Portal Admin) migriert in den nächsten Monaten. 



> [!NOTE]
>Sie können weiterhin das Gruppen-Dashboard im Office 365 Admin Center für die Konfiguration im Zusammenhang mit der **Teams und Kanäle**verwenden. Einstellungen für **Apps** bleibt im Bereich Teams von Office 365 Admin Center und migriert werden weiter unten. 

![Screenshot des Teams Seite im Office 365 Admin Center.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

Im Hinblick auf die Einstellungen in den **Einstellungen durch Benutzer/Lizenztyp**verfügbar sofern diese im Wesentlichen eine Möglichkeit zum Konfigurieren von Benutzergruppen unterschiedlich. Nun, mit dem neuen Admin-Portal, die für jeden Benutzer einzeln möglich. 


Festlegen der Lizenztyp werden migriert. Wenn Sie die Einstellung **Aktivieren Microsoft-Teams, aktiviert oder deaktiviert für alle Benutzer dieses Typs** zum Steuern des Zugriffs auf die Teams für Benutzer über SKUs derzeit verwenden, werden wir Ihre aktuellen Konfigurationen verwalten. Jedoch, Sie kann nicht zum Ändern dieser Einstellung in der neuen Verwaltungsportals werden. Stattdessen können Sie die entsprechenden Lizenzen Benutzern in Ihrem Mandanten über das Office 365 Administrationscenter zuweisen. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft-Teams](user-access.md). 

Die folgende Tabelle zeigt die Abschnitte des Teams Kenntnissen, die migriert werden, und zeigt die Beziehung zwischen der aktuellen Einstellungen und Richtlinien in das neue Admin-Portal.


|Abschnitt Teams in Office 365 Admin center  |Name der Einstellung (Mandanten Level)  |Microsoft-Teams & Skype für Business Admin Center-Richtlinie   |Stufe: Mandanten oder Benutzer   |
|---------|---------|---------|---------|
|Allgemein     |Organisatorische Chat im persönlichen Profil anzeigen        |  TeamsClientConfiguration       |  Mandanten       |
|Allgemein     |Verwenden Sie Skype für Unternehmen für Empfänger, die nicht über Teams verfügen         |TeamsClientConfiguration         |Mandanten         |
|Allgemein     |T-Bot proaktiven Hilfe Nachrichten zulassen         |TeamsClientConfiguration         |Mandanten         |
|E-Mail-Integration     |Zulassen, dass Benutzer das Senden von e-Mails an Kanäle         |TeamsClientConfiguration         |Mandanten         |
|E-Mail-Integration     |Absender zulassen Liste         |TeamsClientConfiguration        |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Feld         |TeamsClientConfiguration         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Ablage        |TeamsClientConfiguration         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |Google-Laufwerk        |TeamsClientConfiguration         |Mandanten         |
|Benutzerdefinierter Cloudspeicher     |ShareFile        |TeamsClientConfiguration         |Mandanten         |
|Geben Sie die Einstellungen von User-Lizenz     |Aktivieren Sie oder deaktivieren Sie den Microsoft-Teams für alle Benutzer          |Veraltet. Verwenden Sie Office 365 Administrationscenter, Lizenzen zuzuweisen.        |         |
|Teams und Kanäle     |         |Umleitung zur Azure Active Directory-Gruppenmanagement (identisch mit Kenntnissen).              |Benutzer         |
|Teams und Kanäle     |         |Umleitung zur Verwaltung von AAD (identisch mit Kenntnissen).             |Benutzer          |
|Anrufe und Besprechungen     |„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen)         |TeamsMeetingPolicy         |Benutzer          |
|Anrufe und Besprechungen     |Ad-hoc-Kanal Meetup zulassen         |TeamsMeetingPolicy         |Benutzer          |
|Anrufe und Besprechungen     |„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen)         |TeamsMeetingPolicy         |Benutzer          |
|Anrufe und Besprechungen     |Zulassen von Videos in Besprechungen         |TeamsMeetingPolicy         |Benutzer          |
|Anrufe und Besprechungen     |Zulassen Sie Bildschirmfreigabe an Besprechungen         |TeamsMeetingPolicy         |Benutzer          |
|Anrufe und Besprechungen     |Private Anrufe zulassen         |TeamsCallingPolicy         |Benutzer          |
|Messaging     |Aktivieren Sie Giphy, damit Benutzer Unterhaltungen GIF-Dateien hinzufügen können         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Bewerten         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Aktivieren von Memes, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Aktivieren Sie Aufkleber, die Benutzer Unterhaltungen hinzufügen und bearbeiten können         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Zulassen Sie Websitebesitzer für alle Nachrichten löschen         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten bearbeiten         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Zulassen, dass Benutzer ihre eigenen Nachrichten löschen         |TeamsMessagingPolicy         |Benutzer         |
|Messaging     |Ermöglicht es Benutzern, privat chat         |TeamsMessagingPolicy         |Benutzer         |



## <a name="manage-settings-during-the-migration"></a>Verwalten von Einstellungen für während der migration

Wir planen der Migration von Teams Einstellungen in den Abschnitten in der folgenden Reihenfolge: Messaging, Besprechungen, Anrufe und schließlich die Abschnitte innerhalb der Richtlinie TeamsClient Konfiguration (Allgemein, E-Mail-Integration und benutzerdefinierte cloudspeicher).   

Sie können weiterhin Ändern der Einstellungen in der Office 365-Verwaltungskonsole und der Skype für Business Admin Center bis Migration eines Bereichs für Ihre Mandanten abgeschlossen ist. 

Die folgende Tabelle zeigt, wo Sie Features während der Migration verwalten können.

|Funktion  |Microsoft-Teams und Skype für Business Admin Center                       |Skype für Business Admin Center (Legacy)  |Office 365 Administrationscenter  |
|---------|:---------:|:---------:|:---------:|
|Für Messagingrichtlinien     |     X    |         |         |
|Teams Interop-Richtlinie     |    X     |         |         |
|Gast für Textnachrichten     |   X      |         |         |
|Zugriff durch externe Einstellungen    |    X     |         |         |
|Die Verwaltung von    |         |         |    X     |    
|Audiokonferenzen     |    X     |    X     |         |
|Anrufpläne     |         |    X     |         |
|Telefonsystem    |         |     X    |         |
|Telefon Nummer management     |         |   X      |         |
|Lizenzierung für Cloud VoIP-Funktionen     |         |         |    X     |
|Automatische Telefonzentralen     |         |    X     |         |
|Anrufwarteschleifen     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Verwalten von Einstellungen nach der migration

Wir werden Sie benachrichtigen, nach der Migration für einen bestimmten Bereich innerhalb Teams abgeschlossen ist. Zu diesem Zeitpunkt können auf Ihre vorhandenen Einstellungen für diesen Abschnitt im Office 365 Admin Center finden Sie unter, aber nicht möglich, stellen Sie alle Änderungen vorhanden. In diesem Fall verwenden Sie zum Verwalten der neu migrierten Einstellungen der Microsoft-Teams & Skype für Business Admin Center.

Klicken Sie nach Abschluss die Migration der diese Einstellungen werden wir sie in der Office 365-Verwaltungskonsole und der Skype für Business Admin Center zu deaktivieren.


