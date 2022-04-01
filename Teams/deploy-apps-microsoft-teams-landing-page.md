---
title: Wissenswertes über Apps in Microsoft Teams
ms.reviewer: ''
description: Erfahren Sie mehr über Apps, und entscheiden Sie, welche Apps in Teams basierend auf dem Profil und den Geschäftsanforderungen Ihrer Organisation zugelassen werden sollen.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
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
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556526"
---
# <a name="about-apps-in-microsoft-teams"></a>Informationen zu Apps in Microsoft Teams

Mithilfe von Apps können Benutzer Inhalte in Ihren bevorzugten Diensten suchen und sie in Teams teilen. Sie ermöglichen Ihnen das Erledigen von Aufgaben wie beispielsweise das Anheften von Diensten am oberen Rand eines Kanals, das Automatisieren von Benachrichtigungen mithilfe von Bots oder das Freigeben und Zuweisen von Aufgaben. Weitere Informationen zur Verwendung von Apps finden Sie unter [Überblick der Apps für Endbenutzer](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Die verschiedenen Arten von Apps, die Ihre Endbenutzer in Teams verwenden können, sind Apps, die von Microsoft erstellt wurden, zertifizierte Apps von Drittanbietern und benutzerdefinierte Apps, die von Ihrer eigenen Organisation erstellt wurden.

## <a name="use-microsoft-provided-apps"></a>Von Microsoft bereitgestellte Apps verwenden

Teams wird mit einer Reihe von integrierten Apps geliefert, darunter Listen, Aufgaben, Lob, Genehmigungen und mehr. Es ist empfehlenswert, die von Teams vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung mit aufzunehmen. Fügen Sie weitere Apps hinzu, während Sie die Einführung von Teams vorantreiben. Einige Standardfunktionen wie Aktivitätenliste, Chat, Kalender und Anrufe sind standardmäßig verfügbar und auch angeheftet, um Endbenutzern den Zugriff zu erleichtern.

## <a name="use-third-party-apps"></a>Verwenden von Drittanbieter-Apps

Zusätzlich zu von Microsoft bereitgestellten Apps können Sie von Microsoft validierte Drittanbieter-Apps verwenden. Microsoft arbeitet mit Microsoft 365-Entwicklerpartnern zusammen, um die Informationen bereitzustellen, die benötigt werden, um Entscheidungen zur Verwendung von Teams-Apps zu beschleunigen. Weitere Informationen finden Sie unter [Microsoft Teams-App – Sicherheit und Compliance](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Verwenden von Open-Source-Beispiel-Apps, die von Microsoft bereitgestellt werden

Sie können auch [Teams-Vorlagen](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) verwenden. Das sind in GitHub verfügbare communitygesteuerte, produktionsbereite Open Source-Apps für Microsoft Teams.

## <a name="create-custom-apps"></a>Erstellen von benutzerdefinierten Apps

Sie können schnell benutzerdefinierte Low-Code-Lösungen erstellen, indem Sie von der Integration von Teams mit [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) profitieren. Sie können auch eine eigene App erstellen, die Ihren geschäftlichen Anforderungen entspricht. Weitere Informationen finden Sie unter [Erstellen von Apps für Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Entscheidungen bei der Bereitstellung von Apps

Teams bietet ohne weitere Konfiguration eine hervorragende Zusammenarbeitserfahrung, und die meisten Organisationen stellen fest, dass die Standardeinstellungen für sie sinnvoll sind. Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Standardeinstellungen geändert werden sollen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit der Kernmenge der [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), die Sie je nach den Bedürfnissen Ihrer Organisation konfigurieren können.

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen für Apps, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich für sie nicht eignen).

### <a name="app-availability-settings"></a>Verfügbarkeitseinstellungen für Apps

Teams bietet viele von Microsoft veröffentlichte und von Drittanbietern stammende Apps, um Benutzer zu binden, die Produktivität zu steigern und häufig verwendete Businessdienste in Teams zu integrieren.
Laden Sie Apps aus dem Teams Store herunter. Standardmäßig sind alle Apps, einschließlich benutzerdefinierter Apps, die Sie mithilfe des [Teams Store-Genehmigungsverfahrens](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process) eingereicht haben, für alle Benutzer aktiviert. Beispielsweise können Benutzer die Planner-App verwenden, um Teamaufgaben in Teams zu erstellen und verwalten.

Standardmäßig sind alle von Microsoft bereitgestellten, Drittanbieter- und benutzerdefinierten Apps verfügbar. Sie können einzelne Apps ein- oder ausschalten. Es gibt organisationsweite Einstellungen, mit denen Sie alle Apps von Drittanbietern und/oder benutzerdefinierte Apps für Ihre gesamte Organisation ein- oder ausschalten können.

| Frage | Aktion |
|--------------|--------|
|Müssen Sie die Teams-Standardeinstellungen für Apps ändern? | Weitere Informationen zu Richtlinien und Einstellungen, die Sie zum Verwalten von Apps in Ihrer Organisation verwenden können, finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>App-Berechtigungen und andere Überlegungen

Apps erhalten ein Einverständnis von den Benutzern und werden vom Administrator oder IT-Experten mithilfe von Richtlinien verwaltet. App-Berechtigungen und Risikoprofil werden jedoch in der App selbst definiert.

| Frage | Aktion |
|--------------|--------|
|<br>Auf welche Apps möchte ich den Zugriff erlauben? Auf welche möchte ich keinen Zugriff erlauben?  | <ul><li>Eine Liste der Gesichtspunkte, die Sie beim Zulassen des Zugriffs auf eine App, einen Bot, eine Registerkarte oder einen Connector berücksichtigen sollten, finden Sie unter [Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu](app-permissions.md).</li><li>Unter [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md) finden Sie Informationen zur Bereitstellung einer App für Benutzer in Ihrer Organisation.</li></ul>|

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Sie können diese Einstellungen je nach den Bedürfnissen und der Konfiguration Ihrer Organisation ändern.

### <a name="activity-reports"></a>Aktivitätsberichte

Mithilfe von Aktivitätsberichten können Sie erfahren, wie Benutzer in Ihrer Organisation Teams verwenden. Wenn einige beispielsweise Teams noch nicht verwenden, wissen sie vielleicht nicht, wie sie den Einstieg finden sollen oder verstehen nicht, wie sie Teams zur Steigerung ihrer Produktivität und Verbesserung der Zusammenarbeit nutzen können. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen. Um Aktivitätsberichte anzuzeigen, müssen Sie ein globaler Administrator in Microsoft 365 oder Office 365, ein Teams-Dienstadministrator oder ein Skype for Business-Administrator sein.

| Frage | Aktion |
|--------------|--------|
| <br>Wer muss in der Lage sein, die Aktivitätsberichte zu sehen, und verfügen die betreffenden Benutzer über die richtigen Berechtigungen, um sie anzuzeigen? |<ul><li>Wenn Sie einem Benutzer keine Administratorrolle zuweisen möchten, können Sie die [Leseberechtigung für Berichte zuweisen](teams-activity-reports.md#reports-reader-role).</li><li>Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [Rollen und Berechtigungen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) und [Anzeigen und Zuweisen von Rollen](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</li></ul> |

### <a name="app-templates"></a>App-Vorlagen

App-Vorlagen sind produktionsbereite Apps für Microsoft, die von der Community gefördert werden, Open Source sind und in GitHub zur Verfügung stehen. Jede App enthält detaillierte Anweisungen zum Bereitstellen und Installieren für Ihre Organisation und ist eine sofort einsatzbereite App, die Sie installieren und sofort verwenden können.

Der gesamte Quellcode steht ebenfalls zur Verfügung. Sie können ihn im Detail durchsuchen oder abzweigen, um ihn Ihren Anforderungen entsprechend zu ändern.

| Frage | Aktion |
|--------------|--------|
| Möchte ich irgendwelche Teams-App-Vorlagen wie Icebreaker installieren? |Weitere Informationen finden Sie unter [App-Vorlagen für Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
