---
title: Häufig gestellte Fragen zu Microsoft Education für IT-Administratoren
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Antworten auf häufig gestellte Fragen von Administratoren von Microsoft Education-Gruppen, die Teams verwenden.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6970cb95ff85ace99cc70cb81620e7a5de322496
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426852"
---
# <a name="microsoft-education-faq-for-it-admins"></a>Häufig gestellte Fragen zu Microsoft Education für IT-Administratoren

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Verwaltung in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Gewusst wie die Teamerstellung steuern? Ich bin besorgt, dass Schüler unangemessene Teams erstellen werden?

Um unangemessene oder irreführende Namen zu vermeiden oder nur um mehr Struktur für die Benennung von Teams bereitzustellen, können Sie die Microsoft 365-Gruppen Benennungsrichtlinie (derzeit in der Vorschau) verwenden:

- **Präfix-Suffix-Benennungsrichtlinie** Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Teams (Gruppen) zu definieren, z. **B. GRP_US_My Group_Engineering**. Die Präfixe und Suffixe können feste Zeichenfolgen oder Benutzerattribute (z. B. **[Abteilung]**) sein, die dem Namen basierend auf dem Benutzer hinzugefügt werden, der das Team erstellt.
- **Benutzerdefinierte blockierte Wörter** Sie können eine Gruppe von Wörtern hochladen, für die Benutzer in einer bestimmten Organisation in Namen von Teams, die sie erstellen, nicht verwendet werden können. Beispielsweise können Sie die Verwendung der Begriffe **CEO**, **Lohnbuchhaltung** und **Personalwesen** in Teamnamen für Gruppen blockieren, für die sie nicht gelten.
- **Klassifizierung** Sie können Klassifizierungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365-Gruppe erstellen.

> [!IMPORTANT]
> Die Verwendung der Microsoft 365-Gruppen Benennungsrichtlinie erfordert Azure Active Directory Premium P1 Lizenzen oder Azure AD Basic EDU-Lizenzen für jeden eindeutigen Benutzer, der Mitglied einer oder mehrerer Microsoft 365-Gruppen ist.

Ausführliche Anweisungen finden Sie unter [Benennungsrichtlinie für Office-Gruppen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!NOTE]
> Wenn Teams automatisch mithilfe der Eingabe von einem anderen System (z. B. School Data Sync) erstellt werden, stellen Sie sicher, dass die Eingabedaten der von Ihnen konfigurierten Benennungsrichtlinie entsprechen. Andernfalls schlägt die Teamerstellung fehl.

## <a name="can-i-see-who-created-a-team"></a>Kann ich sehen, wer ein Team erstellt hat?

