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
ms.openlocfilehash: 7e64fad26d65eb1b7c96388a5f7d9a2f9c6655e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117823"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über verwaltung in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Wie steuere ich die Teamerstellung? Ich befürchte, dass Schüler unangemessene Teams erstellen werden.

Um unangemessene oder irreführende Namen zu vermeiden oder einfach mehr Struktur für die Benennung von Teams zu bieten, können Sie die Benennungsrichtlinie für Microsoft 365-Gruppen verwenden (derzeit in der Vorschau):

-   **Präfix-Suffix-Benennungsrichtlinie** Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Teams (Gruppen) zu definieren, z. B. **GRP_US_My Group_Engineering**. Die Präfixe und Suffixe können feste Zeichenfolgen oder Benutzerattribute (z. B. **[Abteilung]**) sein, die dem Namen basierend auf dem Benutzer hinzugefügt werden, der das Team erstellt.
-   **Benutzerdefinierte blockierte Wörter** Sie können eine Gruppe von Wörtern hochladen, die Benutzern in einer bestimmten Organisation in Namen von Teams, die sie erstellen, nicht verwendet werden können. Sie können beispielsweise die Verwendung der Begriffe **CEO,** **Payroll** und **HR** in Teamnamen für Gruppen blockieren, für die sie nicht gelten.
-   **Klassifizierung** Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation beim Erstellen einer Microsoft 365-Gruppe festlegen können. 

> [!IMPORTANT]
> Für die Verwendung der Benennungsrichtlinie für Microsoft 365-Gruppen sind Azure Active Directory Premium P1-Lizenzen oder Azure AD Basic EDU-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehreren Microsoft 365-Gruppen ist.

