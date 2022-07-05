---
title: Chat, Teams, Kanäle und Apps in Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Enthält Schritt-für-Schritt-Anleitungen zum Konfigurieren von Teams-Einstellungen für Chat, Teams, Apps und Kanäle in Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: 86a63a47a47d438225046174104f79914f051c71
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615641"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, Teams, Kanäle und Apps in Microsoft Teams

Teams bietet ohne weitere Konfiguration eine hervorragende Zusammenarbeitserfahrung, und die meisten Organisationen stellen fest, dass die Standardeinstellungen für sie sinnvoll sind. Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Standardeinstellungen geändert werden sollen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit der Kernmenge der [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), die Sie je nach den Bedürfnissen Ihrer Organisation konfigurieren können.

Schauen Sie sich unser kurzes Video zum Thema Chats, Teams und Kanäle in Teams (4:30 Minuten) an, um die ersten Schritte zu machen:

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

Sie können den [Advisor für Teams](use-advisor-teams-roll-out.md) als Hilfe beim Rollout von Microsoft Teams verwenden. Advisor für Teams führt Sie durch Ihren Rollout von Teams. Er analysiert Ihre Microsoft 365-Umgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können.

> [!TIP]
> Es ist empfehlenswert, die von uns vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung mit aufzunehmen. Fügen Sie mit fortschreitender Aneignung von Teams weitere [Apps, Bots und Connectors](deploy-apps-microsoft-teams-landing-page.md) hinzu.

 > [!Note]
 > Mehr über Teams-Funktionen auf verschiedenen Plattformen erfahren Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Voraussetzungen für die Bereitstellung von Chat

Bevor Sie Teams in Ihrer Organisation bereitstellen, nehmen Sie sich Zeit, um zu überprüfen, ob Ihre Umgebung für Teams bereit ist. Lesen Sie die Informationen unter [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md), und nehmen Sie die erforderlichen Änderungen an Ihrer Umgebung vor.

|Frage|Aktion |
|------------|-------|
|Ist meine Organisation für die Bereitstellung von Teams bereit?|Zur Beantwortung dieser Frage lesen Sie: <ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</li><li>[URLs und IP-Adressbereiche](office-365-urls-ip-address-ranges.md)</li><li>[Planen von Microsoft 365-Gruppen beim Erstellen von Teams](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen für Chat, Teams und Kanäle, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen sich für sie nicht eignen).

### <a name="teams-administrators"></a>Teamadministratoren

Teams bietet eine Reihe benutzerdefinierter Administratorrollen, die zum Verwalten von Teams für Ihre Organisation verwendet werden können. Die Rollen stellen Administratoren verschiedene Funktionen zur Verfügung.

