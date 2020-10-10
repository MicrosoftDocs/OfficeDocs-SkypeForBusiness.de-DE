---
title: Planen der Governance in Microsoft Teams – Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In diesem Artikel erfahren Sie, wie Sie die Implementierung von Governance-Funktionen in Teams planen können.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416912"
---
# <a name="plan-for-governance-in-teams"></a>Planen der Governance in Teams.

Teams bietet eine Reihe umfassender Tools zur Implementierung von Governance-Funktionen, die in Ihrer Organisation möglicherweise erforderlich sind. In diesem Artikel werden IT-Experten dazu aufgefordert, die richtigen Fragen zu stellen, um Ihre Anforderungen an die Governance zu ermitteln und zu erfüllen. 

> [!Tip] 
> Schauen Sie sich die folgende Sitzung an, um mehr über die Governance in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Gruppen-und TEAMERSTELLUNG,-Namensgebung,-Klassifizierung und Gastzugriff

Für Ihre Organisation ist es möglicherweise erforderlich, strenge Steuerelemente für das benennen und Klassifizieren von Teams zu implementieren, unabhängig davon, ob Gäste als Teammitglieder hinzugefügt werden können und wer Teams erstellen kann. Sie können diese Bereiche mit Azure Active Directory (Azure AD) und Vertraulichkeits Beschriftungen konfigurieren. 

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
|Vertraulichkeits Beschriftungen|Konfigurieren von Datenschutz und Gast Freigabe|Nein|TBD|

