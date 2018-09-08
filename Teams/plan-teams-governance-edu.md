---
title: Microsoft Education Governance – häufig gestellte Fragen für IT-Experten - Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Antworten auf häufig gestellte Fragen von Administratoren von Microsoft Education-Gruppen, die Teams verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29e242cfdfe4e4e01c20efd2ec9dae996746b493
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883221"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Microsoft Education Governance – häufig gestellte Fragen für Administratoren

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Wie steuern kann ich Team Erstellung? Ich bin besorgt Studenten ungeeignetes Teams erstellen möchten.

Zur Vermeidung von ungeeignetes oder irreführender Names oder einfach, um weitere Struktur für die Benennung von Teams bereitzustellen, können Sie die Office 365-Gruppen Richtlinie (derzeit in der Vorschau) zum Benennen:

-   **Richtlinie zum Benennen Präfix-Suffix** Präfixe oder Suffixe zum Definieren der Benennungskonvention Teams (Gruppen), beispielsweise **GRP_US_My Group_Engineering**können. Zeichenfolgen oder Benutzerattribute (beispielsweise **[Abteilung]**), die hinzugefügt werden, auf den Namen basierend auf dem Benutzer, der das Team erstellt, können die Präfixe und Suffixe behoben werden.
-   **Benutzerdefinierte blockierte Wörter** Sie können eine Reihe von Wörtern hochladen, dass Benutzer in einer bestimmten Organisation daran gehindert werden, verwenden in den Namen des Teams, die sie erstellen. Beispielsweise können Sie die Begriffe **CEO**, **Lohn und Gehalt**und **HR** blockieren, Teamnamen für Gruppen, die, denen Sie anwenden nicht, verwendet wird.
-   **Klassifizierung** Sie können Klassifikationen erstellen, die die Benutzer in Ihrer Organisation beim Erstellen einer Gruppe von Office 365 festlegen können. 

> [!IMPORTANT]
> Mit Office 365 Gruppen Naming Policy erfordert Azure Active Directory Premium P1 Lizenzen oder Azure AD grundlegende EDU Lizenzen für jeden einzelnen Benutzer, der Mitglied einer oder mehrerer Gruppen von Office 365 ist.

