---
title: Häufig gestellte Fragen zur Microsoft Education-Governance für IT-Spezialisten – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Antworten auf häufig gestellte Fragen von Administratoren von Microsoft Education-Gruppen, die Teams verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0faa5f24ea64ae0fcfc967281126a4852dd139cf
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "35804833"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Verwaltung in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Wie steuere ich die Teamerstellung? Ich mache mir Sorgen, dass Schüler unangemessene Teams erstellen.

Um unangemessene oder irreführende Namen zu vermeiden oder einfach nur mehr Struktur für den Namen von Teams bereitzustellen, können Sie die Namensgebungsrichtlinie für Office 365-Gruppen verwenden (derzeit in Preview):

-   **Präfix-Suffix-Benennungsrichtlinie** Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Teams (Gruppen) zu definieren, beispielsweise **GRP_US_My Group_Engineering**. Bei den Präfixen und Suffixen kann es sich um feste Zeichenfolgen oder Benutzerattribute (wie **[Department]**) handeln, die dem Namen auf der Grundlage des Benutzers hinzugefügt werden, der das Team erstellt.
-   **Benutzerdefinierte blockierte Wörter** Sie können eine Reihe von Wörtern hochladen, die für Benutzer in einer bestimmten Organisation in den Namen der von Ihnen erstellten Teams gesperrt sind. So können Sie beispielsweise verhindern, dass die Begriffe **CEO**, **Payroll**und **HR** in Teamnamen für Gruppen verwendet werden, auf die Sie nicht zutreffen.
-   **Klassifizierung** Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Office 365-Gruppe erstellen. 

> [!IMPORTANT]
> Bei Verwendung der Office 365 Groups-Benennungsrichtlinie sind Azure Active Directory Premium P1-Lizenzen oder Azure AD Basic edu-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehrerer Office 365-Gruppen ist.

