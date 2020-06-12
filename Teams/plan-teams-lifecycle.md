---
title: Planen der Lebenszyklusverwaltung
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In diesem Artikel erfahren Sie, wie Sie die Implementierung von Funktionen für die Lebenszyklusverwaltung in Microsoft Teams planen.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d142be3a8d5f245cda857601995653d6ca6d240
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665287"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Planen der Lebenszyklusverwaltung in Microsoft Teams

Microsoft Teams bietet umfassende Tools für die Implementierung von Prozessen für die Verwaltung des Lebenszyklus der Zusammenarbeit. Dieser Artikel führt IT-Spezialisten durch Fragen, mit denen sie ihre Anforderungen an die Lebenszyklusverwaltung und die entsprechenden Tools ermitteln können. 

Die Planung der Lebenszyklusverwaltung ist deswegen so wichtig, weil Sie dabei einen Plan für die effektive Arbeitsbewältigung erstellen. Die meisten Projekte bestehen aus einem Anfang, einer Mitte und einem Ende. Bei Teams ist das auch so, aber es gibt so viele verschiedene Möglichkeiten für ihre Zusammensetzung und Verwendung, dass nicht immer offensichtlich ist, in welcher Phase ihres Lebenszyklus sie sich gerade befinden. Mithilfe eines Plans für die Lebenszyklusverwaltung können Sie die Projekte Ihrer Organisation durch diese Phasen verfolgen.

> [!Tip]
> In der folgenden Sitzung erfahren Sie mehr über den Lebenszyklus in Microsoft Teams: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance).


## <a name="lifecycle-concepts"></a>Lebenszykluskonzepte

Alle folgenden Konzepte und Definitionen beeinflussen die Entscheidungen, die Sie bezüglich der Lebenszyklusverwaltung treffen.

**Microsoft Teams**