> [!NOTE]
> [Weitere Informationen zum Festlegen dieser Richtlinien und zu den erforderlichen Lizenzen finden](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)Sie unter Unterstützung bei der Planung.
> 
> [!NOTE]
> Das Einschränken der Gruppen-und TEAMERSTELLUNG kann die Produktivität Ihrer Benutzer verlangsamen, da für viele Microsoft 365-und Office 365-Dienste Gruppen erstellt werden müssen, damit der Dienst funktioniert. Weitere Informationen finden Sie unter [Warum steuern, wer Microsoft 365-Gruppen erstellt](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Weitere Informationen

Nachdem Sie Ihre Anforderungen festgelegt haben, können Sie diese mithilfe von Azure AD-Steuerelementen implementieren. Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Erzwingen einer Benennungsrichtlinie für Microsoft 365-Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Benennungsrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Verwenden von Vertraulichkeits Beschriftungen zum Schützen von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Optionen für das Ende des Lebenszyklus für Gruppen, Teams und jammern](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Ablauf, Aufbewahrung und Archivierung von Gruppen und Teams

In Ihrer Organisation sind möglicherweise zusätzliche Anforderungen für das Festlegen von Richtlinien für Ablauf, Aufbewahrung und Archivierung von Teams und Team Daten (Kanal Nachrichten und Kanaldateien) enthalten. Sie können Gruppen Ablaufrichtlinien so konfigurieren, dass der Lebenszyklus der Gruppen-und Aufbewahrungsrichtlinien automatisch verwaltet wird, um Informationen nach Bedarf zu erhalten oder zu löschen, und Sie können Teams archivieren (im schreibgeschützten Modus festlegen), um eine Point-in-Time-Ansicht eines Teams beizubehalten, das nicht mehr aktiv ist. Beachten Sie, dass die archivierten Teams weiterhin die Ablaufrichtlinie angewendet haben und möglicherweise gelöscht werden, wenn Sie nicht ausgeschlossen oder erneuert werden.

|           |            |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation die Angabe eines Ablaufdatums für Teams?</li><li>Erfordert Ihre Organisation, dass bestimmte Datenaufbewahrungsrichtlinien auf Teams angewendet werden?</li><li>Erwartet Ihre Organisation die Möglichkeit, inaktive Teams zu archivieren, um den Inhalt im schreibgeschützten Zustand zu erhalten?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Team Ablauf, Datenaufbewahrung und Archivierung.</li><li>Planen Sie die Implementierung dieser Anforderungen als Teil des Rollouts Ihres Teams.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Benutzer über das Verhalten zu informieren, das Sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

|Funktion |Details |Azure AD Premium-Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Ablaufrichtlinie |Verwalten des Lebenszyklus von Microsoft 365-Gruppen durch Festlegen einer Ablaufrichtlinie |P1 |TBD|
|Aufbewahrungsrichtlinie |Speichern oder löschen Sie Daten für einen bestimmten Zeitraum, indem Sie Aufbewahrungsrichtlinien für Teams im Security & Compliance Center festlegen. **Hinweis**: die Verwendung dieses Features erfordert Lizenzierung von Microsoft 365 oder Office 365 Enterprise E3 oder höher. |Nein |TBD |
|Archivieren und Wiederherstellen |Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, möchten Sie es aber zu Referenzzwecken behalten oder in Zukunft wieder aktivieren. |Nein |TBD |

> [!Note]
> Das Ablaufdatum einer Gruppe ist eine Azure AD Premium-Funktion. Damit dieses Feature verfügbar ist, muss der Mandant ein Abonnement für Azure AD Premium und Lizenzen für den Administrator besitzen, der die Einstellungen und die Mitglieder der betroffenen Gruppen konfiguriert.

#### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Einrichten von Microsoft 365 Groups-Ablauf](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Einrichten von Aufbewahrungsrichtlinien für Teams](retention-policies.md)

- [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Verwaltung von Gruppen-und Teammitgliedern

Die konsistente Verwaltung von Mitgliedern von projektbasierten oder eingeschränkten Gruppen ist für Teams notwendig, die schnelle Onboarding-und offboarding oder Benutzer und Gäste benötigen. Ihre Organisation muss möglicherweise auch sicherstellen, dass alle aktuellen Mitglieder die geschäftliche Berechtigung haben, in einem Team zu sein. Das Verwalten von Mitgliedern kann schwierig sein, da Teambesitzer die Aufgabe übernehmen können und Benutzergruppen in der Regel nicht aus eigenem Antrieb belassen, wenn ein Projekt endet oder wenn Sie die Rollen ändern. Die beste Methode zum Verwalten von Gruppenmitgliedschaften, die es Benutzern ermöglichen, bei Bedarf Zugriff zu erhalten, aber sicherzustellen, dass die Gruppe keine unangemessenen Zugriffs Risiken hat, besteht in zwei Distrikt Prozessen: Berechtigungsverwaltung und Zugriffsprüfungen.

Mit der [Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) können Sie an eine andere Person, beispielsweise einen Projektmanager, delegieren, um alle erforderlichen Ressourcen in einem einzigen Paket zu sammeln, einschließlich der Mitgliedschaft in Teams. Darüber hinaus können Sie festlegen, wer Anforderungen stellen kann: entweder Benutzer in Ihrem Mandanten oder von anderen verbundenen Organisationen. Der Projektmanager erhält Zugriffsanforderungen in seinen e-Mail-Nachfragen sowie Genehmigungs-oder Ablehnungs Anforderungen im myaccess-Portal. Administratoren können die Bedingungen für Access so konfigurieren, dass Sie ein Ablaufdatum oder einen Zeitraum angeben, bis zu dem der Benutzer oder Gast aus dem Team entfernt wird, es sei denn, der Zugriff wird erneuert. Administratoren können auch die Gruppen einrichten, die Teams zugeordnet sind, um an Access-Bewertungen teilzunehmen. Für [Zugriffs](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)Überprüfungen erhalten die Gruppenbesitzer regelmäßige Mahnungen, um die Mitglieder eines Teams zu überprüfen. Die Zugriffsüberprüfungen beinhalten Empfehlungen, die es für Gruppenbesitzer einfacher machen, ihren regelmäßigen Bestätigungsprozess durchlaufen.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Entscheidungspunkte | Erfordert Ihre Organisation einen konsistenten Prozess zum Verwalten der Mitgliedschaft in einem oder mehreren Teams? <br> Erfordert Ihre Organisation Besitzer oder die Mitglieder selbst, Ihre fortgesetzte Mitgliedschaft in einem oder mehreren Teams regelmäßig zu rechtfertigen? <br> Erfordert Ihre Organisation eine Genehmigung für Benutzer und Gäste, um Zugriff auf Ressourcen wie Teams, Gruppen, SharePoint-Websites und apps zu anfordern? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Die nächsten Schritte? | Dokumentieren Sie die Anforderungen Ihrer Organisation für jedes Team oder bestimmte Teams für das Ablaufdatum der Mitgliedschaft.<br>Planen Sie, wie Ihre Organisation Teams, Gruppen, SharePoint-Websites und-apps in Access-Paketen bündeln kann.<br>Planen Sie, welche Personen wie der Vorgesetzte des anfragenden, ein Projektmanager, ein Sponsor für eine verbundene Organisation oder ein Sicherheitsbeauftragter in Ihrer Organisation Zugriffsanforderungen genehmigen oder verweigern müssen. |

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

| Funktion | Details | Azure AD Premium-Lizenz erforderlich | Entscheidung |
|:-|:-|:-|:-|
| Access-Rezensionen | Einrichten von Zugriffsüberprüfungen, um die Mitgliedschaft bestimmter Teams in regelmäßigen Abständen erneut zu zertifizieren | P2 | TBD |
| Berechtigungsverwaltung | Einrichten des Zugriffs Pakets, damit Benutzer und Gästezugriff auf Teams anfordern können | P2 | TBD |

> [!NOTE]
> Weitere Informationen zu den [erforderlichen Lizenzen finden](https://azure.microsoft.com/pricing/details/active-directory/)Sie unter Unterstützung bei der Planung.

### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access-Rezensionen](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Team-Funktionsverwaltung

Ein weiterer wichtiger Aspekt von Governance und Lifecycle Management für Teams ist die Möglichkeit, zu steuern, auf welche Funktionen Ihre Benutzer zugreifen können. Sie können Messaging-, Besprechungs-und Anruffeatures sowohl auf der Microsoft 365-oder Office 365-Organisationsebene als auch pro Benutzer verwalten.


|         |         |
|---------|---------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation das Einschränken von Teamfunktionen für den gesamten Mandanten?</li><li>Erfordert Ihre Organisation das Einschränken von Teamfunktionen für bestimmte Benutzer?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation, um die Funktionen von Teams auf Mandanten-und Benutzerebene zu begrenzen.</li><li>Planen Sie, Ihre spezifischen Anforderungen als Teil des Rollouts für Teams zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Benutzer über das Verhalten zu informieren, das Sie erwarten können.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Fokusbereiche der Featureverwaltung in Teams

Teams bietet granulare Funktionen zum Steuern von Messaging-, Besprechungs-, Anruf-und Live-Ereignis Features und mehr über Richtlinien. Verschiedene Richtlinien können standardmäßig oder pro Benutzer nach Bedarf für Ihre Organisation auf alle Benutzer angewendet werden. 

Detaillierte Listen aller Einstellungen, einschließlich technischer Anleitungen zur Implementierung für Ihre Organisation, finden Sie in den folgenden Artikeln:

- [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
- [Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Private Kanäle in Microsoft Teams](private-channels.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
- [Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)

Darüber hinaus können Sie die Moderation für einen Kanal einrichten und bestimmten Benutzern Moderatorfunktionen zur Verfügung stellen, damit Sie steuern können, wer Kanal Beiträge erstellen und darauf antworten kann. Weitere Informationen finden Sie unter [Einrichten und Verwalten von Kanal Moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Sicherheit und Compliance

Teams basiert auf den erweiterten Sicherheits-und Compliance-Funktionen von Microsoft 365 und Office 365 und unterstützt die Überwachung und Berichterstellung, die Compliance-Inhaltssuche, e-Discovery, rechtliche Aufbewahrungs-und Aufbewahrungsrichtlinien.

> [!Important]
> Wenn Ihre Organisation über Konformitäts-und Sicherheitsanforderungen verfügt, lesen Sie den ausführlichen Inhalt zu diesem Thema im Artikel [Übersicht über Sicherheit und Compliance in Microsoft Teams](security-compliance-overview.md).

## <a name="related-topics"></a>Verwandte Themen

[Governance-Schnellstart für Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
