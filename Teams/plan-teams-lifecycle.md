---
title: Planen der Lebenszyklusverwaltung in Microsoft Teams – Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: Hier erfahren Sie, wie Sie die Implementierung von Funktionen für die Lebenszyklusverwaltung in Microsoft Teams planen.
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5686ec27495c8bbefbd07701031ddc179244986
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641359"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Planen der Lebenszyklusverwaltung in Microsoft Teams

Microsoft Teams bietet umfassende Tools für die Implementierung von Prozessen für die Verwaltung des Lebenszyklus der Zusammenarbeit. Dieser Artikel führt IT-Spezialisten durch Fragen, mit denen sie ihre Anforderungen an die Lebenszyklusverwaltung und die entsprechenden Tools ermitteln können. 

Die Planung der Lebenszyklusverwaltung ist deswegen so wichtig, weil Sie dabei einen Plan für die effektive Arbeitsbewältigung erstellen. Die meisten Projekte bestehen aus einem Anfang, einer Mitte und einem Ende. Bei Teams ist das auch so, aber es gibt so viele verschiedene Möglichkeiten für ihre Zusammensetzung und Verwendung, dass nicht immer offensichtlich ist, in welcher Phase ihres Lebenszyklus sie sich gerade befinden. Mithilfe eines Plans für die Lebenszyklusverwaltung können Sie die Projekte Ihrer Organisation durch diese Phasen verfolgen.

> [!Tip]
> In der folgenden Sitzung erfahren Sie mehr über den Lebenszyklus in Microsoft Teams: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance).


## <a name="lifecycle-concepts"></a>Lebenszykluskonzepte

Alle folgenden Konzepte und Definitionen beeinflussen die Entscheidungen, die Sie bezüglich der Lebenszyklusverwaltung treffen.

**Microsoft Teams**

A _team_ is a collection of people, content, and tools that facilitate collaboration. A team defines who its members are, and the permissions and policies that apply to those members. Teams are built on Office 365 Groups, and changes to Office 365 group membership sync to the team. Like other Office 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Office 365. [Learn more about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Kanäle**

Channels are the collaboration spaces within a team where the actual work is done. Each channel represents a different topic or workstream within the overall team. For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about. Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.

**Teamzugriffstypen**

Diese bestimmen, wer dem Team beitreten kann:

-   _Private_ teams are restricted to team members approved by the team owner(s). This is a typical setting for project teams and virtual teams in a large organization.
-   _Public_ teams are open for anyone in the organization to join directly. This is useful for collaboration on topics of general interest to people in different departments working on different projects. This is a good default setting for smaller organizations.

**Teambenutzertypen und Administratorrollen** 

Teambenutzertypen bestimmen, wie viel Kontrolle ein Teammitglied hat:

-   _Team creator_ has permissions to create a group or team in the directory. The admin can constrain this user type to a subset of admins or users. For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   _Team owner_ manages membership and settings for the team. There can be as many as 10 team owners per team.
-   Ein _Teammitglied_ ist ein Mitglied Ihrer Organisation, das an einem Team teilnimmt.
-   _Guest_ is a user who’s external to your organization. Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).

> [!Note]
> Weitere Informationen zu den Möglichkeiten von Teambesitzern und Teammitgliedern finden Sie im Artikel [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).

Teams admin roles determine what capabilities each admin role holder has. These are described in the following table.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Rolle&nbsp;&nbsp;</th>
    <th width="25%">Beschreibung</th>
    <th width="60%">Kann die folgenden Tasks ausführen und Tools wie beschrieben verwenden</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Teams-Dienstadministrator</td>
    <td valign="top">Verwalten des Microsoft Teams-Dienst, Erstellen und Verwalten von Office 365-Gruppen</td>
    <td valign="top">Verwalten von Besprechungen einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken<sup>1</sup><br><br>Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung, Anrufwarteschleifen und automatischen Telefonzentralen<sup>1</sup><br><br>Verwalten von Messaging einschließlich Messagingrichtlinien<sup>1</sup><br><br>Verwalten aller organisationsweiten Einstellungen einschließlich Partnerverbund, Microsoft Teams-Upgrade und Einstellungen des Microsoft Teams-Clients<sup>1</sup><br><br>Verwalten der Teams in der Organisation und der zugehörigen Einstellungen einschließlich der Mitgliedschaft<sup>2</sup><br><br>Anzeigen von Benutzerprofilseiten und Ausführen einer Problembehandlung für Probleme von Benutzern mit der Anrufqualität mithilfe erweiterter Problembehandlungstools<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams-Kommunikationsadministrator</td>
