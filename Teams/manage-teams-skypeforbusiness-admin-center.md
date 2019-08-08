---
title: Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Sie erfahren, wie Sie die Mandanten-und Benutzereinstellungen für Teams während des Übergangs von der Team Erfahrung im Microsoft 365 Admin Center zum neuen Microsoft Teams Admin Center verwalten.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 5369206deda7a9d4c9e17a87406f208383927f05
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232955"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Was ist das neue Microsoft Teams Admin Center?  

Die neue Administrator-Center-Erfahrung bietet Ihnen eine einheitliche Benutzeroberfläche für die Verwaltung von Teams und Skype for Business. Wir bieten zusätzliche Funktionen, End-to-End-Einblicke und die Möglichkeit, Team Einstellungen auf Benutzerebene zu verwalten.

![Screenshot des Microsoft Teams admin Centers](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Einstellungen, die zum neuen Microsoft Teams Admin Center migriert wurden

In der folgenden Tabelle werden die Abschnitte der Team Erfahrung, die migriert wurden, und die Beziehung zwischen den aktuellen Einstellungen und den Richtlinien im neuen Administratorportal aufgeführt.

|Abschnitt der Teams im Microsoft 365 Admin Center  |Einstellungsname (Mandantenebene)  |Microsoft Teams Admin Center-Richtlinie   |Ebene: Mandant oder Benutzer   |
|---------|---------|---------|---------|
|Allgemein     |Organigramm im persönlichen Profil anzeigen        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Mieter       |
|Allgemein     |Verwenden von Skype for Business für Empfänger, die keine Teams haben         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|E-Mail-Integration     |Zulassen, dass Benutzer e-Mails an Kanäle senden         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|E-Mail-Integration     |Liste der Absender zulassen         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Mieter         |
|Benutzerdefinierter Cloudspeicher     |Feld         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|Benutzerdefinierter Cloudspeicher     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|Benutzerdefinierter Cloudspeicher     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|Benutzerdefinierter Cloudspeicher     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Mieter         |
|Einstellungen nach Benutzer-/Lizenztyp     |Aktivieren oder Deaktivieren von Microsoft Teams für alle Benutzer          |Veraltet<sup>1</sup>        |         |
|Teams und Kanäle     |         |Leitet die Azure Active Directory-Gruppenverwaltung um (identisch mit der aktuellen Benutzeroberfläche).              |User         |
|Teams und Kanäle     |         |Leitet die Aad-Gruppenverwaltung um (identisch mit der aktuellen Benutzeroberfläche).             |User          |
|Apps|Standardmäßiges Aktivieren von neuen externen Apps|Organisationsweite App-Einstellungen|Mieter|
|Apps|Zulassen externer apps|Organisationsweite App-Einstellungen|Mieter|
|Apps|Zulassen von Sideloading externer apps<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|User|
|Apps|Standard-apps<sup>3</sup>|TeamsAppPermissionPolicy|User|
|Apps|Externe apps<sup>3</sup>|TeamsAppPermissionPolicy|User|
|Anrufe und Besprechungen     |„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Meetup für Ad-hoc-Kanal zulassen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen)         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Zulassen von Videos in Besprechungen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Bildschirmübertragung in Besprechungen zulassen         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Anrufe und Besprechungen     |Private Anrufe erlauben         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |User          |
|Messaging     |Aktivieren von Giphy, damit Benutzer GIFs zu Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Inhaltsbewertung         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Aktivieren von Memen, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Aktivieren von Aufklebern, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen, dass Besitzer alle Nachrichten löschen können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen, dass Benutzer eigene Nachrichten bearbeiten können         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Zulassen, dass Benutzer eigene Nachrichten löschen         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Ermöglicht Benutzern, privat zu chatten         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |

<sup>1</sup> veraltet für Gast. Das Aktivieren/Deaktivieren von Guest kann jetzt im Microsoft Teams Admin Center verwaltet werden. Das Aktivieren/Deaktivieren von Teams für Business Enterprise, edu Student und edu faculty wird in Kürze veraltet sein. Dies sollte durch Zuweisen von Lizenzen im Microsoft 365 Admin Center verwaltet werden. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Sideloading wird wie folgt aufgeteilt:

- Erlauben Sie einem Benutzer, apps zu querladen, die auf Benutzerebene in [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)verwaltet werden können.
- Zulassen, dass Benutzer in einem Mandanten mit benutzerdefinierten apps interagieren, die in organisationsweiten App-Einstellungen auf Mandantenebene verwaltet werden können.
 