Weitere Informationen finden Sie unter [Office Gruppen Richtlinie zum Benennen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Wenn Teams mithilfe der Eingabe von einem anderen System (beispielsweise Schule Datensynchronisierung) automatisch erstellt werden, stellen Sie sicher, dass die eingegebenen Daten die Benennungsrichtlinie entspricht, den Sie konfiguriert haben; Erstellung schlägt fehl, wenn es nicht der Fall team.

## <a name="can-i-see-who-created-a-team"></a>Kann ich anzeigen, die ein Team erstellt?

Um herauszufinden, die ein bestimmtes Team erstellt haben, finden Sie unter [Search das Überwachungsprotokoll für Ereignisse in der Microsoft-Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Kann ich steuern, wer Teams erstellen kann?

Im Allgemeinen raten wir von einer verhindert, da jeder Teams erstellen. Wenn jeder Teams erstellen kann, ist die Teams mehr wahrscheinlich sein. Fakultät, Lehrer oder Schüler können Teams Studie Gruppen oder bestimmte Interessengruppen erstellen. Dies hilft Teams innerhalb und außerhalb der Schulungsraum akzeptiert werden.

In unseren wünschen trägt Schulung der Benutzer verantwortlich Teams Usage. Als Benutzer verstehen, dass anonyme nicht erstellen von Teams, sie kennen die Auswirkungen der abfangen deren Erstellung und in der Regel das Tool Missbrauchs vor.

Wenn Sie sicher, dass Sie kontrollieren möchten, wer Teams erstellen können sind, finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Wie erstelle ich ein Team für jeden Kurs automatisch am Anfang des Semester oder Quartal?

Am Anfang jeder Semester oder Quartal benötigen Sie eine Anzahl von neuen Teams. Es möglicherweise sinnvoll, eine automatisierte Ansatz automatisch erstellt werden diese Teams, füllen Sie sie mit der rechten Benutzer und die richtigen Berechtigungen festlegen:

-   Schule Daten synchronisieren können für Exchange Online und SharePoint Online, Klasse Teams für Microsoft-Teams und Klasse OneNote-Notizbücher, Schule Gruppen für Intune für die aus- und Fortbildung, Rostering und einmaliges Anmelden (SSO) Integration für viele andere Office 365 Gruppen erstellen. Drittanbieter-Clientanwendungen. Weitere Informationen finden Sie unter [Übersicht über die Schule Daten synchronisieren](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Mit PowerShell können Sie Teams und Kanäle erstellen und Konfigurieren von Einstellungen automatisch. Weitere Informationen finden Sie unter [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Sie können verwenden die Microsoft Graph-API (derzeit in Beta) zu erstellen, konfigurieren, Klonen und Teams archivieren. Weitere Informationen finden Sie unter [Verwendung der Microsoft Graph-API entwickelt Microsoft-Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> Schule Daten Sync erstellt eine Office 365-Gruppe für jede Klasse synchronisiert und [ausgeblendeter Gruppenmitgliedschaft ermöglicht](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) , sodass nur Lehrer und Schüler innerhalb der Klasse die Mitglieder dieser Klasse anzeigen können. Wenn Sie mit einem anderen Prozess zum Erstellen von Gruppen Klasse HiddenGroupMembershipEnabled mithilfe des Parameters des Cmdlets New-UnifiedGroup die gleichen privaten Anforderungen erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Wie kann ich mit Teams um am Ende der Semester oder Quartal?

Es wird empfohlen, zuerst wie Teams Daten behandeln, wenn die Schule Semester oder Quartal über soll überlegen:, ob es beibehalten oder löschen ihn verfügbar für Studenten, auch nachdem sie den Kurs abgeschlossen haben. Sie sollten zu den Schulkalender beachten festgelegten Richtlinien mit Feiertage Konflikt nicht. Die folgenden Tools können Sie Ihre Strategie implementieren:

-   **Aufbewahrungsrichtlinie:** Verwenden Sie diese Option, um alle Daten, die älter sind als ein Alter löschen, die Sie angeben, um sicherzustellen, dass die alte Daten von Chats (für alle oder bestimmte Benutzer) und Kanäle entfernt werden. Sie können auch konfigurieren, Teams zum Beibehalten des Inhalts, sodass es nicht gelöscht werden kann. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft-Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Ablaufrichtlinie:** Konfigurieren von Teams, um nach einer bestimmten Anzahl von Tagen ablaufen. 30 Tage vor Ablauf, werden alle Besitzer eines Teams benachrichtigt, dass ihr Team erneuert werden muss, andernfalls ihn werden gelöscht (obwohl ein Administrator für weitere 30 Tage gelöschten Teams wiederhergestellt werden kann). Diese Einstellung ist sehr nützlich, um sicherzustellen, dass nicht verwendete Teams Sunsetted sind. Weitere Informationen finden Sie unter [Office 365 Ablauf Gruppenrichtlinien](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Archiv Team:** Diese Einstellung wird Teams in den schreibgeschützten Modus. Sie können weiterhin durchsucht und durchsucht, aber niemand können keine neuen Beiträge hinzufügen. [Archivierung oder Wiederherstellung ein Team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) wird beschrieben, wie Team Besitzer ein Team archivieren können; Team Besitzer können auch das [Diagramm-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) archiviert oder ein Team wiederherstellen.
 
> [!IMPORTANT]
> Verwenden die Office 365 Gruppen Ablaufrichtlinie erfordert Azure Active Directory Premium P1 Lizenzen für jeden einzelnen Benutzer, der Mitglied einer oder mehrerer Gruppen von Office 365 ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen für meine Fakultät von Mitgliedern zu verwenden, wenn ein Team erstellen?

Ja. Benutzer können **Team aus vorhandenen Vorlage erstellen** auswählen, beim Erstellen eines neuen Teams, und Teams Besitzer können auch das [Diagramm-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) verwenden, erstellen Sie ein neues Team verfügbaren Vorlagen aus.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich über PowerShell oder Diagramm automatisieren?

Die [Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) kann Folgendes ausführen:

-   Erstellen Sie ein Team.
-   Hinzufügen von Mitgliedern und Besitzern.
-   Kanäle hinzufügen.
-   Hinzufügen von apps.
-   Verknüpfung die entsprechenden Schritte durch Klonen einer vorhandenen team und seiner Registerkarten zu erhalten.
-   Gewähren Sie dem Benutzer eine Verknüpfung an das Team, den, das Sie gerade erstellt haben.
-   Entfernen Sie Mitglieder, Besitzer, Kanäle und apps, wenn Sie nicht mehr benötigen.
-   Archivieren Sie das Team, wenn sie nicht mehr aktiv ist. 
-   Löschen Sie Team.
-   Erstellen Sie einen Kanal thread

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) können die folgenden Aufgaben ausführen:

-   Erstellen Sie ein Team.
-   Hinzufügen von Mitgliedern und Besitzern.
-   Kanäle hinzufügen.
-   Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie nicht mehr benötigen.
-   Löschen Sie Team.

> [!TIP]
> Diagramm-API und PowerShell-Cmdlets werden ständig Funktionalität hinzufügen. Stellen Sie sicher, dass Sie die [Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) und [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) Artikel häufig für verbesserten Features zu überprüfen.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich welche Teams Features steuern Meine Fakultät und Schüler haben Zugriff auf?

Ja. Sie können Richtlinien zur Steuerung bestimmte messaging, Besprechung, aufrufen, und live-Ereignis-Features, die, denen Ihre Benutzer Zugriff haben. Sie können mit Einstellungen für Mandanten geltende können die gleichen Einstellungen gelten für alle oder Richtlinien auf Benutzerebene anwenden, wenn erforderlich. 

Weitere Informationen zu Richtlinien für Teams finden Sie unter [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich welche externen Parteien steuern Meine Fakultät und Schüler mit zusammenarbeiten?

Gast Access können Benutzer von außerhalb Ihres Mandanten einladen, für die Zusammenarbeit Research oder Gast Vorträge nützlich sein kann:

-   Verwenden Sie mithilfe der Domäne zulassen oder blockieren Gäste basierend auf ihrer Domäne.
-   Aktivieren Sie Gastzugriff ein- und ausschalten für bestimmte Gruppen von Office 365 und Teams, Gäste einladen, was die Teams können (und nicht) zu steuern.
-   Verwenden Sie das Überwachungsprotokoll sehen, welche Benachrichtigungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie unter [Gast Access in Office 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich vorhandene Teams überprüfen?

Überprüfen Sie die Überwachungsprotokolle, finden Sie unter:

-   Wer als Gast, welches Team eingeladen wurde.
-   Wer welches Team erstellt.

Weitere Informationen finden Sie unter [Suchen das Überwachungsprotokoll für Ereignisse in der Microsoft-Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams so schnell weiterentwickelt. Wie kann ich auf dem neuesten Stand bleiben?

So erhalten Sie die neuesten Updates zu Teams die folgenden Ressourcen empfohlen:

-   [Was ist neu in Microsoft-Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog des Microsoft-Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
