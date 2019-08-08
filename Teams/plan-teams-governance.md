---
title: Planen der Governance in Microsoft Teams – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Hier erfahren Sie, wie Sie die Implementierung von Governance-Funktionen in Teams planen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eca84b8b8a8a80772b89800ad105ed1b2394224e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237695"
---
# <a name="plan-for-governance-in-teams"></a>Planen der Governance in Teams.

Teams bietet eine Reihe umfassender Tools zur Implementierung von Governance-Funktionen, die in Ihrer Organisation möglicherweise erforderlich sind. In diesem Artikel werden IT-Experten dazu aufgefordert, die richtigen Fragen zu stellen, um Ihre Anforderungen an die Governance zu ermitteln und zu erfüllen. 

> [!Tip] 
> Schauen Sie sich die folgende Sitzung an, um mehr über die Governance in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Gruppen-und TEAMERSTELLUNG,-Namensgebung,-Klassifizierung und Gastzugriff

Für Ihre Organisation ist es möglicherweise erforderlich, strenge Steuerelemente für das benennen und Klassifizieren von Teams zu implementieren, unabhängig davon, ob Gäste als Teammitglieder hinzugefügt werden können und wer Teams erstellen kann. Sie können jeden dieser Bereiche mit Azure Active Directory (Azure AD) konfigurieren. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation eine bestimmte Benennungskonvention für Teams?</li><li>Müssen Team Entwicklerteams die Möglichkeit geben, organisationsspezifische Klassifizierungen zuzuweisen?</li><li>Müssen Sie die Möglichkeit zum Hinzufügen von Gästen zu Teams pro Team einschränken?</li><li>Muss Ihre Organisation einschränken, wer Teams erstellen kann?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation an TEAMERSTELLUNG,-Namensgebung,-Klassifizierung und-Gastzugriff.</li><li>Planen Sie die Implementierung dieser Anforderungen als Teil des Rollouts Ihres Teams.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Benutzer über das Verhalten zu informieren, das Sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

|Funktion |Details |Azure AD Premium <br> Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Team Benennungsrichtlinie | Verwenden Sie Präfix-Suffix-basierte, benutzerdefinierte blockierte Wörter. |P1 |TBD |
|Team Klassifizierung |Zuweisen von Klassifizierungen zu Teams |P1 |TBD |
|Team Gastzugriff |Zulassen oder verhindern, dass Gäste zu Teams hinzugefügt werden. |Nein |TBD |
|Teamerstellung |Beschränken Sie die TEAMERSTELLUNG auf Administratoren. |Nein |TBD|
|Teamerstellung |Beschränken Sie die TEAMERSTELLUNG auf Mitglieder der Sicherheitsgruppe. |P1 |TBD|