<td valign="top">Verwalten von Anruf- und Besprechungsfunktionen innerhalb des Microsoft Teams-Diensts</td>
<td valign="top">Verwalten von Besprechungen einschließlich Besprechungsrichtlinien, Konfigurationen und Konferenzbrücken<sup>1</sup><br><br>Verwalten der VoIP-Funktionen einschließlich Anrufrichtlinien, Telefonnummernbestand und -zuweisung, Anrufwarteschleifen und automatischen Telefonzentralen<sup>1</sup><br><br>Anzeigen von Benutzerprofilseiten und Ausführen einer Problembehandlung für Probleme von Benutzern mit der Anrufqualität mithilfe erweiterter Problembehandlungstools<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams-Kommunikationsspezialist</td>
<td valign="top">Ausführen einer Problembehandlung für Kommunikationsprobleme innerhalb von Microsoft Teams mithilfe von Standardtools</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams-Kommunikationssupporttechniker</td>
<td valign="top">Ausführen einer Problembehandlung für Kommunikationsprobleme innerhalb von Microsoft Teams mithilfe erweiterter Tools</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can view the full call record information.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell – Skype for Business-Modul</a> oder <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Admin Center für Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell – Microsoft Teams-Modul</a> oder <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Admin Center für Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Nur <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Admin Center für Microsoft Teams</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Im Vorfeld zu treffende IT-Entscheidungen

Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires. These can include items like naming conventions, expiration policies, retention policies, and more. Generally speaking, it’s much easier to implement these requirements prior to scaling your deployment across your organization.

Weitere Informationen finden Sie unter [Planen der Governance in Microsoft Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Lebenszyklusphasen von Teams

Generally speaking, a team has a purpose that’s aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.

Jedes Team hat einen Anfang, das heißt die Phase, in der das Team erstellt wird und die Kanäle eingerichtet werden. Außerdem hat es eine Mitte, das heißt die Phase, in der das Team genutzt wird und die Zusammenarbeit dem Rhythmus des Workflows entspricht. Manchmal gibt es auch ein Ende, das heißt die Phase, in der das Team seinen Zweck erfüllt hat und nicht mehr benötigt wird. 

Weitere Informationen finden Sie unter [Verwalten von Teams im Admin Center für Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Phase 1: Anfang

#### <a name="create-the-team"></a>Erstellen des Teams

The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub). Defining the team goal goes hand in hand with identifying the right people. As far as practicable, it’s a good idea to foster open collaboration by aiming for broad membership. 

Teambesitzer können Teammitglieder einladen, das Teambild und die Teambeschreibung festlegen sowie Berechtigungen für einzelne Mitglieder festlegen. 

> [!Tip]
>  Im Idealfall identifizieren Sie mindestens zwei Teambesitzer, um Abwesenheiten oder Umbesetzungen zu berücksichtigen.

#### <a name="team-origins"></a>Teamursprünge

Teams können durch verschiedene Methoden entstehen. Beispiele:

-   Create the team from scratch. Add members by using individual email aliases or usernames, or expand a distribution list.
-   Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.
-   Fügen Sie ein Team zu einer vorhandenen Office 365-Gruppe hinzu. Damit erhält das Team auch Zugriff auf das zugehörige Postfach und die entsprechende SharePoint-Website.
-   Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams. The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).

Unter den folgenden Links finden Sie weitere Informationen zum Organisieren Ihrer Teams:

-   [Bewährte Methoden zum Organisieren von Teams in Microsoft Teams](best-practices-organizing.md)
-   [Bereitstellen von Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Bereitstellen von Besprechungen und Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)
-   [Bereitstellen von Cloud Voice](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Was ist der Zweck des Teams?</li><li>Wer gehört zum Team?</li><li>Soll das Team privat oder öffentlich sein?</li><li>Können neue Mitglieder sich selbst hinzufügen, oder werden sie von Teambesitzern hinzugefügt?</li><li>Wer soll über Berechtigungen zum Erstellen von Kanälen oder Hinzufügen von Registerkarten, Bots und Connectors verfügen?</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Erstellen Sie das Team.</li><li>Planen Sie Kanäle.</li></ul>|


#### <a name="set-up-channels"></a>Einrichten von Kanälen

Alle Teambesitzer oder Mitglieder mit entsprechenden Berechtigungen können Kanäle in einem Team erstellen. Wichtig ist, das Ziel des jeweiligen Kanals zu berücksichtigen. Möglich sind unter anderem die Zusammenarbeit an Projekten, Diskussionen über bestimmte Themen oder Bereiche von gemeinsamem Interesse. Standardmäßig verfügt jedes Team über den Kanal „Allgemein“. Die meisten Teams benötigen mehr Kanäle, die von Mitgliedern erstellt werden. Wahrscheinlich wird die Anzahl der Kanäle organisch wachsen, wenn sich neue Themen oder Projekte ergeben, und möglicherweise entwachsen die Diskussionen dem Kanal, in dem sie begonnen haben.

Der Kanalbesitzer kann das Interesse wecken, indem er eine Willkommensnachricht veröffentlicht, relevante Dokumente in die Registerkarte **Dateien** hochlädt oder Registerkarten zu Connectors im Kanal hinzufügt. Außerdem legt der Besitzer die Kanalbeschreibung fest, und er kann wichtige Kanäle automatisch als Favoriten festlegen, damit sie für alle Teammitglieder aufgelistet werden.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Welche Kanäle werden anfangs zum Team hinzugefügt?</li><li>Welche Anleitungen werden gegebenenfalls zum Hinzufügen neuer Kanäle bereitgestellt? (Nach welchen Kriterien sollen Kanäle eingerichtet werden: Projekte, Themen, andere Kriterien?)</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Erstellen Sie die ersten Kanäle.</li><li>Stellen Sie eine Willkommensnachricht bereit.</li><li>Beginnen Sie mit der Zusammenarbeit.</li></ul>|

### <a name="stage-2-middle"></a>Phase 2: Mitte

Mit dem Beginn der Teamarbeit entwickelt sich die Teammitgliedschaft wahrscheinlich weiter, ebenso wie die Kanalhierarchie. Wenn das Team nicht streng kontrolliert und abgeschottet werden muss, sollten Sie die Mitglieder dazu ermutigen, Dinge auszuprobieren – auch wenn sie in Sackgassen führen. Wenn sich die Benutzer sicherer fühlen, können sie mit \@Teamerwähnungen experimentieren, Kanäle als Favoriten markieren und den allgemeinen Kanal nutzen, um sich mit dem Veröffentlichen von Beiträgen vertraut zu machen. Da jedes Team anders ist, sollte die Weiterentwicklung des Designs der Nutzung folgen. Überwachen Sie die Nutzung und den Zustand des Teams mithilfe der Berichterstellungsfunktionen von Microsoft Teams.

Vertrauen, Toleranz und ein Geist der Zusammenarbeit entstehen ganz natürlich, wenn wichtige Gruppenkommunikation in Microsoft Teams begonnen und fortgeführt wird. Teammitglieder erkennen, dass Gruppen-Chats hilfreicher sind als 1:1-Chats. Einzelne Teams entwickeln eine eigene Persönlichkeit, unterstützt von lustigen Features wie Giphys und Aufklebern. Gleichzeitig ist es wichtig, dass unübliches oder ungebührliches Verhalten jederzeit unterbunden wird.

Da es sich bei Teams quasi um lebende Organismen handelt, müssen sie gelegentlich untersucht und gepflegt werden. Hier sind ein paar bewährte Methoden:

-   Setzen Sie Pioniere ein, um die Nutzung wieder zu steigern, wenn sie abnimmt, und um kreative neue Verhaltensweisen zu entdecken und zu fördern. 
-   Verwalten Sie Gäste mit Bedacht, und stellen Sie sicher, dass ihr Zugriff endet, wenn die jeweilige Geschäftsanforderung nicht mehr gegeben ist.
-   Lassen Sie Kanäle mit den Geschäftsanforderungen wachsen, indem Sie bei Bedarf neue Kanäle hinzufügen und alte einschlafen lassen (oder erwägen Sie basierend auf Ihren Aufbewahrungsanforderungen, diese Kanäle zu archivieren oder zu löschen, wenn sie vertrauliche oder kurzlebige Daten enthalten).
-   Bilden Sie neue Teams, wenn größere Gruppen oder interessenbezogene Bereiche entstehen.
-   Probieren Sie verschiedene Arten der Zusammenarbeit in Kanälen aus, zum Beispiel Kanalbesprechungen oder Registerkartenunterhaltungen, in denen es um Dokumente geht.

Wenn ein Team anfängt, in einen Trott zu verfallen, ziehen Sie Folgendes in Betracht:

-   Steuern Sie die Kommunikation zu Teams hin, das heißt weg von E-Mails.
-   Verwenden Sie mobile Apps, um das Engagement der Benutzer zu verstärken.
-   Reduzieren Sie die Anzahl der Kanäle.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Wer soll die Nutzung überwachen, um Probleme zu identifizieren?</li><li>Welche Metriken werden verwendet, um zu ermitteln, ob ein Team in gutem Zustand ist?</li><li>Identifizieren Sie Teams, die nicht mehr von Nutzen sind.</li><li>Identifizieren Sie schwächelnde Teams, die noch einen Zweck erfüllen, aber einer Wiederbelebung bedürfen.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Implementieren Sie einen Prozess für die Überwachung des Zustands einzelner Teams.</li></ul>|

### <a name="stage-3-end"></a>Phase 3: Ende

Wenn die Arbeit eines Teams erledigt ist, muss das Ende auch offiziell bestätigt werden. Damit vermitteln Sie den Teammitgliedern, dass die Arbeit abgeschlossen ist, und verhindern gleichzeitig, dass jemand auf veraltete, überholte Informationen zugreift. Sie können das Team selbst nutzen, um Abschlussrituale wie nachträgliche Bewertungen und Zusammenfassungen durchzuführen.

Sie können Teams löschen, von denen Sie wissen, dass Sie sie nicht benötigen (zum Beispiel ein Team, das ausschließlich zu Testzwecken erstellt wurde, oder ein Team, das vertrauliche Daten enthält). Tatsächlich werden Teams nur vorläufig gelöscht, und dieser Vorgang kann von der IT bis zu 21 Tage lang (30 Tage für Office 365-Gruppen) rückgängig gemacht werden. Das Löschen von Teams hat keine Auswirkungen auf Chats oder Inhalte, die gemäß Compliancerichtlinien aufbewahrt wurden.

Sie können neben den Archivierungsfunktionen auch Ablauf- und Aufbewahrungsrichtlinien verwenden, um den Zugriff auf Daten durch Teams zu verhindern, die nicht mehr aktiv sind oder deren Besitzer die Organisation verlassen haben.

Weitere Informationen zum Einrichten von Ablauf- und Aufbewahrungsrichtlinien finden Sie unter [Übersicht über Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Definieren Sie, was das Ende des Lebens eines Teams ausmacht.</li><li>Entscheiden Sie, ob und wie lange der Inhalt eines Teams verfügbar bleiben soll.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie bewährte Methoden und gesammelte Erfahrungen.</li><li>Archivieren Sie bei Bedarf die Daten.</li></ul>|