<sup>3</sup> Standard-apps und externe Apps können auf Benutzerebene in TeamsAppPermissionPolicy aktiviert und deaktiviert werden. Darüber hinaus können apps auf Mandantenebene in organisationsweiten App-Einstellungen blockiert werden, die alle Einstellungen auf Benutzer-und Mandantenebene außer Kraft setzen. 

> [!NOTE]
> Sie verwenden weiterhin das Dashboard "Gruppen" im Microsoft 365 Admin Center für die Konfiguration in Bezug auf Teams und Kanäle. Einstellungen für apps verbleiben im Bereich "Teams" des Microsoft 365 admin Centers und werden später migriert. 

## <a name="manage-settings-during-the-migration"></a>Verwalten von Einstellungen während der Migration

Sie können die Einstellungen im Microsoft 365 Admin Center und im Skype for Business Admin Center weiter ändern, bis die Migration für einen Abschnitt für Ihren Mandanten abgeschlossen ist. 

In der folgenden Tabelle wird gezeigt, wo Sie Features während der Migration verwalten können.

|Feature  |Microsoft Teams Admin Center                      |Skype for Business Admin Center (Legacy)  |Microsoft 365 Admin Center  |
|---------|:---------:|:---------:|:---------:|
|Gruppen-Messaging, Besprechungen und Live-Ereignisrichtlinien     |     X    |         |         |
|Upgrade-Richtlinie für Teams     |    X     |         |         |
|Gast Einstellungen für Nachrichten, Besprechungen und Sprachnachrichten     |   X      |         |         |
|Lifecycle Management für Teams   |    X    |      |       |
|Einstellungen für Teams   |    X    |      |       |
|Einstellungen für den externen Zugriff     |    X    |      |       |
|Benutzerverwaltung    |         |         |    X     |    
|Audiokonferenzen     |    X     |    X     |         |
|Anrufpläne     |         |    X     |         |
|Telefonsystem    |         |     X    |         |
|Verwaltung von Telefonnummern     |         |   X      |         |
|Lizenzierung für Cloud-Sprachfeatures     |         |         |    X     |
|Automatische Telefonzentralen     |         |    X     |         |
|Anrufwarteschleifen     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Verwalten von Einstellungen nach der Migration

Wenn die Migration dieser Einstellungen abgeschlossen ist, werden Sie im Office 365 Admin Center und im Skype for Business Admin Center deaktiviert, und Sie können dann im neuen Microsoft Teams Admin Center verwaltet werden.


## <a name="edu-migration-june-july-2019"></a>EDU-Migration Juni-Juli 2019

Im Juni und Juli 2019 werden die restlichen edu-Mandanten aus der alten Administrator Erfahrung (im Microsoft 365 Admin Center) in das Team Admin Center migriert. Überprüfen Sie das Nachrichten Center (im Microsoft 365 Admin Center), um zu erfahren, wann Sie migriert werden. Nach der Migration werden die folgenden Informationen angezeigt:

|Abschnitt der Teams im Microsoft 365 Admin Center  |Einstellungsname (Mandantenebene)  |Microsoft Teams Admin Center-Richtlinie   |Ebene: Mandant oder Benutzer   |
|---------|---------|---------|---------|  
| Messaging  |Besitzer können gesendete Nachrichten löschen |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging | Benutzer können gesendete Nachrichten löschen |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging  | Benutzer können gesendete Nachrichten bearbeiten |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |User|
| Messaging | Zulassen, dass Benutzer chatten |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging | Verwenden von Giphys in Unterhaltungen | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging | Giphy-Inhaltsbewertung | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging | Verwenden von Memen in Konversationen  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
| Messaging | Verwenden von Aufklebern in Konversationen |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |

Darüber hinaus finden Sie hier die Einstellungen, die nur im Microsoft Teams Admin Center zur Verfügung stehen:

|Einstellungsname | Microsoft Teams Admin Center-Richtlinie | Ebene: Mandant oder Benutzer
|-------------|-------------------------------------|---------|
|URL-Vorschau zulassen | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
|Zulassen, dass ein Benutzer Benutzer aus einem Gruppen-Chat entfernt |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
|Ermöglichen des immersiven Readers zum Anzeigen von Nachrichten |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| User |
|Zulassen, dass Benutzer Nachrichten übersetzen |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| User |
|Lesebestätigungen | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
|Benutzer können Prioritäts Benachrichtigungen senden | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | User |
|Erstellen von Sprachnachrichten |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| User |
|Auf mobilen Geräten: Anzeigen von bevorzugten Kanälen über den letzten Chats |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| User |