Ein _Team_ ist eine Sammlung von Personen, Inhalten und Tools, die die Zusammenarbeit unterstützen. Ein Team definiert, wer seine Mitglieder sind und welche Berechtigungen und Richtlinien für diese Mitglieder gelten. Teams basieren auf Microsoft 365-Gruppen, und Änderungen an der Mitgliedschaft in Microsoft 365-Gruppen werden mit dem Team synchronisiert. Ebenso wie andere Microsoft 365-Gruppen verfügen Teams automatisch über ein Exchange-Postfach, eine SharePoint-Website, ein OneNote-Notizbuch und andere Microsoft 365- oder Office 365-Ressourcen. [Weitere Informationen zu Microsoft 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Kanäle**

Kanäle sind die Zusammenarbeitsbereiche innerhalb eines Teams, in denen die eigentliche Arbeit stattfindet. Jeder Kanal stellt ein anderes Thema oder einen anderen Arbeitsstream innerhalb des Gesamtteams dar. Für jeden Kanal wird automatisch auf der SharePoint-Website ein Ordner erstellt, in dem alle für diesen Kanal freigegebenen Dateien gespeichert werden. So können die Benutzer für sie wichtige Dokumente leicht finden und mit ihnen arbeiten. Außerdem können Kanäle mit Apps erweitert werden, die für den jeweiligen Arbeitsstream relevant sind. Sie können zum Beispiel ein Power BI-Dashboard zu einem Kanal hinzufügen, um den Erfolg eines Projektaspekts zu verfolgen.

**Teamzugriffstypen**

Diese bestimmen, wer dem Team beitreten kann:

-   _Private_ Teams sind auf Teammitglieder beschränkt, die von den Teambesitzern genehmigt werden. Dies ist eine typische Einstellung für Projektteams und virtuelle Teams in einer großen Organisation.
-   _Öffentliche_ Teams stehen allen in der Organisation offen, und alle können direkt beitreten. Dies ist hilfreich bei der Zusammenarbeit an Themen, die für Personen in verschiedenen Abteilungen, die an verschiedenen Projekten arbeiten, von allgemeinem Interesse sind. Diese Einstellung eignet sich gut als Standardeinstellung für kleinere Organisationen.

**Teambenutzertypen und Administratorrollen** 

Teambenutzertypen bestimmen, wie viel Kontrolle ein Teammitglied hat:

-   Der _Teamersteller_ verfügt über Berechtigungen zum Erstellen einer Gruppe oder eines Teams im Verzeichnis. Der Administrator kann diesen Benutzertyp auf eine Teilmenge der Administratoren oder Benutzer begrenzen. Weitere Informationen finden Sie unter [Verwalten von Personen, die berechtigt sind, Microsoft 365-Gruppen zu erstellen](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   Der _Teambesitzer_ verwaltet die Mitgliedschaft und die Einstellungen für das Team. Pro Team sind bis zu 100 Teambesitzer möglich.
-   Ein _Teammitglied_ ist ein Mitglied Ihrer Organisation, das an einem Team teilnimmt.
-   Ein _Gast_ ist ein Benutzer, der nicht zu Ihrer Organisation gehört. Jeder, der über eine E-Mail-Adresse verfügt, kann als Gast eingeladen werden, sofern Ihre Organisation den [Gastzugriff](guest-access.md) aktiviert hat.

> [!Note]
> Weitere Informationen zu den Möglichkeiten von Teambesitzern und Teammitgliedern finden Sie im Artikel [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).

Die Administratorrollen in Microsoft Teams bestimmen, welche Möglichkeiten den Inhabern der einzelnen Administratorrollen zur Verfügung stehen. Diese Rollen und Möglichkeiten werden in der folgenden Tabelle beschrieben.

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
    <td valign="top">Verwalten des Microsoft Teams-Dienstes, Erstellen und Verwalten von Microsoft 365-Gruppen</td>
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
<td valign="top">Zugreifen auf Benutzerprofilseiten, um mit der Anrufanalyse eine Problembehandlung für Anrufe auszuführen. Kann nur Benutzerinformationen für den gesuchten Benutzer anzeigen.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams-Kommunikationssupporttechniker</td>
<td valign="top">Ausführen einer Problembehandlung für Kommunikationsprobleme innerhalb von Microsoft Teams mithilfe erweiterter Tools</td>
<td valign="top">Zugreifen auf Benutzerprofilseiten, um mit der Anrufanalyse eine Problembehandlung für Anrufe auszuführen. Kann sämtliche Informationen in Anrufdatensätzen anzeigen.<sup>3</sup></td>
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

Bevor Sie Microsoft Teams in Ihrer Organisation einführen, sollten Sie Governancerichtlinien implementieren, die die Organisation für notwendig befunden hat. Dazu können Dinge gehören wie Benennungskonventionen, Ablaufrichtlinien, Aufbewahrungsrichtlinien und vieles mehr. Generell ist es viel einfacher, diese Anforderungen zu implementieren, bevor Sie die Bereitstellung für die gesamte Organisation skalieren.

Weitere Informationen finden Sie unter [Planen der Governance in Microsoft Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Lebenszyklusphasen von Teams

Allgemein ausgedrückt hat ein Team einen Zweck, der einem Projekt oder der Erreichung eines Ziels entspricht. Auch wenn ein Team auf der Grundlage gemeinsamer Interessen gebildet wurde, wird sich die Teammitgliedschaft wahrscheinlich im Lauf der Zeit ändern. Möglicherweise kommt die Diskussion zum Erliegen, nur um in einem anderen Team auf etwas andere Weise wieder aufzuleben.

Jedes Team hat einen Anfang, das heißt die Phase, in der das Team erstellt wird und die Kanäle eingerichtet werden. Außerdem hat es eine Mitte, das heißt die Phase, in der das Team genutzt wird und die Zusammenarbeit dem Rhythmus des Workflows entspricht. Manchmal gibt es auch ein Ende, das heißt die Phase, in der das Team seinen Zweck erfüllt hat und nicht mehr benötigt wird. 

Weitere Informationen finden Sie unter [Verwalten von Teams im Admin Center für Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Phase 1: Anfang

#### <a name="create-the-team"></a>Erstellen des Teams

Der erste Schritt besteht darin, das Ziel des Teams zu definieren. (Dabei kann es um Geschäftsprozesse, die Organisationsstruktur oder Projekte gehen oder einfach um die Schaffung eines offenen, unstrukturierten Hubs für Zusammenarbeit.) Die Definition des Teamziels geht Hand in Hand mit dem Identifizieren der richtigen Personen. Soweit möglich ist es eine gute Idee, die offene Zusammenarbeit zu fördern, indem Sie eine breite Mitgliedschaft anstreben. 

Teambesitzer können Teammitglieder einladen, das Teambild und die Teambeschreibung festlegen sowie Berechtigungen für einzelne Mitglieder festlegen. 

> [!Tip]
>  Im Idealfall identifizieren Sie mindestens zwei Teambesitzer, um Abwesenheiten oder Umbesetzungen zu berücksichtigen.

#### <a name="team-origins"></a>Teamursprünge

Teams können durch verschiedene Methoden entstehen. Beispiele:

-   Erstellen Sie das Team von Grund auf. Fügen Sie Mitglieder hinzu, indem Sie einzelne E-Mail-Aliase oder Benutzernamen verwenden oder eine Verteilerliste erweitern.
-   Erstellen Sie das Team aus einem vorhandenen Team, dessen Kanalkonfiguration und App-Konfigurationen Sie als Vorlage verwenden. Optional können Sie auch die Mitgliederliste dieses Teams verwenden.
-   Fügen Sie ein Team zu einer vorhandenen Microsoft 365-Gruppe hinzu. Damit erhält das Team auch Zugriff auf das zugehörige Postfach und die entsprechende SharePoint-Website.
-   Verwenden Sie zum Erstellen von Teams die Teams-APIs für Microsoft Graph oder PowerShell-Cmdlets. Die APIs können programmgesteuert Teams auf der Grundlage von Attributen des globalen Adressbuchs (wie zum Beispiel Region oder Abteilung) oder von Geschäftsprozessen (z. B. Kundenverpflichtungen oder Kurslisten) erstellen.

Unter den folgenden Links finden Sie weitere Informationen zum Organisieren Ihrer Teams:

-   [Bewährte Methoden zum Organisieren von Teams in Microsoft Teams](best-practices-organizing.md)
-   [Bereitstellen von Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Bereitstellen von Besprechungen und Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)
-   [Bereitstellen von Cloud Voice](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Was ist der Zweck des Teams?</li><li>Wer gehört zum Team?</li><li>Soll das Team privat oder öffentlich sein?</li><li>Können neue Mitglieder sich selbst hinzufügen, oder werden sie von Teambesitzern hinzugefügt?</li><li>Wer soll über Berechtigungen zum Erstellen von Kanälen oder Hinzufügen von Registerkarten, Bots und Connectors verfügen?</li></ul> |
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Erstellen Sie das Team.</li><li>Planen Sie Kanäle.</li></ul>|


#### <a name="set-up-channels"></a>Einrichten von Kanälen

Alle Teambesitzer oder Mitglieder mit entsprechenden Berechtigungen können Kanäle in einem Team erstellen. Wichtig ist, das Ziel des jeweiligen Kanals zu berücksichtigen. Möglich sind unter anderem die Zusammenarbeit an Projekten, Diskussionen über bestimmte Themen oder Bereiche von gemeinsamem Interesse. Standardmäßig verfügt jedes Team über den Kanal „Allgemein“. Die meisten Teams benötigen mehr Kanäle, die von Mitgliedern erstellt werden. Wahrscheinlich wird die Anzahl der Kanäle organisch wachsen, wenn sich neue Themen oder Projekte ergeben, und möglicherweise entwachsen die Diskussionen dem Kanal, in dem sie begonnen haben.

Der Kanalbesitzer kann das Interesse wecken, indem er eine Willkommensnachricht veröffentlicht, relevante Dokumente in die Registerkarte **Dateien** hochlädt oder Registerkarten zu Connectors im Kanal hinzufügt. Außerdem legt der Besitzer die Kanalbeschreibung fest, und er kann wichtige Kanäle automatisch als Favoriten festlegen, damit sie für alle Teammitglieder aufgelistet werden.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Welche Kanäle werden anfangs zum Team hinzugefügt?</li><li>Welche Anleitungen werden gegebenenfalls zum Hinzufügen neuer Kanäle bereitgestellt? (Nach welchen Kriterien sollen Kanäle eingerichtet werden: Projekte, Themen, andere Kriterien?)</li></ul> |
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Erstellen Sie die ersten Kanäle.</li><li>Stellen Sie eine Willkommensnachricht bereit.</li><li>Beginnen Sie mit der Zusammenarbeit.</li></ul>|

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
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Wer soll die Nutzung überwachen, um Probleme zu identifizieren?</li><li>Welche Metriken werden verwendet, um zu ermitteln, ob ein Team in gutem Zustand ist?</li><li>Identifizieren Sie Teams, die nicht mehr von Nutzen sind.</li><li>Identifizieren Sie schwächelnde Teams, die noch einen Zweck erfüllen, aber einer Wiederbelebung bedürfen.</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Implementieren Sie einen Prozess für die Überwachung des Zustands einzelner Teams.</li></ul>|

### <a name="stage-3-end"></a>Phase 3: Ende

Wenn die Arbeit eines Teams erledigt ist, muss das Ende auch offiziell bestätigt werden. Damit vermitteln Sie den Teammitgliedern, dass die Arbeit abgeschlossen ist, und verhindern gleichzeitig, dass jemand auf veraltete, überholte Informationen zugreift. Sie können das Team selbst nutzen, um Abschlussrituale wie nachträgliche Bewertungen und Zusammenfassungen durchzuführen.

Sie können Teams löschen, von denen Sie wissen, dass Sie sie nicht benötigen (zum Beispiel ein Team, das ausschließlich zu Testzwecken erstellt wurde, oder ein Team, das vertrauliche Daten enthält). Tatsächlich werden Teams nur „vorläufig gelöscht“, so dass die IT in der Lage ist, diesen Vorgang bis zu 21 Tage lang (30 Tage für Microsoft 365-Gruppen) rückgängig zu machen. Das Löschen von Teams hat keine Auswirkungen auf Chats oder Inhalte, die gemäß Compliancerichtlinien aufbewahrt wurden. Kanäle weisen auch ein "Soft Delete"-Feature auf und können bis zu 21 Tage nach dem Löschen wiederhergestellt gemacht werden.

Sie können neben den Archivierungsfunktionen auch Ablauf- und Aufbewahrungsrichtlinien verwenden, um den Zugriff auf Daten durch Teams zu verhindern, die nicht mehr aktiv sind oder deren Besitzer die Organisation verlassen haben.

Weitere Informationen zum Einrichten von Ablauf- und Aufbewahrungsrichtlinien finden Sie unter [Übersicht über Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Definieren Sie, was das Ende des Lebens eines Teams ausmacht.</li><li>Entscheiden Sie, ob und wie lange der Inhalt eines Teams verfügbar bleiben soll.</li></ul> |
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie bewährte Methoden und gesammelte Erfahrungen.</li><li>Archivieren Sie bei Bedarf die Daten.</li></ul>|

## <a name="related-topics"></a>Verwandte Themen

[Governance-Schnellstart für Teams](teams-adoption-governance-quick-start.md)
