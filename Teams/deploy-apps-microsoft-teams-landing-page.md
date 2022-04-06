---
title: Wissenswertes über Apps in Microsoft Teams
ms.reviewer: ''
description: Erfahren Sie mehr über Apps, und entscheiden Sie, welche Apps in Teams basierend auf dem Profil und den Geschäftsanforderungen Ihrer Organisation zugelassen werden sollen.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb3d38060a9538196795e3da7b325840321814d8
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686392"
---
# <a name="about-apps-in-microsoft-teams"></a>Informationen zu Apps in Microsoft Teams

Apps sind eine hervorragende Möglichkeit, Ihre Arbeitsplatztools und -dienste zusammenzubringen und mit anderen zusammenzuarbeiten. Apps helfen Endbenutzern, produktiver, kollaborativer und effektiver bei ihren täglichen Aufgaben zu sein. Organisationen verwenden Apps, um sich mit ihren Kunden in Verbindung zu setzen, Dienste bereitzustellen und Informationen freizugeben. Mit apps können Benutzer effektiver in Teams Chats, Besprechungen und Kanälen. Beispiele hierfür sind Endbenutzer, die einen angehefteten Kalender in Teams verwenden, um schnell mit anderen zusammenzuarbeiten, eine App mit Bots-Funktionen, die Benutzer über QoS über einen Webdienst in einem Teams Kanal informiert, und eine App zum Freigeben und Zuweisen von Aufgaben zu verschiedenen Endbenutzern in einem Kanal.

Unsere umfangreiche Auswahl an überprüften und sicheren Apps im Store bietet Endbenutzern Zugriff auf die Tools und Dienste, die Ihre Organisation täglich benötigt. Microsoft Teams Apps sind webbasierte SaaS-Apps, die nicht bereitgestellt werden müssen. Endbenutzer können Apps in Teams nur basierend auf den von Ihnen bereitgestellten Berechtigungen verwenden. Als Administrator genehmigen oder blockieren Sie einfach die Verwendung einer beliebigen App für die Benutzer Ihrer Organisation. Sie steuern die Verfügbarkeit von Apps für alle Benutzer in Besprechungen, Chats und Kanälen.

