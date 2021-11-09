---
title: Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Antworten auf häufig gestellte Fragen von Administratoren von Microsoft Education-Gruppen, die Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 66fc220e2796ae35b7a11467e16da98ab475d647
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831729"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Häufig gestellte Fragen zur Microsoft Education-Governance für Administratoren

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über Das Management in ihrer Microsoft Teams zu erfahren: [Governance, Verwaltung](https://aka.ms/teams-governance) und Lebenszyklus in Microsoft Teams

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Wie steuere ich die Teamerstellung? Ich bin besorgt, dass Schüler/Studierende unangemessene Teams erstellen werden.

Sie können die Benennungsrichtlinie für Microsoft 365-Gruppen (derzeit in der Vorschau) verwenden, um unangemessene oder irreführende Namen zu vermeiden oder einfach eine mehr Struktur für die Benennung von Teams zu bieten:

-   **Präfix-Suffix-Benennungsrichtlinie** Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Teams (Gruppen) zu definieren, z. B. **GRP_US_My Group_Engineering.** Bei den Präfixen und Suffixen kann es sich um feste Zeichenfolgen oder Benutzerattribute (z. B. **[Abteilung]**) handelt, die dem Namen basierend auf dem Benutzer hinzugefügt werden, der das Team erstellt.
-   **Benutzerdefinierte blockierte Wörter** Sie können eine Gruppe von Wörtern hochladen, für die Benutzer in einer bestimmten Organisation die Verwendung von in Namen von Teams blockiert werden, die sie erstellen. So können Sie beispielsweise die Begriffe **CEO,** **Payroll** und **HR** in Teamnamen für Gruppen blockieren, für die sie nicht gelten.
-   **Klassifizierung** Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation beim Erstellen einer Gruppe Microsoft 365 können. 

> [!IMPORTANT]
> Die Verwendung der Microsoft 365-Benennungsrichtlinie für Gruppen erfordert Azure Active Directory Premium P1-Lizenzen oder Azure AD Basic EDU-Lizenzen für jeden eindeutigen Benutzer, der Mitglied einer oder mehreren Microsoft 365 ist.

Ausführliche Anweisungen finden Sie unter [Office für Gruppenbenennungsrichtlinie.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Wenn Teams automatisch anhand der Eingaben eines anderen Systems (z. B. School Data Sync) erstellt werden, überprüfen Sie, ob die Eingabedaten der von Ihnen konfigurierten Benennungsrichtlinie entsprechen. Andern falls nicht, kann die Teamerstellung nicht fehlschlagen.

## <a name="can-i-see-who-created-a-team"></a>Kann ich sehen, wer ein Team erstellt hat?

Wenn Sie herausfinden müssen, wer ein bestimmtes Team erstellt hat, lesen Sie Durchsuchen des Überwachungsprotokolls [nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>Kann ich steuern, wer Teams erstellen kann?

Im Allgemeinen wird empfohlen, niemanden am Erstellen von Teams zu verhindern. Wenn jeder Teams erstellen kann, ist Teams wahrscheinlich weit verbreitet. Lehrpersonal, Lehrkräfte oder Schüler/Studenten Teams Lerngruppen oder spezielle Interessengruppen erstellen. Dies hilft Teams innerhalb und außerhalb des Klassenzimmers akzeptiert zu werden.

Nach unserer Erfahrung trägt die Benutzererziehung dazu bei, verantwortlich für die Teams zu gewährleisten. Sobald die Benutzer verstehen, dass das Erstellen von Teams nicht anonym ist, verstehen sie die Implikationen einer unnützen Erstellung der Teams und scheuen in der Regel die Falsche Nutzung des Tools.

Wenn Sie sicher sind, dass Sie steuern möchten, wer Teams erstellen kann, lesen Sie Verwalten, [wer Gruppen Microsoft 365 kann.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Wie erstelle ich zu Beginn des Semesters oder Quartals automatisch ein Team für jeden Kurs?

Zu Beginn jedes Semesters oder Quartals benötigen Sie eine Reihe neuer Teams. Es kann sinnvoll sein, einen automatisierten Ansatz zu verwenden, um diese Teams automatisch zu erstellen, sie mit den richtigen Benutzern zu füllen und die richtigen Berechtigungen zu festlegen:

-   School Data Sync können Microsoft 365-Gruppen für Exchange Online und SharePoint Online, Kursteams für Microsoft Teams- und OneNote-Kursnotizbücher, Schulgruppen für Intune for Education sowie eine Liste und einmaliges Anmelden (Single Sign-On, SSO) erstellen. ) für viele andere Anwendungen von Drittanbietern. Weitere Informationen finden Sie [unter Übersicht über School Data Sync.](/schooldatasync/overview-of-school-data-sync)
-   Mit PowerShell können Sie Teams und Kanäle erstellen und Einstellungen automatisch konfigurieren. Weitere Microsoft Teams finden Sie unter [PowerShell.](/powershell/module/teams/?view=teams-ps)
-   Sie können die Microsoft Graph-API (derzeit in der Betaversion) verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren. Weitere Informationen finden Sie Graph Verwenden der [Microsoft Graph-API](/graph/api/resources/teams-api-overview) für die Zusammenarbeit mit Microsoft Teams.

> [!TIP]
> School Data Sync erstellt für jede synchronisierte Klasse eine Microsoft 365-Gruppe und aktiviert ausgeblendete Gruppenmitgliedschaften, sodass nur Lehrer und Schüler innerhalb des Kurss die Mitglieder dieses Kurs sehen können. [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) Wenn Sie einen anderen Prozess zum Erstellen von Klassengruppen verwenden, verwenden Sie den Parameter HiddenGroupMembershipEnabled des New-UnifiedGroup-Cmdlets, um die gleichen Datenschutzanforderungen zu erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Wie kann ich mit Teams umgehen, wenn das Semester oder Quartal endet?

Es wird empfohlen, zuerst zu überlegen, wie Sie Teams-Daten nach Abschluss des Schuljahrs oder Quartals behandeln möchten: ob sie gelöscht oder für Kursteilnehmer verfügbar bleiben sollen, auch nachdem sie den Kurs abgeschlossen haben. Sie sollten den Schulkalender im Auge behalten, damit alle von Ihnen festgelegten Richtlinien nicht mit Feiertagen in Konflikt stehen. Sie können die folgenden Tools verwenden, um Ihre Strategie zu implementieren:

-   **Aufbewahrungsrichtlinie:** Verwenden Sie diese Option, um alle Daten zu löschen, die älter als ein von Ihnen festgelegtes Alter sind, um sicherzustellen, dass alte Daten aus Chats (für alle oder einige Benutzer) und Kanäle entfernt werden. Sie können inhalte auch so Teams, dass sie nicht gelöscht werden können. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **Ablaufrichtlinie:** Konfigurieren Sie Teams so, dass sie nach einer bestimmten Anzahl von Tagen ablaufen. 30 Tage vor Ablauf werden alle Besitzer eines Teams benachrichtigt, dass ihr Team erneuert werden muss, andernfalls wird es gelöscht (ein Administrator kann gelöschte Teams jedoch für weitere 30 Tage wiederherstellen). Diese Einstellung ist sehr hilfreich, um sicherzustellen, dass nicht verwendete Teams untergehen. Weitere Informationen finden Sie [Microsoft 365 Ablaufrichtlinie für eine Gruppe.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Archivteam:** Diese Einstellung versetzt Teams in den schreibgeschützten Modus. Sie können weiterhin durchsucht und durchsucht werden, aber niemand kann neue Beiträge hinzufügen. [Das Archivieren oder Wiederherstellen eines Teams beschreibt,](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) wie Teambesitzer ein Team archivieren können. Teambesitzer können auch die [Graph-API (Beta)](/graph/api/resources/teams-api-overview) verwenden, um ein Team zu archivieren oder wiederherzustellen.
 
> [!IMPORTANT]
> Die Verwendung Microsoft 365 Ablaufrichtlinie für Gruppen erfordert Azure Active Directory Premium P1 für jeden eindeutigen Benutzer, der Mitglied einer oder mehreren Gruppen Microsoft 365 ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen für die Mitglieder meiner Lehrpersonal, die beim Erstellen eines Teams verwendet werden können?

Ja. Benutzer können **beim** Erstellen eines neuen Teams die Option Team aus vorhandener Vorlage erstellen auswählen, und Teams-Besitzer können auch die [Graph-API (Beta)](/graph/api/resources/teams-api-overview) verwenden, um ein neues Team aus den verfügbaren Vorlagen zu erstellen.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich mit PowerShell oder Graph?

Die [Microsoft Graph-API (Beta)](/graph/api/resources/teams-api-overview) kann folgende Aufgaben nutzen:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Fügen Sie Kanäle hinzu.
-   Apps hinzufügen.
-   Klonen Sie diese Schritte, indem Sie ein vorhandenes Team klonen, und erhalten Sie auch dessen Registerkarten.
-   Geben Sie dem Benutzer einen Link zu dem gerade erstellten Team.
-   Entfernen Sie Mitglieder, Besitzer, Kanäle und Apps, wenn Sie sie nicht mehr benötigen.
-   Archivieren Sie das Team, wenn es nicht mehr aktiv ist. 
-   Löschen Sie das Team.
-   Erstellen eines Kanalthreads

[PowerShell](/powershell/module/teams/?view=teams-ps) kann folgende Aufgaben verwenden:

-   Erstellen Sie ein Team.
-   Fügen Sie Mitglieder und Besitzer hinzu.
-   Fügen Sie Kanäle hinzu.
-   Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie sie nicht mehr benötigen.
-   Löschen Sie das Team.

> [!TIP]
> Die Graph-API und PowerShell-Cmdlets fügen ständig Funktionen hinzu. Überprüfen Sie häufig die [Microsoft Graph-API (Beta)](/graph/api/resources/teams-api-overview) und [PowerShell-Artikel](/powershell/module/teams/?view=teams-ps) auf Funktionsverbesserungen.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich steuern, Teams Funktionen, auf die meine Lehrpersonal und Schüler/Studenten zugreifen können?

Ja. Mithilfe von Richtlinien können Sie bestimmte Nachrichten-, Besprechungs-, Anruf- und Liveereignisfeatures steuern, auf die Ihre Benutzer zugreifen können. Sie können mandantenweite Einstellungen verwenden, um dieselben Einstellungen auf alle anzuwenden, oder bei Bedarf Richtlinien auf Benutzerebene anwenden. 

Weitere Details zu den Teams finden Sie unter Verwalten [Microsoft Teams Einstellungen für Ihre Organisation.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich steuern, mit welchen externen Parteien mein Lehrpersonal und meine Studenten zusammenarbeiten?

Sie können Gastzugriff verwenden, um Benutzer von außerhalb Ihres Mandanten einzu einladen. Dies kann hilfreich für Forschungszusammenarbeit oder Vorlesungen von Gästen sein:

-   Verwenden Sie eine Domänen-Allowlist, um Gäste basierend auf ihrer Domäne zu erlauben oder zu blockieren.
-   Aktivieren und deaktivieren Sie den Gastzugriff für bestimmte Microsoft 365 Gruppen und Teams, um zu steuern, welche Teams Gäste einladen können (und welche nicht).
-   Verwenden Sie das Überwachungsprotokoll, um zu sehen, welche Warnungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie unter [Gastzugriff in Microsoft 365 Gruppen.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich zu vorhandenen Teams überprüfen?

Sie können die Überwachungsprotokolle überprüfen, um zu sehen:

-   Wer wurde als Gast zu welchem Team eingeladen.
-   Wer team erstellt.

Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams sich so schnell weiterentwickelt. Wie kann ich auf dem Laufenden bleiben?

Wir empfehlen die folgenden Ressourcen, um die neuesten Updates auf dem neuesten Stand zu Teams:

-   [Neues in Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)