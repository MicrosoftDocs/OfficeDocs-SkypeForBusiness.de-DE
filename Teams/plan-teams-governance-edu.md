---
title: Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Antworten auf häufig gestellte Fragen von Administratoren von Microsoft Education-Gruppen, die Teams verwenden.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f8f8593d598901c71590cc395eb45b0bac7cf4f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812905"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über Das Management in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams.](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Wie steuere ich die Teamerstellung? Ich befürchte, dass Schüler/Studierende unangemessene Teams erstellen werden.

Sie können die Benennungsrichtlinie für Microsoft 365-Gruppen (derzeit in der Vorschau) verwenden, um unangemessene oder irreführende Namen zu vermeiden oder einfach nur eine Struktur für die Benennung von Teams zu bieten:

-   **Präfix-Suffix-Benennungsrichtlinie** Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Teams (Gruppen) zu definieren, z. B. **GRP_US_My Group_Engineering.** Bei den Präfixen und Suffixen kann es sich um feste Zeichenfolgen oder Benutzerattribute (z. B. **[Abteilung]**) handelt, die dem Namen basierend auf dem Benutzer hinzugefügt werden, der das Team erstellt.
-   **Benutzerdefinierte blockierte Wörter** Sie können eine Gruppe von Wörtern hochladen, die Benutzer in einer bestimmten Organisation in Namen von Teams, die sie erstellen, nicht verwenden können. So können Sie beispielsweise die Begriffe **"CEO",** "Lohnbuchhaltung" und "Personalwesen" in Teamnamen für Gruppen blockieren, für die sie nicht gelten. 
-   **Klassifizierung** Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation beim Erstellen einer Microsoft 365-Gruppe festlegen können. 

> [!IMPORTANT]
> Für die Verwendung der Benennungsrichtlinie für Microsoft 365-Gruppen sind Azure Active Directory Premium P1-Lizenzen oder Azure AD Basic -EDU-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehreren Microsoft 365-Gruppen ist.