Um Ihren Endbenutzern apps bereitzustellen, die sie benötigen, lesen Sie weiter, um die Arten von Apps zu verstehen und zu erfahren, wo Ihre Benutzer auf diese Apps zugreifen. Weitere Informationen zur Verwendung von Apps finden Sie unter [Übersicht über Apps für Endbenutzer](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Die verschiedenen Arten von Apps, die Endbenutzer in Teams verwenden können, sind:

* [Kern-Apps, die Teil Teams sind](#core-apps).
* Andere [von Microsoft erstellte Apps](#microsoft-provided-apps).
* [Drittanbieter-Apps](#third-party-apps-validated-by-microsoft) von Partnern (von Microsoft überprüft).
* [Benutzerdefinierte Apps](#custom-apps) , die von Ihrer eigenen Organisation erstellt wurden.

## <a name="core-apps"></a>Kern-Apps

Einige Standardfunktionen wie Aktivitätsfeed, Teams Kanäle, Chat, Kalender und Anrufe sind standardmäßig verfügbar und angeheftet, um Endbenutzern den Zugriff zu erleichtern. Als Administrator können Sie das Standardverhalten mithilfe der [Setuprichtlinie](/microsoftteams/teams-app-setup-policies) ändern.

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Kern-Apps sind die Apps, die standardmäßig in Teams angeheftet sind." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Von Microsoft bereitgestellte Apps

Microsoft bietet viele Apps zur Verbesserung der Produktivität und Zusammenarbeit. Sie und Endbenutzer können diese Apps finden, indem Sie nach Microsoft suchen, das als Publisher im Admin Center oder als Anbieter im Team Store aufgeführt ist.

Teams wird mit einer Reihe von integrierten Apps geliefert, darunter Listen, Aufgaben, Lob, Genehmigungen und mehr. Es ist empfehlenswert, die von Teams vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung mit aufzunehmen.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Microsoft-Apps im Teams Admin Center" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Von Microsoft überprüfte Drittanbieter-Apps

Zusätzlich zu den von Microsoft bereitgestellten Apps können Sie von Microsoft validierte Drittanbieter-Apps verwenden. Microsoft überprüft die Funktionalität und Sicherheit dieser Apps, bevor diese Apps im Teams Store verfügbar gemacht werden. Informationen zu den Vorteilen der [App-Validierung finden Sie unter Validierung von Drittanbieter-Apps](overview-of-app-validation.md).

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Beispiel für Apps von Drittanbietern im Teams Store":::

## <a name="custom-apps"></a>Benutzerdefinierte Apps

Apps, die von Entwicklern in Ihrer Organisation erstellt wurden, werden als benutzerdefinierte Apps bezeichnet. Die Entwicklung einer solchen App wird für bestimmte Anforderungen Ihrer Organisation in Auftrag gegeben, und Sie verfügen über Steuerelemente, um solche Apps zuzulassen oder zu verbieten. Entwickler in Ihrer Organisation können mithilfe Teams Integration in [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) schnell benutzerdefinierte Low-Code-Lösungen erstellen.

Nachdem ein Administrator die Verwendung von benutzerdefinierten Apps erlaubt hat, finden Endbenutzer solche Apps, indem sie im linken Navigationsbereich Teams Store auf "**Für Ihre Organisation erstellt**" klicken.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Benutzerdefinierte Apps in Teams Store in Teams Desktop-App" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Grundlegendes zum Querladen von benutzerdefinierten Apps

Beim Entwickeln von benutzerdefinierten Apps und vor der Verteilung an die Endbenutzer testen Entwickler die Apps, indem sie sie dem Store hinzufügen, um sie selbst zu testen oder mit einem Team zu testen, in dem sie die App querladen. Diese Methode wird als Querladen von Apps bezeichnet und gilt nur für benutzerdefinierte Apps.

Entwickler können eine App querladen, um sie den Mitgliedern eines bestimmten Teams zur Verfügung zu stellen, in der Regel zum Testen einer Unterentwicklungs-App.Developers can sideload an app to make it available to the members of a specific team, typically for testing an under-development app. Dies erfordert keine Administratorgenehmigung, wenn Querladen zulässig ist. Als Administrator können Sie das Querladen für jeden Entwickler verbieten.

Wenn Sie das Querladen nicht zulassen, können die Entwickler ihre Apps weiterhin in einem [Testmandanten](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant) testen. Sobald die Entwicklung benutzerdefinierter Apps abgeschlossen ist, fordern Entwickler Administratoren auf, ihre benutzerdefinierte App an die Endbenutzer zu verteilen. Ausführliche Informationen finden Sie [unter Veröffentlichen einer benutzerdefinierten App](/microsoftteams/upload-custom-apps). Als Administrator können Sie die Verwendung einer benutzerdefinierten App für bestimmte Benutzer zulassen oder verbieten.

### <a name="about-app-templates"></a>Informationen zu App-Vorlagen

App-Vorlagen für Teams sind funktionale, produktionsbereite Beispiel-Apps, die von Microsoft erstellt wurden, um beliebte Anwendungsfälle zu veranschaulichen, bewährte Methoden für die App-Entwicklung zu präsentieren und Open Source-Apps bereitzustellen, die Entwickler erweitern können, um benutzerdefinierte Apps zu erstellen. Entwickler Ihrer Organisation passen App-Vorlagen für Die Anforderungen Ihrer Organisation mit einfachen Änderungen am Code an, der in GitHub verfügbar ist. Als Administrator stellen Sie diese Apps als benutzerdefinierte Apps für Ihre Endbenutzer bereit.

Weitere Informationen finden Sie [unter Microsoft Teams App-Vorlagen](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Grundlegendes zu App-Funktionen

Um umfassende Funktionen bereitzustellen, mit denen Endbenutzer innerhalb Teams arbeiten können, nutzen App-Entwickler die folgenden App-Funktionen. Messaging-Erweiterungen ermöglichen benutzern die Interaktion mit Ihrem Webdienst Teams Client. Sie suchen oder starten Aktionen in einem externen System. Sie können das Ergebnis der Interaktion als reich formatierte Karte an den Teams Client senden. Besprechungserweiterungs-Apps integrieren die Apps eines Entwicklers in Besprechungen und bieten eine reaktionsschnelle Besprechungserfahrung.

Bots werden auch als Chatbot oder Unterhaltungsbot bezeichnet. Es handelt sich um eine App, die einfache und sich wiederholende Aufgaben ausführt. Eine Bot-Interaktion kann eine schnelle Frage und Antwort sein, oder es kann eine komplexe Unterhaltung sein, die Zugriff auf Dienste oder Unterstützung bietet. Benutzer können mit etwas Einzelchat oder in einem Kanal chatten. Sie können beispielsweise die Polly-App verwenden, um schnelle Umfragen zu erstellen, Feedback zu erhalten und eine Pulsprüfung durchzuführen.

Registerkarten sind Teams Webseiten, die am oberen Rand eines Kanals oder Chats angeheftet sind. MitHilfe von Registerkarten können Sie mit Inhalten und Diensten mit einer webähnlichen Oberfläche interagieren. Sie können Registerkarten als Teil eines Kanals innerhalb eines Teams, eines Gruppenchats oder einer persönlichen App für einen einzelnen Benutzer hinzufügen.

Webhooks und Connectors liefern Inhalte und Updates von Diensten, die Endbenutzer häufig verwenden (z. B. Jira Cloud und Bitbucket), direkt in einer Kanalunterhaltung. Apps, die diese Funktion verwenden, können mit externen Apps kommunizieren und Benachrichtigungen und Nachrichten von einem externen Dienst senden oder empfangen.

Messaging-Erweiterungen sind Tastenkombinationen zum Einfügen von App-Inhalten oder zum Reagieren auf eine Nachricht, ohne dass Endbenutzer von der Unterhaltung weg navigieren müssen. Messaging-Erweiterungen können Suchbefehle für Endbenutzer haben, um externe Inhalte schnell zu finden und in eine Nachricht oder Aktionsbefehle einzufügen.

Informationen zum Anzeigen häufiger Anwendungsfälle, die Teams Funktionen zugeordnet sind, finden Sie unter [Zuordnen von Anwendungsfällen zu Teams App-Features](/microsoftteams/platform/concepts/design/map-use-cases).

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