Ausführliche Anweisungen finden Sie unter [Benennungsrichtlinie für Office-Gruppen.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Wenn Teams automatisch mithilfe der Eingaben aus einem anderen System erstellt werden (z. B. School Data Sync), vergewissern Sie sich, dass die Eingabedaten der von Ihnen konfigurierten Benennungsrichtlinie entsprechen. Andern falls nicht, kann die Teamerstellung fehlschlagen.

## <a name="can-i-see-who-created-a-team"></a>Kann ich sehen, wer ein Team erstellt hat?

Informationen dazu, wer ein bestimmtes Team erstellt hat, finden Sie unter Durchsuchen des Überwachungsprotokolls [nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>Kann ich steuern, wer Teams erstellen kann?

Im Allgemeinen empfehlen wir, niemanden am Erstellen von Teams zu verhindern. Wenn jeder Teams erstellen kann, wird Teams wahrscheinlich weit verbreitet sein. Lehrkräfte, Lehrkräfte oder Studierende können Teams verwenden, um Studiengruppen oder spezielle Interessensgruppen zu erstellen. Dies hilft Ihnen, Teams innerhalb und außerhalb des Klassenzimmers zu akzeptieren.

Unserer Erfahrung nach trägt die Benutzererziehung dazu bei, eine verantwortliche Nutzung von Teams sicherzustellen. Sobald die Benutzer verstehen, dass das Erstellen von Teams nicht anonym ist, verstehen sie die Auswirkungen der unorglich erstellten Teams und scheuen sich tendenziell vor einer falschen Nutzung des Tools.

Wenn Sie sicher sind, dass Sie steuern möchten, wer Teams erstellen kann, lesen Sie [Verwalten, wer Microsoft 365-Gruppen erstellen kann.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Wie erstelle ich automatisch ein Team für jeden Kurs zu Beginn des Semesters oder Quartals?

Zu Beginn jedes Semesters oder Quartals benötigen Sie eine Reihe neuer Teams. Es kann sinnvoll sein, einen automatisierten Ansatz zu verwenden, um diese Teams automatisch zu erstellen, sie mit den richtigen Benutzern zu füllen und die richtigen Berechtigungen zu setzen:

-   School Data Sync kann Microsoft 365-Gruppen für Exchange Online und SharePoint Online, Kursteams für Microsoft Teams- und OneNote-Kursnotizbücher, Schulgruppen für Intune für Bildungseinrichtungen und die SSO-Integration (Single Sign-On) für viele andere Drittanbieteranwendungen erstellen. Weitere Informationen finden [Sie unter Übersicht über School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Mit PowerShell können Sie Teams und Kanäle erstellen und Einstellungen automatisch konfigurieren. Weitere Informationen finden Sie unter [Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)
-   Sie können die Microsoft Graph-API (derzeit in der Betaversion) verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren. Weitere Informationen finden Sie unter Verwenden der [Microsoft Graph-API](/graph/api/resources/teams-api-overview) für die Zusammenarbeit mit Microsoft Teams.

> [!TIP]
> School Data Sync erstellt eine Microsoft 365-Gruppe für jede synchronisierte Klasse und aktiviert ausgeblendete Gruppenmitgliedschaften, sodass nur Lehrer und Kursteilnehmer im Kurs die Mitglieder dieser Klasse sehen können. [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) Wenn Sie einen anderen Prozess zum Erstellen von Klassengruppen verwenden, verwenden Sie den Parameter HiddenGroupMembershipEnabled des New-UnifiedGroup cmdlet, um die gleichen Datenschutzanforderungen zu erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Wie kann ich mit Teams umgehen, wenn das Semester oder Quartal endet?

Wir empfehlen Ihnen, zuerst darüber nach zu überlegen, wie Sie teams-Daten behandeln möchten, wenn das Schulsemester oder -quartal vorüber ist: ob Sie sie löschen oder auch nach Abschluss des Kurses für Die Kursteilnehmer verfügbar halten möchten. Sie sollten den Schulkalender berücksichtigen, damit alle von Ihnen festgelegten Richtlinien nicht mit den Feiertagen in Konflikt stehen. Sie können die folgenden Tools verwenden, um Ihre Strategie zu implementieren:

-   **Aufbewahrungsrichtlinie:** Verwenden Sie diese Option, um alle Daten zu löschen, die älter als das von Ihnen festgelegte Alter sind, um sicherzustellen, dass alte Daten aus Chats (für alle oder einige Benutzer) und Kanäle entfernt werden. Sie können Teams auch so konfigurieren, dass Inhalte beibehalten werden, sodass sie nicht gelöscht werden können. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Ablaufrichtlinie:** Konfigurieren Sie Teams so, dass sie nach einer bestimmten Anzahl von Tagen ablaufen. 30 Tage vor Ablauf werden alle Besitzer eines Teams darüber informiert, dass ihr Team verlängert werden muss, andernfalls wird es gelöscht (obwohl ein Administrator gelöschte Teams für weitere 30 Tage wiederherstellen kann). Diese Einstellung ist sehr hilfreich, um sicherzustellen, dass nicht verwendete Teams nicht mehr genutzt werden. Weitere Informationen finden Sie unter Ablaufrichtlinie für [Microsoft 365-Gruppen.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Archivteam:** Diese Einstellung versetzt Teams in den schreibgeschützten Modus. Sie können weiterhin durchsucht und durchsucht werden, aber niemand kann neue Beiträge hinzufügen. [Das Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) beschreibt, wie Teambesitzer ein Team archivieren können. Teambesitzer können auch die [Graph-API (Beta)](/graph/api/resources/teams-api-overview) verwenden, um ein Team zu archivieren oder wiederherzustellen.
 
> [!IMPORTANT]
> Für die Verwendung der Ablaufrichtlinie für Microsoft 365-Gruppen sind Azure Active Directory Premium P1-Lizenzen für jeden eindeutigen Benutzer erforderlich, der Mitglied einer oder mehreren Microsoft 365-Gruppen ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen, die meine Lehrpersonal beim Erstellen eines Teams verwenden können?

Ja. Benutzer können **beim** Erstellen eines neuen Teams Team aus vorhandener Vorlage erstellen auswählen, und Teambesitzer können auch die [Graph-API (Beta)](/graph/api/resources/teams-api-overview) verwenden, um ein neues Team aus den verfügbaren Vorlagen zu erstellen.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich über PowerShell oder Graph automatisieren?

Die [Microsoft Graph-API (Beta)](/graph/api/resources/teams-api-overview) kann die folgenden Schritte tun:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Hinzufügen von Kanälen.
-   Apps hinzufügen.
-   Tastenkombinationen für diese Schritte, indem Sie ein vorhandenes Team klonen und dessen Registerkarten auch erhalten.
-   Geben Sie dem Benutzer einen Link zu dem gerade erstellten Team.
-   Entfernen Sie Mitglieder, Besitzer, Kanäle und Apps, wenn Sie sie nicht mehr benötigen.
-   Archivieren Sie das Team, wenn es nicht mehr aktiv ist. 
-   Löschen Sie das Team.
-   Erstellen eines Kanalthreads

[PowerShell](/powershell/module/teams/?view=teams-ps) kann die folgenden Schritte tun:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Hinzufügen von Kanälen.
-   Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie sie nicht mehr benötigen.
-   Löschen Sie das Team.

> [!TIP]
> Die Graph-API- und PowerShell-Cmdlets fügen ständig Funktionen hinzu. Überprüfen Sie die [Artikel microsoft Graph API (Beta)](/graph/api/resources/teams-api-overview) und [PowerShell](/powershell/module/teams/?view=teams-ps) häufig auf Funktionsverbesserungen.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich steuern, auf welche Teams-Features meine Lehrpersonal und Kursteilnehmer Zugriff haben?

Ja. Mithilfe von Richtlinien können Sie bestimmte Nachrichten-, Besprechungs-, Anruf- und Liveereignisfeatures steuern, auf die Ihre Benutzer zugreifen können. Sie können mandantenweite Einstellungen verwenden, um dieselben Einstellungen auf alle anzuwenden, oder bei Bedarf Richtlinien auf Benutzerebene anwenden. 

Weitere Informationen zu Teams-Richtlinien finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich steuern, mit welchen externen Parteien meine Lehrpersonal und Kursteilnehmer zusammenarbeiten?

Sie können den Gastzugriff verwenden, um Benutzer von außerhalb Ihres Mandanten einzu einladen, was für die Recherchezusammenarbeit oder Gastvorlesungen nützlich sein kann:

-   Verwenden Sie die Whitelisting für Domänen, um Gäste basierend auf ihrer Domäne zu erlauben oder zu blockieren.
-   Aktivieren und deaktivieren Sie den Gastzugriff für bestimmte Microsoft 365-Gruppen und Teams, um zu steuern, welche Teams Gäste einladen können (und können).
-   Verwenden Sie das Überwachungsprotokoll, um zu sehen, welche Benachrichtigungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie unter [Gastzugriff in Microsoft 365-Gruppen.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich zu vorhandenen Teams überprüfen?

Sie können die Überwachungsprotokolle überprüfen, um zu sehen:

-   Wer wurde als Gast zu welchem Team eingeladen?
-   Wer hat welches Team erstellt?

Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams entwickelt sich so schnell. Wie kann ich auf dem neuesten Stand bleiben?

Wir empfehlen die folgenden Ressourcen, um die neuesten Updates für Teams zu erhalten:

-   [Neues in Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)