Ausführliche Anweisungen finden Sie unter ["Benennungsrichtlinie für Office-Gruppen".](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Wenn Teams automatisch anhand der Eingaben aus einem anderen System (z. B. School Data Sync) erstellt werden, überprüfen Sie, ob die Eingabedaten mit der von Ihnen konfigurierten Benennungsrichtlinie konform sind. Andern falls nicht, kann die Teamerstellung fehlschlagen.

## <a name="can-i-see-who-created-a-team"></a>Kann ich sehen, wer ein Team erstellt hat?

Informationen dazu, wer ein bestimmtes Team erstellt hat, finden Sie unter Durchsuchen des Überwachungsprotokolls [nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>Kann ich steuern, wer Teams erstellen kann?

Im Allgemeinen wird empfohlen, nicht zu verhindern, dass jemand Teams erstellt. Wenn jeder Teams erstellen kann, ist es wahrscheinlicher, dass Teams weit verbreitet ist. Lehrkräfte, Lehrkräfte oder Studenten können Teams verwenden, um Lerngruppen oder spezielle Interessengruppen zu erstellen. Dies hilft Ihnen, Teams innerhalb und außerhalb des Klassenzimmers akzeptiert zu werden.

Nach unserer Erfahrung hilft Die Benutzererziehung bei der Sicherstellung einer verantwortlichen Nutzung von Teams. Sobald die Benutzer verstehen, dass das Erstellen von Teams nicht anonym ist, verstehen sie die Implikationen einer sorglosen Erstellung der Teams und scheuen in der Regel die fehlvermittelte Nutzung des Tools.

Wenn Sie sicher sind, dass Sie steuern möchten, wer Teams erstellen kann, lesen Sie "Verwalten, wer [Microsoft 365-Gruppen erstellen kann".](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Wie erstelle ich zu Beginn des Semesters oder Quartals automatisch ein Team für jeden Kurs?

Zu Beginn jedes Semesters oder Quartals benötigen Sie eine Reihe neuer Teams. Es kann sinnvoll sein, einen automatisierten Ansatz zu verwenden, um diese Teams automatisch zu erstellen, sie mit den richtigen Benutzern zu füllen und die richtigen Berechtigungen zu festlegen:

-   School Data Sync kann Microsoft 365-Gruppen für Exchange Online und SharePoint Online, Kursteams für Microsoft Teams und OneNote-Kursnotizbücher, Schulgruppen für Intune for Education sowie die Integration von Liste und einmaligem Anmelden (Single Sign-On, SSO) für viele andere Anwendungen von Drittanbietern erstellen. Weitere Informationen finden Sie [unter "Übersicht über School Data Sync".](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)
-   Mit PowerShell können Sie Teams und Kanäle erstellen und Einstellungen automatisch konfigurieren. Weitere [Informationen finden Sie unter Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
-   Sie können die Microsoft Graph-API (derzeit in der Betaversion) verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren. Weitere Informationen finden Sie unter Verwenden [der Microsoft Graph-API](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) für die Zusammenarbeit mit Microsoft Teams.

> [!TIP]
> School Data Sync erstellt für jede synchronisierte Klasse [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) eine Microsoft 365-Gruppe und aktiviert ausgeblendete Gruppenmitgliedschaften, damit nur Lehrkräfte und Kursteilnehmer innerhalb des Kurs die Mitglieder dieses Kurs sehen können. Wenn Sie einen anderen Prozess zum Erstellen von Klassengruppen verwenden, verwenden Sie den Parameter HiddenGroupMembershipEnabled des New-UnifiedGroup cmdlet, um die gleichen Datenschutzanforderungen zu erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Wie verdinge ich mich mit Teams, wenn das Semester oder Quartal endet?

Wir empfehlen Ihnen, zuerst zu überlegen, wie Sie die Daten zu Teams behandeln möchten, wenn das Schuljahr bzw. Quartal vorüber ist: ob Sie die Daten löschen oder auch nach Abschluss des Kurses für Kursteilnehmer verfügbar halten möchten. Sie sollten den Schulkalender berücksichtigen, damit alle von Ihnen festgelegten Richtlinien nicht mit Feiertagen in Konflikt stehen. Sie können die folgenden Tools verwenden, um Ihre Strategie zu implementieren:

-   **Aufbewahrungsrichtlinie:** Verwenden Sie diese Option, um alle Daten zu löschen, die älter als ein von Ihnen festgelegtes Alter sind, um sicherzustellen, dass alte Daten aus Chats (für alle oder einige Benutzer) und Kanälen entfernt werden. Sie können Teams auch so konfigurieren, dass Inhalte beibehalten werden, sodass sie nicht gelöscht werden können. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **Ablaufrichtlinie:** Konfigurieren Sie Teams so, dass sie nach einer bestimmten Anzahl von Tagen ablaufen. 30 Tage vor Ablauf werden alle Besitzer eines Teams benachrichtigt, dass ihr Team verlängert werden muss. Andernfalls wird es gelöscht (ein Administrator kann gelöschte Teams jedoch für weitere 30 Tage wiederherstellen). Diese Einstellung ist sehr hilfreich, um sicherzustellen, dass nicht verwendete Teams untergehen. Weitere Informationen finden Sie unter [Ablaufrichtlinie für Microsoft 365-Gruppen.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Archivteam:** Diese Einstellung versetzt Teams in den schreibgeschützten Modus. Sie können weiterhin durchsucht und durchsucht werden, aber niemand kann neue Beiträge hinzufügen. [Das Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) beschreibt, wie Teambesitzer ein Team archivieren können. Teambesitzer können auch die [Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) verwenden, um ein Team zu archivieren oder wiederherzustellen.
 
> [!IMPORTANT]
> Für die Verwendung der Ablaufrichtlinie für Microsoft 365-Gruppen sind Azure Active Directory Premium P1-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehreren Microsoft 365-Gruppen ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen, die meine Lehrkräfte beim Erstellen eines Teams verwenden können?

Ja. Benutzer können **beim** Erstellen eines neuen Teams die Option "Team aus vorhandener Vorlage erstellen" auswählen, und Teambesitzer können auch die [Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) verwenden, um ein neues Team aus den verfügbaren Vorlagen zu erstellen.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich mit PowerShell oder Graph automatisieren?

Die [Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) kann folgende Aufgaben nutzen:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Fügen Sie Kanäle hinzu.
-   Apps hinzufügen.
-   Tastenkombinationen für diese Schritte, indem Sie ein vorhandenes Team klonen und auch dessen Registerkarten erhalten.
-   Geben Sie dem Benutzer einen Link zu dem gerade erstellten Team.
-   Entfernen Sie Mitglieder, Besitzer, Kanäle und Apps, wenn Sie sie nicht mehr benötigen.
-   Archivieren Sie das Team, wenn es nicht mehr aktiv ist. 
-   Löschen Sie das Team.
-   Erstellen eines Kanalthreads

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) kann folgende Aufgaben verwenden:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Fügen Sie Kanäle hinzu.
-   Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie sie nicht mehr benötigen.
-   Löschen Sie das Team.

> [!TIP]
> Die Graph-API und die PowerShell-Cmdlets fügen ständig Funktionen hinzu. Überprüfen Sie häufig die [Artikel zur Microsoft Graph-API (Beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) und [zu PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) auf Funktionsverbesserungen.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich steuern, auf welche Funktionen von Teams mein Lehrpersonal und meine Schüler/Studierenden zugreifen können?

Ja. Mithilfe von Richtlinien können Sie bestimmte Nachrichten-, Besprechungs-, Anruf- und Liveereignisfeatures steuern, auf die Ihre Benutzer zugreifen können. Sie können mandantenweite Einstellungen verwenden, um dieselben Einstellungen auf alle anzuwenden, oder bei Bedarf Richtlinien auf Benutzerebene anwenden. 

Weitere Details zu Richtlinien für Microsoft Teams finden Sie unter "Verwalten von [Microsoft Teams-Einstellungen für Ihre Organisation".](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich steuern, mit welchen externen Parteien mein Lehrpersonal und meine Studenten zusammenarbeiten?

Mithilfe des Gastzugriffs können Sie Benutzer von außerhalb Ihres Mandanten einladen, was bei der Zusammenarbeit an Recherchen oder bei Vorträgen von Gästen hilfreich sein kann:

-   Verwenden Sie die Whitelisting für Domänen, um Gäste basierend auf ihrer Domäne zu erlauben oder zu blockieren.
-   Aktivieren und deaktivieren Sie den Gastzugriff für bestimmte Microsoft 365-Gruppen und -Teams, um zu steuern, welche Teams Gäste einladen können (oder nicht).
-   Verwenden Sie das Überwachungsprotokoll, um zu sehen, welche Benachrichtigungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie unter [Gastzugriff in Microsoft 365-Gruppen.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich zu vorhandenen Teams überprüfen?

Sie können die Überwachungsprotokolle überprüfen, um zu sehen:

-   Wer als Gast zu welchem Team eingeladen wurde.
-   Wer hat welches Team erstellt?

Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams entwickelt sich so schnell. Wie kann ich auf dem Laufenden bleiben?

Wir empfehlen die folgenden Ressourcen, um die neuesten Updates in Teams zu erhalten:

-   [Neues in Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
