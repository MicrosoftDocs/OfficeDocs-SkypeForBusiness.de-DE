---
title: Planen der Governance in Microsoft Teams – Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In diesem Artikel erfahren Sie, wie Sie die Implementierung von Governancefunktionen in Teams planen.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e51b85e7ecf8efc61c6ca78ca16e4366372885
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756231"
---
# <a name="plan-for-governance-in-teams"></a>Planen der Governance in Teams.

Teams bietet eine umfangreiche Reihe von Tools zum Implementieren aller Governancefunktionen, die Ihre Organisation möglicherweise benötigt. Dieser Artikel führt IT-Profis dazu, die richtigen Fragen zu stellen, um ihre Anforderungen für governance zu bestimmen und wie sie diese erfüllen können. 

> [!Tip] 
> Schauen Sie sich die folgende Sitzung an, um mehr über Governance in Microsoft Teams zu erfahren: [Governance, Verwaltung und Lebenszyklus in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Gruppen- und Teamerstellung, Benennung, Klassifizierung und Gastzugriff

Möglicherweise müssen Sie in Ihrer Organisation strenge Steuerelemente implementieren, um zu bestimmen, wie Teams benannt und klassifiziert werden, ob Gäste als Teammitglieder hinzugefügt werden können und wer Teams erstellen kann. Sie können diese Bereiche mithilfe von Azure Active Directory (Azure AD) und Vertraulichkeitsbeschriftungen konfigurieren. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation eine bestimmte Benennungskonvention für Teams?</li><li>Benötigen Teamersteller die Möglichkeit, Teams organisationsspezifische Klassifizierungen zuzuordnen?</li><li>Müssen Sie die Möglichkeit einschränken, Gäste zu Teams pro Team hinzuzufügen?</li><li>Muss in Ihrer Organisation eingeschränkt werden, wer Teams erstellen kann?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Teamerstellung, Benennung, Klassifizierung und Gastzugriff.</li><li>Planen Sie, diese Anforderungen im Rahmen Ihres Teams-Rollouts zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Teams-Benutzer über das verhalten zu informieren, das sie erwarten können.</li></ul>|

> [!NOTE]
> Weitere Informationen zum Festlegen dieser Richtlinien und zu den benötigten Lizenzen finden Sie unter Weitere Informationen zur Planung ihrer [Planung.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Das Einschränken der Gruppen- und Teamerstellung kann die Produktivität Ihrer Benutzer beeinträchtigen, da viele Microsoft 365- und Office 365-Dienste erfordern, dass Gruppen erstellt werden, damit der Dienst funktioniert. Weitere Informationen finden Sie unter Warum steuern, wer [Microsoft 365-Gruppen erstellt.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>Weitere Informationen

Nachdem Sie Ihre Anforderungen festgelegt haben, können Sie sie mithilfe von Azure AD-Steuerelementen implementieren. Technische Anleitungen zum Implementieren dieser Einstellungen finden Sie unter:

- [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Erzwingen einer Benennungsrichtlinie für Microsoft 365-Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Benennungsrichtlinie für Microsoft 365-Gruppen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Verwenden von Vertraulichkeitsbeschriftungen zum Schützen von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Optionen für das Ende des Lebenszyklus für Gruppen, Teams und Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Ablauf, Aufbewahrung und Archivierung von Gruppen und Teams

Ihre Organisation hat möglicherweise zusätzliche Anforderungen zum Festlegen von Richtlinien für Ablauf-, Aufbewahrungs- und Archivierungsteams- und Teamdaten (Kanalnachrichten und Kanaldateien). Sie können Gruppenablaufrichtlinien so konfigurieren, dass der Lebenszyklus der Gruppen- und Aufbewahrungsrichtlinien automatisch verwaltet wird, um Informationen nach Bedarf zu erhalten oder zu löschen, und Sie können Teams archivieren (auf schreibgeschützten Modus festlegen), um eine Point-in-Time-Ansicht eines Teams zu erhalten, das nicht mehr aktiv ist. Beachten Sie, dass archivierte Teams weiterhin die Ablaufrichtlinie angewendet haben und gelöscht werden können, sofern sie nicht ausgeschlossen oder verlängert werden.

|-          |-           |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation die Angabe eines Ablaufdatums für Teams?</li><li>Erfordert Ihre Organisation, dass bestimmte Datenaufbewahrungsrichtlinien auf Teams angewendet werden?</li><li>Erwartet Ihre Organisation die Möglichkeit, inaktive Teams zu archivieren, um den Inhalt in einem schreibgeschützten Zustand zu erhalten?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für den Ablauf des Teams, die Datenaufbewahrung und archivierung.</li><li>Planen Sie, diese Anforderungen im Rahmen Des Rollouts von Teams zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Teams-Benutzer über das verhalten zu informieren, das sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

|Funktion |Details |Azure AD Premium-Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Ablaufrichtlinie |Verwalten Sie den Lebenszyklus von Microsoft 365-Gruppen, indem Sie eine Ablaufrichtlinie festlegen. |P1 |TBD|
|Aufbewahrungsrichtlinie |Speichern oder löschen Sie Daten für einen bestimmten Zeitraum, indem Sie Aufbewahrungsrichtlinien für Teams im Security & Compliance Center festlegen. **Hinweis:** Für die Verwendung dieses Features ist eine Lizenzierung von Microsoft 365 oder Office 365 Enterprise E3 oder höher erforderlich. |Nein |TBD |
|Archivieren und Wiederherstellen |Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, Sie es aber zur Referenz behalten oder in Zukunft reaktivieren möchten. |Nein |TBD |

> [!Note]
> Der Gruppenablauf ist ein Azure AD Premium-Feature. Damit dieses Feature verfügbar ist, muss Ihr Mandant über ein Abonnement von Azure AD Premium und Lizenzen für den Administrator verfügen, der die Einstellungen und die Mitglieder der betroffenen Gruppen konfiguriert.

#### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zum Implementieren dieser Einstellungen finden Sie unter:

- [Einrichten des Ablaufs von Microsoft 365-Gruppen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Richten Sie Aufbewahrungsrichtlinien für Teams ein.](retention-policies.md)

- [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Gruppen- und Teammitgliedschaftsverwaltung

Eine konsequente Verwaltung von Mitgliedern projektbasierter oder eingeschränkter Gruppen ist für Teams erforderlich, die schnelles Onboarding und Offboarding oder Benutzer und Gäste erfordern. Möglicherweise muss Ihre Organisation auch sicherstellen, dass alle aktuellen Mitglieder über die geschäftliche Begründung verfügen, in einem Team zu sein. Das Verwalten von Mitgliedern kann schwierig sein, da Teambesitzer Gruppen verlassen können und Benutzer Gruppen normalerweise nicht von sich aus verlassen, wenn ein Projekt endet oder wenn sie Rollen ändern. Die beste Methode zum Verwalten der Gruppenmitgliedschaft, die Benutzern den Zugriff bei Bedarf ermöglicht, aber dafür sorgt, dass die Gruppe kein Risiko für unangemessenen Zugriff hat, besteht in zwei Bezirksprozessen: Berechtigungsverwaltung und Zugriffsüberprüfungen.

[Mit der Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) können Sie eine Stellvertretung an eine andere Person, z. B. einen Projektmanager, erstellen, um alle erforderlichen Ressourcen, einschließlich Teammitgliedschaften, in einem einzigen Paket zu sammeln. Sie können auch definieren, wer Anforderungen stellen kann: entweder Benutzer in Ihrem Mandanten oder aus anderen verbundenen Organisationen. Der Projektmanager erhält Zugriffsanforderungen in seiner E-Mail und genehmigt oder verweigert Anforderungen im MyAccess-Portal. Administratoren können die Bedingungen für den Zugriff so konfigurieren, dass sie ein Ablaufdatum oder einen Zeitraum enthalten, bis der Benutzer oder Gast aus dem Team entfernt wird, sofern der Zugriff nicht verlängert wird. Administratoren können auch die Gruppen einrichten, die Teams zugeordnet sind, um an Zugriffsüberprüfungen teilnehmen zu können. Bei [Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)erhalten die Gruppenbesitzer regelmäßige Erinnerungen, um die Mitglieder eines Teams zu überprüfen. Access-Rezensionen enthalten Empfehlungen, die es Gruppenbesitzern einfacher machen, ihren regulären Attestierungsprozess zu durchgehen.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Entscheidungspunkte | Erfordert Ihre Organisation einen konsistenten Prozess zum Verwalten der Mitgliedschaft in einem oder mehreren Teams? <br> Erfordert Ihre Organisation besitzer oder die Mitglieder selbst, ihre fortgesetzte Mitgliedschaft in einem oder mehreren Teams regelmäßig zu rechtfertigen? <br> Erfordert Ihre Organisation eine Genehmigung für Benutzer und Gäste, um Zugriff auf Ressourcen wie Teams, Gruppen, SharePoint-Websites und Apps anfordern zu können? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Nächste Schritte? | Dokumentieren Sie die Anforderungen Ihrer Organisationen für jedes Team oder bestimmte Teams für den Ablauf der Mitgliedschaft.<br>Planen Sie, wie Ihre Organisation Teams, Gruppen, SharePoint-Websites und Apps in Zugriffspaketen bündeln kann.<br>Planen Sie, welche Personen, z. B. der Vorgesetzte des Antragsgebers, ein Projektmanager, ein Sponsor für eine verbundene Organisation oder ein Sicherheitsbeauftragter in Ihrer Organisation, Zugriffsanforderungen genehmigen oder verweigern müssen. |

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

| Funktion | Details | Azure AD Premium-Lizenz erforderlich | Entscheidung |
|:-|:-|:-|:-|
| Access-Rezensionen | Einrichten von Zugriffsüberprüfungen, um die Mitgliedschaft bestimmter Teams in regelmäßigen Intervallen zu reertfizieren | P2 | TBD |
| Berechtigungsverwaltung | Setup access package to allow users and guests to request access to teams | P2 | TBD |

> [!NOTE]
> Um Ihnen bei der Planung zu helfen, [erfahren Sie mehr darüber, welche Lizenzen sie benötigen.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zum Implementieren dieser Einstellungen finden Sie unter:

- [Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access-Rezensionen](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Featureverwaltung von Teams

Ein weiterer wichtiger Aspekt des Governance- und Lebenszyklusmanagements für Teams ist die Möglichkeit, zu steuern, auf welche Features Ihre Benutzer zugreifen können. Sie können Nachrichten-, Besprechungs- und Anruffunktionen verwalten, entweder auf Microsoft 365- oder Office 365-Organisationsebene oder pro Benutzer.


|-        |-        |
|---------|---------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation das Einschränken von Teams-Features für den gesamten Mandanten?</li><li>Muss Ihre Organisation die Features von Teams für bestimmte Benutzer einschränken?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation zum Einschränken von Teams-Features auf Mandanten- und Benutzerebene.</li><li>Planen Sie, Ihre spezifischen Anforderungen im Rahmen Ihres Teams-Rollouts zu implementieren.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um die Teams-Benutzer über das verhalten zu informieren, das sie erwarten können.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Fokusbereiche der Featureverwaltung von Teams

Teams bietet detaillierte Funktionen zum Steuern von Nachrichten, Besprechungen, Anrufen und Liveereignisfeatures und vielem mehr über Richtlinien. Unterschiedliche Richtlinien können standardmäßig oder pro Benutzer auf alle Benutzer angewendet werden, wie es von Ihrer Organisation erforderlich ist. 

Ausführliche Listen aller Einstellungen, einschließlich technischer Anleitungen zur Implementierung dieser Einstellungen für Ihre Organisation, finden Sie in den folgenden Artikeln:

- [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
- [Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Private Kanäle in Microsoft Teams](private-channels.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
- [Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)

Darüber hinaus können Sie moderation für einen Kanal einrichten und bestimmten Benutzern Moderatorfunktionen geben, damit sie steuern können, wer Kanalbeiträge erstellen und darauf reagieren kann. Weitere Informationen finden Sie unter Einrichten und Verwalten der Kanalmoderation [in Microsoft Teams.](manage-channel-moderation-in-teams.md)

## <a name="security-and-compliance"></a>Sicherheit und Compliance

Teams baut auf den erweiterten Sicherheits- und Compliancefunktionen von Microsoft 365 und Office 365 auf und unterstützt Überwachungs- und Berichterstellungs-, Complianceinhaltssuche, E-Discovery, Rechtliche Aufbewahrungs- und Aufbewahrungsrichtlinien.

> [!Important]
> Wenn Ihre Organisation Compliance- und Sicherheitsanforderungen hat, lesen Sie den ausführlichen Inhalt zu diesem Thema im Artikel Übersicht über Sicherheit und [Compliance in Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Verwandte Themen

[Governance-Schnellstart für Teams](teams-adoption-governance-quick-start.md)

[Microsoft 365-Lizenzierungsleitfade für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