| Frage | Aktion |
|--------------|--------|
|Wem wird die Rolle des Teams-Kommunikationsadministrators zugewiesen?|Weitere Informationen zu den Administratorrollen in Teams finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).|
|Wem wird die Rolle des Teams-Kommunikationssupporttechnikers zugewiesen?|Informationen zum Zuweisen von Administratorrollen finden Sie unter [Zuweisen von Administrator- und anderen Rollen zu Benutzern mithilfe von Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Wem wird die Rolle des Teams-Kommunikationssupportexperten zugewiesen?||

### <a name="teams-owners-and-members"></a>Teambesitzer und -mitglieder

In Microsoft Teams können Sie zusätzlich zu den Administratorrollen die Benutzerrollen "Besitzer" und "Mitglieder" zuweisen und ihnen selektiv Moderatorenfunktionen zuordnen (wenn die Moderation eingerichtet wurde), um zu steuern, wer bestimmte Aktionen in einem Kanal ausführen kann. Mit der Moderation können Sie steuern, wer neue Beiträge in einem Kanal starten kann, Teammitglieder als Moderatoren hinzufügen und entfernen sowie steuern, ob Teammitglieder auf vorhandene Kanalmeldungen antworten können.

|Frage|Aktion |
|------------|-------|
|Wem sollten die einzelnen Rollen zugewiesen werden? | Einen Vergleich der Funktionen der einzelnen Rollen finden Sie unter [Zuweisen von Teambesitzern, Moderatoren und Mitgliedern in Microsoft Teams](assign-roles-permissions.md).
|Wie kann ich eine Benutzerrolle zuweisen? | Informationen zum Zuweisen oder Ändern einer Rolle finden Sie unter [Zuweisen einer Benutzerrolle](assign-roles-permissions.md#assign-a-user-role).
|Muss ich steuern, wer in einem Kanal Beiträge senden und beantworten kann? | Informationen zum Konfigurieren der Moderation finden Sie unter [Einrichten und Verwalten der Kanalmoderation in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Messagingrichtlinien

Mithilfe von Messaging-Richtlinien wird gesteuert, welche Chat- und Messaging-Funktionen den Benutzern in Teams zur Verfügung stehen. Beispielsweise, wer gesendete Nachrichten bearbeiten und löschen, wer Chat verwenden, wer Memes in Unterhaltungen verwenden kann und mehr. Standardmäßig wird den Benutzern die globale Messaging-Richtlinie zugewiesen, und alle Funktionen sind **Aktiviert**. Sie können die globale Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messaging-Richtlinien für die Benutzer in Ihrer Organisation erstellen. 

|Frage|Aktion |
|------------|-------|
|Soll ich die globale Messagingrichtlinie anpassen?|Informationen zur Verwendung des Microsoft Teams Admin Centers zum Ändern der globalen Messagingrichtlinie oder zum Hinzufügen einer neuen Richtlinie finden Sie unter [Verwalten von Messagingrichtlinien in Teams](messaging-policies-in-teams.md).|
|Benötige ich mehrere Messagingrichtlinien?|Informationen zum Erstellen und Zuweisen einer Messagingrichtline in PowerShell finden Sie unter [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md) (PowerShell-Beispielskript – Erstellen und Zuweisen einer Messagingrichtlinie).|
|Wie bestimme ich, welche Benutzergruppen welche Messagingrichtlinie erhalten?|Informationen zu den CsTeamsMessagingPolicy-Cmdlets finden Sie unter [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Externer Zugriff

Externer Zugriff (Partnerverbund) ermöglicht es Ihren Benutzern, mit Personen außerhalb Ihrer Organisation per Chat zu kommunizieren. Durch Aktivieren dieser Funktion und Hinzufügen von Domänen zur Liste der zulässigen Domänen können Ihre Benutzer mit Benutzern in anderen Domänen und Organisationen kommunizieren. Externer Zugriff ist standardmäßig aktiviert.

|Frage|Aktion |
|------------|-------|
|<ul><li>Kann ich externe Besprechungen und Chats für meine Organisation deaktivieren?</li><li>Falls er aktiviert ist, soll ich die Domänen einschränken, mit denen meine Organisation kommunizieren kann?</li></ul> |<br>Informationen zum Aktivieren oder Deaktivieren externer Besprechungen und Chats finden Sie unter [Verwalten externer Besprechungen und Chats](manage-external-access.md).|

### <a name="guest-access"></a>Gastzugriff

Mithilfe des Gastzugriffs in Teams können Einzelbenutzer außerhalb Ihrer Organisation auf Teams und Kanäle zugreifen. Sie können die Einstellungen für den Gastzugriff verwenden, um zu steuern, welche Features Gästen zur Verfügung stehen. Der Gastzugriff ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Gastzugriff in Teams](./guest-access.md).

> [!NOTE]
> Weitere Informationen zu externem Zugriff und Gastzugriff finden Sie hier: [Kommunikation mit Benutzern aus anderen Organisationen in Microsoft Teams](communicate-with-users-from-other-organizations.md).


|Frage|Aktion |
|------------|-------|
|Kann ich den Gastzugriff für meine Organisation deaktiviert?|Informationen zum Aktivieren oder Deaktivieren des Gastzugriffs finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams](set-up-guests.md).|
|Falls er aktiviert ist, soll ich die für Gäste in meiner Organisation verfügbaren Funktionen anpassen?|Informationen zum Anpassen der Verfügbarkeit von Funktionen bei Gastzugriff finden Sie unter [Authorize guest access in Teams](teams-dependencies.md) (Autorisieren des Gastzugriffs in Microsoft Teams).|

### <a name="private-channels"></a>Private Kanäle

Private Kanäle ermöglichen es einer Teilmenge von Teammitgliedern, in einem privaten Bereich zusammenzuarbeiten, auf den andere Teammitglieder weder zugreifen noch ihn anzeigen können. Jede Person, auch Gäste, kann einem privaten Kanal als Mitglied hinzugefügt werden, solange sie bereits Mitglied des Teams ist.

|Frage|Aktion |
|------------|-------|
|Möchte ich Teambesitzern und Mitgliedern erlauben, private Kanäle zu erstellen?|Informationen zum Festlegen einer Richtlinie für private Kanäle für Ihre Organisation finden Sie unter [Verwalten von Kanalrichtlinien in Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Freigegebene Kanäle

Freigegebene Kanäle ermöglichen es Ihnen, Personen, die nicht Mitglied eines Teams sind, zu einem Kanäle hinzuzufügen. Dies gilt auch für Personen, die nicht zu Ihrer Organisation gehören. Freigegebene Kanäle bieten gegenüber dem Gastzugriff den Vorteil, dass Personen außerhalb Ihrer Organisation kein Gastkonto in Ihrem Verzeichnis benötigen.

|Frage|Aktion |
|------------|-------|
|Wann verwende ich freigegebene Kanäle im Vergleich zum Gastzugriff?|Weitere Informationen finden Sie unter [Freigegebene Kanäle in Microsoft Teams](shared-channels.md).|
|<ul><li>Kann ich Teambesitzern das Erstellen freigegebener Kanäle erlauben?</li><li>Kann ich Teambesitzern das Freigeben von Kanälen mit Personen außerhalb der Organisation erlauben?</li><li>Kann ich Benutzern die Teilnahme an freigegebenen Kanälen erlauben, die sich außerhalb der Organisation befinden?</li></ul> |<br>Informationen zum Festlegen einer Richtlinie für freigegebene Kanäle für Ihre Organisation finden Sie unter [Verwalten von Kanalrichtlinien in Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Teams-Einstellungen

Mithilfe der Teams-Einstellungen können Sie für Ihre Teams Funktionen wie E-Mail-Integration, Cloud-Speicheroptionen, die Organisationsregisterkarte, das Einrichten von Geräten in Besprechungsräumen und den Suchbereich einrichten. Wenn Sie Änderungen an diesen Einstellungen vornehmen, betreffen sie alle Teams in Ihrer Organisation. Weitere Informationen finden Sie unter [Teams-Einstellungen](enable-features-office-365.md#teams-settings).

|Frage|Aktion |
|------------|-------|
|Soll ich die Teams-Einstellungen für meine Organisation anpassen? | Informationen über Teams-Einstellungen und ihre Anpassung finden Sie unter [Teams-Einstellungen](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Teams-Clients

Teams unterstützt eine Reihe von Clients, von Web- über Desktop- bis zu mobilen Clients, und in der Standardkonfiguration können die Benutzer die Clients ihrer Wahl verwenden. Weitere Informationen hierzu finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).

|Frage|Aktion |
|------------|-------|
|Soll ich die Teams-Clientverfügbarkeit für meine Organisation anpassen?|Lesen Sie [Hardwareanforderungen für die Microsoft Teams-App](hardware-requirements-for-the-teams-app.md). |
|Soll ich die Teams-Clienteinstellungen für meine Organisation anpassen?|Erfahren Sie mehr über das [Installieren von Microsoft Teams mithilfe von MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Microsoft Teams-Nutzungsbericht

Benutzer mit den Rollen globaler Administrator, Teams-Dienstadministrator und Leseberechtigung für Berichte können Teams-Nutzungsberichte lesen. Weitere Informationen finden Sie in den [Analysen zur Nutzung von Microsoft 365](/microsoft-365/admin/usage-analytics/usage-analytics).

|Frage|Aktion |
|------------|-------|
|<br> Wer muss in der Lage sein, die Teams-Nutzungsberichte zu sehen, und verfügen die betreffenden Benutzer über die richtige Rolle, um sie anzuzeigen? |<ul><li>Wenn der Benutzer kein Administrator ist, [weisen Sie die Leseberechtigung für Berichte zu](teams-activity-reports.md#reports-reader-role).</li><li>Informationen zum Zuweisen von Administratorrollen in Azure Active Directory finden Sie unter [Rollen und Berechtigungen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) und [Anzeigen und Zuweisen von Rollen](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).|

### <a name="teams-default-apps"></a>Teams-Standard-Apps 

Teams bietet eine Reihe von vom Originalhersteller (von Microsoft bereitgestellte) und von Drittanbietern stammende Apps, um Benutzer zu binden, die Produktivität zu steigern und häufig verwendete Businessdienste in Teams zu integrieren. Laden Sie Apps aus dem Teams Store herunter. Apps sind in Teams standardmäßig aktiviert. 

Weitere Informationen zum Bereitstellen und Verwalten von Apps in Teams finden Sie in unserem ausführlichen Leitfaden [Apps, Bots und Connectors](deploy-apps-microsoft-teams-landing-page.md).

## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Je nach den Bedürfnissen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, diese Einstellungen zu ändern.

### <a name="teams-licensing"></a>Teams-Lizenzierung

Teams wird als Teil vieler Microsoft 365-Lizenzen angeboten.

|Frage|Aktion |
|------------|-------|
|Verfügen meine Benutzer über die erforderlichen Lizenzen, um alle Funktionen von Teams zu verwenden, die ich bereitstellen möchte? | Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilität von Exchange und SharePoint

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange, SharePoint und das Erstellen einer Microsoft 365-Gruppe aktiviert sein. Die folgenden Artikel geben allgemeine Informationen zu Exchange-Postfächern wieder, die in verschiedenen Umgebungen gehostet sind, über die Interaktion von Exchange und Teams und ähnliche Überlegungen für SharePoint und OneDrive.

|Frage|Aktion |
|------------|-------|
| Kann ich die benötigten Teams-Funktionen mit den aktuellen Exchange- und SharePoint-Bereitstellungen bieten? |Weitere Informationen zu Exchange und SharePoint in Teams finden Sie unter:<ul><li> [Interaktion von Exchange und Teams](exchange-teams-interact.md)</li><li>[Interaktion von SharePoint Online und OneDrive mit Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams-Grenzwerte und -Daten 

Bei der Planung einer Enterprise-Bereitstellung von Teams sollten Sie alle relevanten Einschränkungen und Spezifikationen berücksichtigen, wie etwa die maximale Anzahl von Mitgliedern pro Team, die maximale Anzahl Teams, die von einem Benutzer erstellt werden können usw.

|Frage|Aktion |
|------------|-------|
| Welche Grenzwerte werde ich mit meiner Teams-Bereitstellung mit Wahrscheinlichkeit erreichen? | Weitere Informationen finden Sie unter [Limits and specifications for Teams](limits-specifications-teams.md) (Grenzwerte und Daten für Teams). |

### <a name="urls-and-ports"></a>URLs und Ports

Organisationen, die eine fein abgestufte Kontrolle ihres Internetdatenverkehrs betreiben, sollten [URLs und IP-Adressbereiche](/office365/enterprise/urls-and-ip-address-ranges) lesen. Dort finden sie eine aktuelle Liste der URLs, IP-Adressen, Ports und Protokolle, die für Microsoft Teams richtig konfiguriert sein müssen. Microsoft verbessert die Microsoft 365-Dienste ständig und fügt neue Funktionen hinzu. Das bedeutet, dass sich die erforderlichen Ports, URLs und IP-Adressen mit der Zeit ändern können. Wir empfehlen, den Artikel über RSS zu abonnieren, damit Sie erfahren, wenn diese Informationen aktualisiert oder geändert werden. Stellen Sie mindestens sicher, dass Sie die oben unter [Voraussetzungen für die Chat-Bereitstellung](#chat-deployment-prerequisites) aufgeführten Ports geöffnet haben.

|Frage|Aktion |
|------------|-------|
| Benötige ich Internetzugriffsregeln, um Benutzern die Verwendung von Teams zu ermöglichen, oder ist das Öffnen der mindestens erforderlichen Ports ausreichend? | Weitere Informationen finden Sie unter [URLs und IP-Adressbereiche](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Governance (Benennungskonventionen, wer darf Teams erstellen)

Ihre Organisation schreibt möglicherweise die Implementierung von Kontrollen zur Benennung und Klassifizierung von Teams, zu den Personen, die Teams erstellen können und zum Ablauf, der Aufbewahrung und der Archivierung von Teams vor. Dies wird als Governance bezeichnet. Für die Konfiguration dieser Bereiche können Sie Azure Active Directory (Azure AD) verwenden.


| Frage | Aktion |
|--------------|--------|
|Muss ich Kontrollen zum Personenkreis implementieren, der Teams erstellen kann?| Lesen Sie [Planen der Governance in Teams](plan-teams-governance.md).|
|Muss ich Kontrollen zur Benennung von Teams implementieren?|Lesen Sie [Erzwingen einer Benennungsrichtlinie für Microsoft 365-Gruppen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Teams-Anwendungsrichtlinie (Seitenbereichssteuerung)

Eine angeheftete App wird im Seitenbereich in Teams angezeigt. Durch Erstellen von Teams-Anwendungsrichtlinien können Sie Sätze von angehefteten Teams-Apps vorkonfigurieren, um Teams für ausgewählte Benutzergruppen zu personalisieren. Standardmäßig ist die Einstellung **Externe Apps in Microsoft Teams zulassen** aktiviert.

| Frage | Aktion |
|--------------|--------|
|Sollte ich vorkonfigurierte Sätze angehefteter Teams-Anwendungen erstellen? | Lesen Sie [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).|
|Wie soll ich entscheiden, welche Gruppen diese App-Gruppen erhalten?|Lesen Sie [Berechtigungen für Microsoft Teams-Apps und Überlegungen dazu](app-permissions.md).|

### <a name="archiving-and-compliance"></a>Archivierung und Kompatibilität 

Ihre Organisation schreibt möglicherweise vor, dass Sie Verfahren zur Archivierung und zu den in bestimmten Arten von Teams aufzubewahrenden Arten von Daten implementieren. Lesen Sie [Übersicht über Sicherheit und Compliance in Teams](security-compliance-overview.md), um zu erfahren, welche Einstellungen standardmäßig aktiviert sind.

| Frage | Aktion |
|--------------|--------|
|Muss ich für Teams Aufbewahrung konfigurieren?|Informationen zum Einrichten von Aufbewahrungsrichtlinien finden Sie unter [Set up Teams retention policies](retention-policies.md) (Einrichten von Aufbewahrungsrichtlinien in Teams).|
|Muss ich die Archivierung von Teams konfigurieren?|Informationen zum Archivieren oder Wiederherstellen eines Teams finden Sie unter [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Muss ich zusätzliche Complianceeinstellungen konfigurieren?|Weitere Informationen zu Sicherheit und Compliance finden Sie unter [Überblick über Sicherheit und Compliance in Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Bedingter Zugriff 

Teams verwendet in großem Umfang Exchange und SharePoint für elementare Produktivitätsszenarien, einschließlich Besprechungen, Kalender, Interoperabilitäts-Chats und Dateifreigabe. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Teams, wenn sich Benutzer direkt bei Teams anmelden – unabhängig vom Client. Richtlinien für den bedingten Zugriff, die für die Teams-Cloud-App festgelegt wurden, steuern Aspekte wie den Benutzerzugriff auf Teams-Dienste aus bestimmten Netzwerken.

| Frage | Aktion |
|--------------|--------|
|<br>Muss ich bedingen Zugriff für Teams konfigurieren?|<ul><li>Die Grundlagen von Zugriffsrichtlinien sind unter [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) (Funktionsweise von Richtlinien für den bedingten Zugriff für Teams) erläutert.</li><li>Informationen zum Einrichten der mehrstufigen Authentifizierung (MFA) für Teams finden Sie unter:<ul><li>[Schnellstart: Vorschreiben von MFA für bestimmte Apps mithilfe von bedingtem Zugriff in Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Einstellungsreferenz für bedingten Zugriff in Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Schulung und Weiterbildung (EDU) 

IT-Experten, die in Bildungseinrichtungen arbeiten, können Teams for Education nutzen, das eine Reihe von Funktionen bietet, die auf bildungsspezifische Szenarien für Studenten, Lehrkräfte und ihr Geschäftsumfeld zugeschnitten sind.

| Frage | Aktion |
|--------------|--------|
|Muss ich EDU-spezifische Teams-Vorlagen verwenden? |Weitere Informationen zu Teams for Education finden Sie unter [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md) (Häufig gestellte Fragen zu Governance von Microsoft Education für Administratoren).|
|Muss ich eine Suche mit eingeschränktem Suchbereich bereitstellen?|Informationen zum Einrichten von Teams for EDU finden Sie unter [Schnellstart – Teams for Education-Administratoren](teams-quick-start-edu.yml).|
|Muss ich Teams in den School Data Sync-Dienst integrieren, um Benutzerkonten bereitzustellen?|[Teams-Ressourcen für Administratoren in Bildungseinrichtungen](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Behörden – GCC-Überlegungen

Die Nutzung von Office 365 for Government – GCC (Government Community Cloud) ist angemessen, um den Anforderungen von IT-Experten zu genügen, die Bereitstellungen von Office 365 in Bundes-, Landes-, Kommunal- oder Territorialbehörden der USA oder in anderen Entitäten betreuen, in denen Daten verarbeitet werden, die gesetzlichen Bestimmungen und Anforderungen unterliegen.

| Frage | Aktion |
|--------------|--------|
| Muss ich Teams in einer Office 365 for Government – GCC-Umgebung bereitstellen? | Überlegungen zur Bereitstellung finden Sie unter [Planen der Bereitstellung von Office 365 Government – GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Nächste Schritte
- [Fördern der Einführung](adopt-microsoft-teams-landing-page.md) von Chat, Teams, Kanälen und Apps.
- Nehmen Sie die vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung auf. Fügen Sie mit fortschreitender Aneignung von Teams weitere [Apps, Bots und Connectors](deploy-apps-microsoft-teams-landing-page.md) hinzu.
- [Bereitstellung von Besprechungen und Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)
- [Bereitstellen von Cloud Voice](cloud-voice-landing-page.md)