> [!NOTE]
> [Weitere Informationen zum Festlegen dieser Richtlinien und zu den erforderlichen Lizenzen finden](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)Sie unter Unterstützung bei der Planung.
> 
> [!NOTE]
> Das Einschränken der Gruppen-und TEAMERSTELLUNG kann die Produktivität Ihrer Benutzer verlangsamen, da für viele Office 365-Dienste die Erstellung von Gruppen erforderlich ist, damit der Dienst funktioniert. Weitere Informationen finden Sie unter [Warum steuern, wer Office 365-Gruppen erstellt](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Weitere Informationen

Nachdem Sie Ihre Anforderungen festgelegt haben, können Sie diese mithilfe von Azure AD-Steuerelementen implementieren. Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

- [Erzwingen einer Benennungsrichtlinie für Office 365-Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Office 365-gruppenbenennungsrichtlinie](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)


## <a name="group-and-team-expiration-retention-and-archiving"></a>Ablauf, Aufbewahrung und Archivierung von Gruppen und Teams

In Ihrer Organisation sind möglicherweise zusätzliche Anforderungen für das Festlegen von Richtlinien für Ablauf, Aufbewahrung und Archivierung von Teams und Team Daten (Kanal Nachrichten und Kanaldateien) enthalten. Sie können Gruppen Ablaufrichtlinien so konfigurieren, dass der Lebenszyklus der Gruppen-und Aufbewahrungsrichtlinien automatisch verwaltet wird, um Informationen nach Bedarf zu erhalten oder zu löschen, und Sie können Teams archivieren (im schreibgeschützten Modus festlegen), um eine Point-in-Time-Ansicht eines Teams beizubehalten, das nicht mehr aktiv.

|           |            |
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation die Angabe eines Ablaufdatums für Teams?</li><li>Erfordert Ihre Organisation, dass bestimmte Datenaufbewahrungsrichtlinien auf Teams angewendet werden?</li><li>Erwartet Ihre Organisation die Möglichkeit, inaktive Teams zu archivieren, um den Inhalt im schreibgeschützten Zustand zu erhalten?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Team Ablauf, Datenaufbewahrung und Archivierung.</li><li>Planen Sie die Implementierung dieser Anforderungen als Teil des Rollouts Ihres Teams.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Benutzer über das Verhalten zu informieren, das Sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

|Funktion |Details |Azure AD Premium-Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Ablaufrichtlinie |Verwalten des Lebenszyklus von Office 365-Gruppen durch Festlegen einer Ablaufrichtlinie |P1 |TBD|
|Aufbewahrungsrichtlinie |Speichern oder löschen Sie Daten für einen bestimmten Zeitraum, indem Sie Aufbewahrungsrichtlinien für Teams im Security #a0 Compliance Center festlegen. **Hinweis**: die Verwendung dieses Features erfordert Lizenzierung von Office 365 Enterprise E3 oder höher. |Nein |TBD |
|Archivieren und Wiederherstellen |Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, möchten Sie es aber zu Referenzzwecken behalten oder in Zukunft wieder aktivieren. |Nein |TBD |

> [!Note]
> Das Ablaufdatum einer Gruppe ist eine Azure AD Premium-Funktion. Damit dieses Feature verfügbar ist, muss der Mandant ein Abonnement für Azure AD Premium und Lizenzen für den Administrator besitzen, der die Einstellungen und die Mitglieder der betroffenen Gruppen konfiguriert.

#### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Einrichten von Office 365 Groups-Ablauf](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Einrichten von Aufbewahrungsrichtlinien für Teams](retention-policies.md)

- [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Team-Funktionsverwaltung

Ein weiterer wichtiger Aspekt von Governance und Lifecycle Management für Teams ist die Möglichkeit, zu steuern, auf welche Funktionen Ihre Benutzer zugreifen können. Sie können Messaging-, Besprechungs-und Anruffeatures verwalten, entweder auf der Office 365-Mandantenebene oder pro Benutzer. 


|         |         |
|---------|---------|
| ![Ein Symbol, das Entscheidungspunkte darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation das Einschränken von Teamfunktionen für den gesamten Mandanten?</li><li>Erfordert Ihre Organisation das Einschränken von Teamfunktionen für bestimmte Benutzer?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation, um die Funktionen von Teams auf Mandanten-und Benutzerebene zu begrenzen.</li><li>Planen Sie, Ihre spezifischen Anforderungen als Teil des Rollouts für Teams zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Benutzer über das Verhalten zu informieren, das Sie erwarten können.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Fokusbereiche der Featureverwaltung in Teams

Teams bietet granulare Funktionen zum Steuern von Messaging-, Besprechungs-, Anruf-und Live-Ereignis Features und mehr über Richtlinien. Verschiedene Richtlinien können standardmäßig oder pro Benutzer nach Bedarf für Ihre Organisation auf alle Benutzer angewendet werden. 

Detaillierte Listen aller Einstellungen, einschließlich technischer Anleitungen zur Implementierung für Ihre Organisation, finden Sie in den folgenden Artikeln:

- [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
- [Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
- [Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)

Darüber hinaus können Sie die Moderation für einen Kanal einrichten und bestimmten Benutzern Moderatorfunktionen zur Verfügung stellen, damit Sie steuern können, wer Kanal Beiträge erstellen und darauf antworten kann. Weitere Informationen finden Sie unter [Einrichten und Verwalten von Kanal Moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Sicherheit und Compliance

Teams basiert auf den erweiterten Sicherheits-und Compliance-Funktionen von Office 365 und unterstützt die Überwachung und Berichterstellung, die Compliance-Inhaltssuche, e-Discovery, rechtliche Aufbewahrungs-und Aufbewahrungsrichtlinien. 

> [!Important]
> Wenn Ihre Organisation über Konformitäts-und Sicherheitsanforderungen verfügt, lesen Sie den ausführlichen Inhalt zu diesem Thema im Artikel [Übersicht über Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