Informationen dazu, wer ein bestimmtes Team erstellt hat, finden [Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>Kann ich steuern, wer Teams erstellen kann?

Im Allgemeinen wird davon abgeraten, zu verhindern, dass jemand Teams erstellt. Wenn jeder Teams erstellen kann, ist es wahrscheinlicher, dass Teams weit verbreitet ist. Lehrkräfte, Lehrkräfte oder Schüler/Studenten können Teams verwenden, um Studiengruppen oder spezielle Interessengruppen zu erstellen. Diese Funktion hilft Teams, innerhalb und außerhalb des Klassenzimmers akzeptiert zu werden.

Benutzerschulungen tragen unserer Erfahrung nach dazu bei, eine verantwortungsvolle Nutzung von Teams sicherzustellen. Sobald Die Benutzer verstehen, dass das Erstellen von Teams nicht anonym ist, verstehen sie die Auswirkungen der leichtfertigen Erstellung und scheuen sich davor, das Tool zu missbrauchen.

Wenn Sie sicher sind, dass Sie steuern möchten, wer Teams erstellen kann, lesen [Sie "Verwalten, wer Microsoft 365-Gruppen erstellen kann](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)".

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Gewusst wie zu Beginn des Semesters oder Quartals automatisch ein Team für jeden Kurs erstellen?

Zu Beginn jedes Semesters oder Quartals benötigen Sie neue Teams. Es kann sinnvoll sein, einen automatisierten Ansatz zu verfolgen, um diese Teams automatisch zu erstellen, sie mit den richtigen Benutzern zu füllen und die richtigen Berechtigungen festzulegen:

- School Data Sync kann Microsoft 365-Gruppen für Exchange Online und SharePoint Online, Kursteams für Microsoft Teams und OneNote-Kursnotizbücher, Schulgruppen für Intune für Bildungseinrichtungen sowie Listen und Single Sign-On (SSO)-Integration für viele andere Drittanbieteranwendungen erstellen. Weitere Informationen finden Sie unter [Übersicht über School Data Sync](/schooldatasync/overview-of-school-data-sync).
- Mit PowerShell können Sie Teams und Kanäle erstellen und Einstellungen automatisch konfigurieren. Weitere Informationen finden Sie unter [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
- Sie können die Microsoft Graph-API (derzeit in der Vorschau) verwenden, um Teams zu erstellen, zu konfigurieren, zu klonen und zu archivieren. Weitere Informationen finden Sie unter [Verwenden der Microsoft Graph-API für die Zusammenarbeit mit Microsoft Teams](/graph/api/resources/teams-api-overview).

> [!TIP]
> School Data Sync erstellt eine Microsoft 365-Gruppe für jeden synchronisierten Kurs und [aktiviert die ausgeblendete Gruppenmitgliedschaft](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) , sodass nur Lehrer und Schüler innerhalb des Kurses die Mitglieder dieses Kurses sehen können. Wenn Sie einen anderen Prozess zum Erstellen von Klassengruppen verwenden, verwenden Sie den HiddenGroupMembershipEnabled-Parameter des cmdlets New-UnifiedGroup, um die gleichen Datenschutzanforderungen zu erfüllen.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Gewusst wie mit Teams umgehen, wenn das Semester oder Quartal endet?

Es wird empfohlen, dass Sie zuerst überlegen, wie Sie Teams-Daten behandeln möchten, wenn das Schulsemester oder -quartal vorbei ist: ob Sie sie löschen oder für Schüler/Studenten verfügbar halten möchten, auch nachdem sie den Kurs abgeschlossen haben. Sie sollten den Schulkalender berücksichtigen, damit alle von Ihnen festgelegten Richtlinien keinen Konflikt mit Feiertagen verursachen. Sie können die folgenden Tools verwenden, um Ihre Strategie zu implementieren:

- **Aufbewahrungsrichtlinie:** Verwenden Sie diese Richtlinie, um alle Daten zu löschen, die älter als ein von Ihnen angegebenes Alter sind, um sicherzustellen, dass alte Daten aus Chats (für alle oder einige Benutzer) und Kanälen entfernt werden. Sie können Teams auch so konfigurieren, dass Inhalte aufbewahrt werden, sodass sie nicht gelöscht werden können. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
- **Ablaufrichtlinie:** Konfigurieren Sie Teams so, dass sie nach einem festgelegten Tag ablaufen. Dreißig Tage vor Ablauf werden alle Besitzer eines Teams benachrichtigt, dass ihr Team erneuert werden muss, andernfalls wird es gelöscht. Ein Administrator kann gelöschte Teams jedoch für weitere 30 Tage wiederherstellen. Diese Einstellung ist nützlich, um sicherzustellen, dass nicht verwendete Teams eingestellt werden. Weitere Informationen finden Sie unter [Microsoft 365-Gruppenablaufrichtlinie](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

- **Archivteam:** Diese Einstellung versetzt Teams in den schreibgeschützten Modus. Sie können weiterhin durchsucht und durchsucht werden, aber niemand kann neue Beiträge hinzufügen. [Das Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) beschreibt, wie Teambesitzer ein Team archivieren können; Teambesitzer können auch die [Graph-API (Vorschau)](/graph/api/resources/teams-api-overview) verwenden, um ein Team zu archivieren oder wiederherzustellen.

> [!IMPORTANT]
> Die Verwendung der Microsoft 365-Gruppen Ablaufrichtlinie erfordert Azure Active Directory Premium P1 Lizenzen für jeden eindeutigen Benutzer, der Mitglied einer oder mehrerer Microsoft 365-Gruppen ist.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Gibt es Teamvorlagen, die meine Lehrkräfte beim Erstellen eines Teams verwenden können?

Ja. Benutzer können beim Erstellen eines neuen Teams **"Team erstellen" aus einer vorhandenen Vorlage** auswählen, und Teams-Besitzer können auch die [Graph-API (Vorschau)](/graph/api/resources/teams-api-overview) verwenden, um ein neues Team aus den verfügbaren Vorlagen zu erstellen.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Welche Aufgaben kann ich über PowerShell oder Graph automatisieren?

Die [Microsoft Graph-API (Vorschau)](/graph/api/resources/teams-api-overview) kann die folgenden Aufgaben ausführen:

- Erstellen Sie ein Team.
- Mitglieder und Besitzer hinzufügen.
- Kanäle hinzufügen.
- Fügen Sie Apps hinzu.
- Verlinken Sie diese Schritte, indem Sie ein vorhandenes Team klonen und auch seine Registerkarten abrufen.
- Geben Sie dem Benutzer einen Link zu dem team, das Sie erstellt haben.
- Entfernen Sie Mitglieder, Besitzer, Kanäle und Apps, wenn Sie sie nicht mehr benötigen.
- Archivieren Sie das Team, wenn es nicht mehr aktiv ist.
- Löschen Sie das Team.
- Erstellen eines Kanalthreads

[PowerShell](/powershell/module/teams/?view=teams-ps) kann die folgenden Aufgaben ausführen:

- Erstellen Sie ein Team.
- Mitglieder und Besitzer hinzufügen.
- Kanäle hinzufügen.
- Entfernen Sie Mitglieder, Besitzer und Kanäle, wenn Sie sie nicht mehr benötigen.
- Löschen Sie das Team.

> [!TIP]
> Die cmdlets Graph-API und PowerShell fügen ständig Funktionen hinzu. Stellen Sie sicher, dass Sie in den [Microsoft Graph-API -Artikeln (Vorschau)](/graph/api/resources/teams-api-overview) und [PowerShell](/powershell/module/teams/?view=teams-ps) häufig nach Featureverbesserungen suchen.  

## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>Kann ich steuern, auf welche Teams-Features meine Lehrpersonal und Studenten zugreifen können?

Ja. Sie können Richtlinien verwenden, um bestimmte Messaging-, Besprechungs-, Anruf- und Liveereignisfeatures zu steuern, auf die Ihre Benutzer Zugriff haben. Sie können mandantenweite Einstellungen verwenden, um die gleichen Einstellungen auf alle anzuwenden, oder bei Bedarf Richtlinien auf Benutzerebene anwenden.

Weitere Informationen zu Teams-Richtlinien finden [Sie unter Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md).

## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>Kann ich steuern, mit welchen externen Parteien meine Lehrkräfte und Studenten zusammenarbeiten?

Sie können den Gastzugriff verwenden, um Benutzer von außerhalb Ihres Mandanten einzuladen, was für die Zusammenarbeit an Recherchen oder Gastvorlesungen hilfreich sein kann:

- Verwenden Sie eine Domänen-Zulassungsliste, um Gäste basierend auf ihrer Domäne zuzulassen oder zu blockieren.
- Aktivieren und deaktivieren Sie den Gastzugriff für bestimmte Microsoft 365-Gruppen und Teams, um zu steuern, welche Teams Gäste einladen können (und welche nicht).
- Verwenden Sie das Überwachungsprotokoll, um zu sehen, welche Benachrichtigungen an eingeladene Gäste gesendet wurden.

Weitere Informationen finden Sie [unter Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Welche Informationen kann ich zu vorhandenen Teams überprüfen?

Sie können die Überwachungsprotokolle überprüfen, um Folgendes anzuzeigen:

- Wer als Gast zu welchem Team eingeladen wurde.
- Wer welches Team erstellt hat.

Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams entwickelt sich so schnell weiter. Wie kann ich auf dem laufenden bleiben?

Wir empfehlen die folgenden Ressourcen, um die neuesten Updates für Teams zu erhalten:

- [Neuerungen in Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
- [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