Ausführliche Anweisungen finden Sie unter [Benennungsrichtlinie für Office-Gruppen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Wenn Teams automatisch erstellt werden, indem Sie die Eingabe von einem anderen System verwenden (beispielsweise School Data Sync), stellen Sie sicher, dass die Eingabedaten der von Ihnen konfigurierten Benennungsrichtlinie entsprechen. Wenn dies nicht der Fall ist, schlägt die TEAMERSTELLUNG fehl.

## <a name="can-i-see-who-created-a-team"></a>Kann ich sehen, wer ein Team erstellt hat?

Informationen dazu, wer ein bestimmtes Team erstellt hat, finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Kann ich Steuern, wer Teams erstellen kann?

Generell empfehlen wir, Personen zu verhindern, die Teams erstellen. Wenn jeder Teams erstellen kann, ist es wahrscheinlicher, dass Teams häufig angenommen werden. Lehrkräfte, Lehrer oder Schüler können Teams verwenden, um Studiengruppen oder spezielle Interessengruppen zu erstellen. Dadurch können Teams innerhalb und außerhalb des Schulungskurses akzeptiert werden.

Nach unserer Erfahrung hilft die Benutzerschulung dabei, die Nutzung Verantwortlicher Teams zu gewährleisten. Sobald Benutzer verstehen, dass das Erstellen von Teams nicht anonym ist, verstehen Sie die Auswirkungen der sorglosen Erstellung und neigen dazu, die Verwendung des Tools zu scheuen.

Wenn Sie sicher sind, dass Sie steuern möchten, wer Teams erstellen kann, lesen Sie [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Wie erstelle ich automatisch für jeden Kurs zu Beginn des Semesters oder Quartals ein Team?

Zu Beginn jedes Semesters oder Quartals benötigen Sie eine Reihe neuer Teams. Es ist möglicherweise sinnvoll, einen automatisierten Ansatz zum automatischen Erstellen dieser Teams zu nutzen, Sie mit den richtigen Benutzern zu füllen und die richtigen Berechtigungen zu definieren:

-   School Data Sync kann Office 365-Gruppen für Exchange Online und SharePoint Online, Klassen Teams für Microsoft Teams und OneNote-Kurs Notizbuch, Schulgruppen für InTune für Bildungseinrichtungen und die Integration von Dienstplänen und einmaliges Anmelden (SSO) für viele andere Benutzer erstellen. Anwendungen von Drittanbietern. Weitere Informationen finden Sie unter [Übersicht über School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Mit PowerShell können Sie Teams und Kanäle erstellen und Einstellungen automatisch konfigurieren. Weitere Informationen finden Sie unter [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Sie können die Microsoft Graph-API (derzeit in Beta) verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren. Weitere Informationen finden Sie unter [Verwenden der Microsoft Graph-API für die Zusammenarbeit mit Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> School Data Sync erstellt eine Office 365-Gruppe für jede synchronisierte Klasse und [ermöglicht eine versteckte Gruppenmitgliedschaft](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) , sodass nur Lehrer und Schüler innerhalb der Klasse die Mitglieder dieser Klasse sehen können. Wenn Sie zum Erstellen von Klassen Gruppen einen anderen Prozess verwenden, verwenden Sie den HiddenGroupMembershipEnabled-Parameter des Cmdlets New-Unifiedgroup, um dieselben Datenschutzanforderungen zu erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Wie behandele ich Teams, wenn das Semester oder das Quartal endet?

Wir empfehlen, dass Sie sich zunächst überlegen, wie Sie mit den Team Daten umgehen möchten, wenn das Schuljahr oder-Quartal abgelaufen ist: ob Sie es löschen oder für Schüler verfügbar halten möchten, auch wenn Sie den Kurs abgeschlossen haben. Sie sollten den Schulkalender berücksichtigen, damit die von Ihnen gesetzten Richtlinien nicht mit Feiertagen in Konflikt stehen. Sie können die folgenden Tools verwenden, um Ihre Strategie zu implementieren:

-   **Aufbewahrungsrichtlinie:** Verwenden Sie diese Funktion, um alle Daten zu löschen, die älter als ein von Ihnen festgelegtes Alter sind, um sicherzustellen, dass alte Daten aus Chats (für alle oder einige Benutzer) und Kanäle entfernt werden. Sie können auch Teams so konfigurieren, dass Inhalte aufbewahrt werden, damit Sie nicht gelöscht werden können. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Ablaufrichtlinien:** Konfigurieren Sie Teams so, dass Sie nach einer bestimmten Anzahl von Tagen ablaufen. Dreißig Tage vor Ablauf werden alle Besitzer eines Teams benachrichtigt, dass Ihr Team erneuert werden muss, andernfalls wird es gelöscht (obwohl ein Administrator gelöschte Teams für weitere 30 Tage wiederherstellen kann). Diese Einstellung ist sehr hilfreich, wenn Sie sicherstellen möchten, dass ungenutzte Teams nicht verwendet werden. Weitere Informationen finden Sie unter [Office 365-Gruppen Ablaufrichtlinien](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Archiv Team:** Mit dieser Einstellung werden die Teams in den schreibgeschützten Modus versetzt. Sie können weiterhin durchsucht und durchsucht werden, aber niemand kann neue Beiträge hinzufügen. [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) beschreibt, wie Teambesitzer ein Team archivieren können. Teambesitzer können auch die [Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) zum Archivieren oder Wiederherstellen eines Teams verwenden.
 
> [!IMPORTANT]
> Bei Verwendung der Office 365 Groups-Ablaufrichtlinie sind Azure Active Directory Premium P1-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehrerer Office 365-Gruppen ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen für meine Dozenten Mitglieder, die Sie beim Erstellen eines Teams verwenden können?

Ja. Benutzer können beim Erstellen eines neuen Teams die Option " **Team aus vorhandener Vorlage erstellen** " auswählen, und die Besitzer von Teams können auch die [Diagramm-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) verwenden, um aus den verfügbaren Vorlagen ein neues Team zu erstellen.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich über PowerShell oder Graph automatisieren?

Die [Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) kann die folgenden Aktionen ausführen:

-   Erstellen Sie ein Team.
-   Mitglieder und Besitzer hinzufügen.
-   Hinzufügen von Kanälen
-   Apps hinzufügen.
-   Führen Sie eine Verknüpfung mit diesen Schritten durch, indem Sie ein vorhandenes Team Klonen und die Registerkarten ebenfalls abrufen.
-   Weisen Sie dem Benutzer einen Link zu dem soeben erstellten Team zu.
-   Entfernen Sie Mitglieder, Besitzer, Kanäle und apps, wenn Sie Sie nicht mehr benötigen.
-   Archivieren Sie das Team, wenn es nicht mehr aktiv ist. 
-   Löschen Sie das Team.
-   Erstellen eines Kanal Fadens

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) kann die folgenden Aktionen ausführen:

-   Erstellen Sie ein Team.
-   Mitglieder und Besitzer hinzufügen.
-   Hinzufügen von Kanälen
-   Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie Sie nicht mehr benötigen.
-   Löschen Sie das Team.

> [!TIP]
> Die Diagramm-API und PowerShell-Cmdlets fügen ständig Funktionen hinzu. Stellen Sie sicher, dass Sie die [Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) und [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) -Artikel häufig für Funktionsverbesserungen überprüfen.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich Steuern, auf welche Teamfunktionen meine Dozenten und Schüler Zugriff haben?

Ja. Sie können Richtlinien verwenden, um bestimmte Messaging-, Besprechungs-, Anruf-und Live-Ereignis Features zu steuern, auf die Ihre Benutzer zugreifen können. Sie können Mandantenweite Einstellungen verwenden, um die gleichen Einstellungen auf alle anzuwenden, oder wenn erforderlich, Richtlinien auf Benutzerebene anzuwenden. 

Weitere Informationen zu den Teamrichtlinien finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich Steuern, mit welchen externen Parteien meine Lehrkräfte und Schüler zusammenarbeiten?

Sie können den Gastzugriff verwenden, um Benutzer von außerhalb Ihres Mandanten einzuladen, was für Forschungszusammenarbeit oder Gastvorträge hilfreich sein kann:

-   Verwenden Sie die Domänen-Whitelist, um Gäste basierend auf Ihrer Domäne zuzulassen oder zu blockieren.
-   Aktivieren und deaktivieren Sie den Gastzugriff für bestimmte Office 365-Gruppen und-Teams, um zu steuern, welche Teams Gäste einladen können (und können).
-   Verwenden Sie das Überwachungsprotokoll, um festzustellen, welche Benachrichtigungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie unter [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich über vorhandene Teams überprüfen?

Sie können die Überwachungsprotokolle überprüfen, um Folgendes anzuzeigen:

-   Wer als Gast zu welchem Team eingeladen wurde.
-   Wer hat welches Team erstellt?

Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams entwickelt sich so schnell. Wie kann ich auf dem Laufenden bleiben?

Wir empfehlen die folgenden Ressourcen, um die neuesten Updates für Teams zu erhalten:

-   [Neuerungen in Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
