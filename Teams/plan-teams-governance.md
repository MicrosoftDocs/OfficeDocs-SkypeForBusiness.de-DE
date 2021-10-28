---
title: Planen der Governance in Microsoft Teams – Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: In diesem Artikel erfahren Sie, wie Sie die Implementierung von Governancefunktionen in Ihrer Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 947ced749db6922d756400e99fb61035c5a86600
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605651"
---
# <a name="plan-for-governance-in-teams"></a>Planen der Governance in Teams.

Teams bietet eine reihe von Tools zum Implementieren aller Governancefunktionen, die Ihre Organisation möglicherweise benötigt. Dieser Artikel führt IT-Profis an, die richtigen Fragen zu stellen, um ihre Anforderungen an Governance und ihre Erfüllung zu bestimmen. 

> [!Tip] 
> Schauen Sie sich die folgende Sitzung an, um mehr über Governance in Ihrer Microsoft Teams zu erfahren: [Governance, Verwaltung](https://aka.ms/teams-governance) und Lebenszyklus in Microsoft Teams

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Gruppen- und Teamerstellung, Benennung, Klassifizierung und Gastzugriff

Ihre Organisation erfordert möglicherweise, dass Sie strenge Kontrollen für den Namen und die Classified von Teams, darüber, ob Gäste als Teammitglieder hinzugefügt werden können und wer Teams erstellen kann, implementieren. Sie können diese Bereiche mithilfe von Azure Active Directory (Azure AD) und Vertraulichkeitsbeschriftungen konfigurieren. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Entscheidungspunkte|<ul><li>Ist für Ihre Organisation eine bestimmte Benennungskonvention für Teams erforderlich?</li><li>Benötigen Teamersteller die Möglichkeit, organisationsspezifische Klassifizierungen zu Teams zuzuordnen?</li><li>Müssen Sie die Möglichkeit zum Hinzufügen von Gästen zu Teams pro Team einschränken?</li><li>Ist es für Ihre Organisation erforderlich, die Personen zu beschränken, die Teams erstellen können?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation an Teamerstellung, Benennung, Klassifizierung und Gastzugriff.</li><li>Planen Sie die Implementierung dieser Anforderungen im Rahmen Ihrer Teams Bereitstellung.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um Teams Benutzer über das zu erwartende Verhalten zu informieren.</li></ul>|

> [!NOTE]
> Um Ihnen bei der Planung im Voraus zu helfen, erfahren Sie mehr über das [Festlegen dieser Richtlinien und die erforderlichen Lizenzen.](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Das Einschränken der Gruppen- und Teamerstellung kann die Produktivität Ihrer Benutzer beeinträchtigen, da viele Microsoft 365- und Office 365-Dienste die Erstellung von Gruppen erfordern, damit der Dienst funktioniert. Weitere Informationen finden Sie unter [Planen von Governance in Teams.](/microsoft-365/solutions/manage-creation-of-groups)


#### <a name="additional-information"></a>Weitere Informationen

Nachdem Sie Ihre Anforderungen festgelegt haben, können Sie sie mithilfe von Azure AD implementieren. Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Azure Active Directory-Cmdlets zum Konfigurieren von Gruppeneinstellungen](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Erzwingen einer Benennungsrichtlinie für Microsoft 365 in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 Benennungsrichtlinie für Gruppen](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365 gruppen und SharePoint Websites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Optionen für das Ende des Lebenszyklus für Gruppen, Teams und Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Ablauf, Aufbewahrung und Archivierung für Gruppen und Teams

Möglicherweise gibt es in Ihrer Organisation zusätzliche Anforderungen für das Festlegen von Richtlinien für Ablauf, Aufbewahrung und Archivierung von Teams und Teamdaten (Kanalnachrichten und Kanaldateien). Sie können Gruppenablaufrichtlinien konfigurieren, um den Lebenszyklus der Gruppe automatisch zu verwalten, und Aufbewahrungsrichtlinien, um Informationen nach Bedarf zu erhalten oder zu löschen, und Sie können Teams archivieren (sie auf schreibgeschützten Modus festlegen), um eine Point-in-Time-Ansicht eines Teams zu erhalten, das nicht mehr aktiv ist. Beachten Sie, dass für archivierte Teams weiterhin die Ablaufrichtlinie angewendet wird und gelöscht werden kann, es sei denn, sie wurden ausgeschlossen oder verlängert.

|-          |-           |
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Erfordert Ihre Organisation die Angabe eines Ablaufdatums für Teams?</li><li>Erfordert Ihre Organisation, dass bestimmte Aufbewahrungsrichtlinien für Daten auf Teams angewendet werden?</li><li>Erwartet Ihre Organisation, dass die Möglichkeit zum Archivieren inaktiver Teams erforderlich ist, um die Inhalte in einem schreibgeschützten Zustand zu archivieren?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation an Teamablauf, Datenaufbewahrung und Archivierung.</li><li>Planen Sie die Implementierung dieser Anforderungen im Rahmen Ihrer Teams Bereitstellung.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um Teams Benutzer über das zu erwartende Verhalten zu informieren.</li></ul>|

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

|Funktion |Details |Azure AD Premium lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Ablaufrichtlinie |Verwalten Sie den Lebenszyklus Microsoft 365 Gruppen, indem Sie eine Ablaufrichtlinie festlegen. |P1 |TBD|
|Aufbewahrungsrichtlinie |Speichern oder Löschen von Daten für einen bestimmten Zeitraum durch Festlegen von Aufbewahrungsrichtlinien für Teams im Security & Compliance Center. **Hinweis:** Die Verwendung dieses Features erfordert eine Lizenzierung von Microsoft 365 oder Office 365 Enterprise E3 oder höher. |Nein |TBD |
|Archivieren und Wiederherstellen |Archivieren Sie ein Team, wenn es nicht mehr aktiv ist, Sie es jedoch zu Referenz-bzw. reaktivieren möchten. |Nein |TBD |

> [!Note]
> Gruppenablauf ist ein Azure AD Premium Feature. Damit dieses Feature verfügbar ist, muss Ihr Mandant über ein Abonnement für Azure AD Premium und Lizenzen für den Administrator verfügen, der die Einstellungen konfiguriert, sowie für die Mitglieder der betroffenen Gruppen.

#### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Richten Sie die Microsoft 365 Ablauf für Gruppen ein.](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Richten Sie Teams Aufbewahrungsrichtlinien ein.](retention-policies.md)

- [Archivieren oder Wiederherstellen eines Teams.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Verwaltung von Gruppen- und Teammitgliedschaften

Eine durchgängige Verwaltung von Mitgliedern projektbasierter oder eingeschränkter Gruppen ist für Teams erforderlich, die schnelles Onboarding und Offboarding oder Benutzer und Gäste erfordern. Möglicherweise muss Ihre Organisation auch sicherstellen, dass alle aktuellen Mitglieder über die geschäftliche Begründung verfügen, um in einem Team zu sein. Das Verwalten von Mitgliedern kann schwierig sein, da Teambesitzer die Gruppe verlassen können und benutzer in der Regel Gruppen nicht auf eigene Hand verlassen, wenn ein Projekt endet oder die Rollen wechseln. Die beste Möglichkeit zum Verwalten der Gruppenmitgliedschaft, die Benutzern den Zugriff bei Bedarf ermöglicht, aber sicherstellen kann, dass keine Gefahr eines unangemessenen Zugriffs besteht, besteht in zwei Prozessprozessen im Bezirk: Verwaltung von Berechtigungen und Überprüfungen des Zugriffs.

[Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview) ermöglicht es Ihnen, eine Stellvertretung an eine Person, z. B. einen Projektmanager, zu delegieren, um alle erforderlichen Ressourcen, einschließlich Teammitgliedschaften, in einem einzigen Paket zu sammeln. Sie können auch definieren, wer Anforderungen stellen kann: entweder Benutzer in Ihrem Mandanten oder von anderen verbundenen Organisationen. Der Projektmanager erhält in seiner E-Mail Zugriffsanforderungen und genehmigt oder verweigert Anforderungen im MyAccess-Portal. Administratoren können die Bedingungen für den Zugriff so konfigurieren, dass ein Ablaufdatum oder -zeitraum angegeben wird, bis der Benutzer oder Gast aus dem Team entfernt wird, sofern der Zugriff nicht verlängert wird. Administratoren können auch die Teams zugeordneten Gruppen für die Teilnahme an Zugriffsüberprüfungen einrichten. Bei [der Überprüfung des Zugriffs](/azure/active-directory/governance/access-reviews-overview)erhalten die Gruppenbesitzer regelmäßige Erinnerungen zum Überprüfen der Mitglieder eines Teams. Access-Überprüfungen enthalten Empfehlungen, die es Gruppenbesitzern erleichtern, ihren regulären Nachweisprozess zu durchgehen.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Entscheidungspunkte | Erfordert Ihre Organisation einen einheitlichen Prozess zum Verwalten der Mitgliedschaft in einem oder mehreren Teams? <br> Erfordert Ihre Organisation Besitzer oder die Mitglieder selbst, um ihre fortgesetzte Mitgliedschaft in einem oder mehreren Teams in regelmäßigen Abständen zu rechtfertigen? <br> Erfordert Ihre Organisation eine Genehmigung für Benutzer und Gäste, um Zugriff auf Ressourcen wie Teams, Gruppen, SharePoint Websites und Apps an bitten zu können? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Nächste Schritte? | Dokumentieren Sie die Anforderungen Ihrer Organisation für jedes Team oder bestimmte Teams für den Ablauf der Mitgliedschaft.<br>Planen Sie, wie Ihre Organisation Teams, Gruppen, SharePoint Websites und Apps in Zugriffspaketen bündeln kann.<br>Planen Sie, welche Personen wie der Manager des Antrags, ein Projektmanager, ein Sponsor für eine verbundene Organisation oder ein Sicherheitsbeauftragter in Ihrer Organisation Zugriffsanforderungen genehmigen oder verweigern müssen. |

> [!TIP]
> Verwenden Sie die folgende Tabelle, um die Anforderungen Ihrer Organisation zu erfassen.

| Funktion | Details | Azure AD Premium lizenz erforderlich | Entscheidung |
|:-|:-|:-|:-|
| Access-Rezensionen | Einrichten von Zugriffsüberprüfungen, um in regelmäßigen Abständen die Mitgliedschaft bestimmter Teams zu befizieren | P2 | TBD |
| Berechtigungsverwaltung | Setup-Zugriffspaket, um Benutzern und Gästen das Anfordern des Zugriffs auf Teams zu ermöglichen | P2 | TBD |

> [!NOTE]
> Erfahren Sie mehr darüber, welche Lizenzen benötigt werden, um Ihnen bei der [Planung im Voraus zu helfen.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen zur Implementierung dieser Einstellungen finden Sie unter:

- [Berechtigungsverwaltung](/azure/active-directory/governance/entitlement-management-overview)
- [Access-Rezensionen](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams von Features

Ein weiterer wichtiger Aspekt der Governance und des Lebenszyklusmanagements für Teams ist die Möglichkeit zu steuern, auf welche Features Ihre Benutzer Zugriff haben. Sie können Funktionen für Messaging, Besprechungen und Anrufe entweder auf Microsoft 365 Office 365 Organisation oder pro Benutzer verwalten.


|-        |-        |
|---------|---------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Muss Ihre Organisation die Teams für den gesamten Mandanten einschränken?</li><li>Ist es für Ihre Organisation erforderlich, Teams features für bestimmte Benutzer zu beschränken?</li></ul>|
| ![Ein Symbol, das die nächsten Schritte darstellt.](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation zur Beschränkung Teams Features auf Mandanten- und Benutzerebene.</li><li>Planen Sie die Implementierung Ihrer spezifischen Anforderungen im Rahmen Ihres Teams Rollouts.</li><li>Kommunizieren und veröffentlichen Sie Ihre Richtlinien, um Teams Benutzer über das zu erwartende Verhalten zu informieren.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams der Featureverwaltung

Teams bietet granulare Funktionen zum Steuern von Nachrichten, Besprechungen, Anrufen und Liveereignisfunktionen und vieles mehr über Richtlinien. Standardmäßig können auf alle Benutzer oder je nach Bedarf für Ihre Organisation unterschiedliche Richtlinien angewendet werden. 

Detaillierte Listen aller Einstellungen, einschließlich technischer Anleitungen zu deren Implementierung für Ihre Organisation, finden Sie in den folgenden Artikeln:

- [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
- [Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Private Kanäle in Microsoft Teams](private-channels.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)
- [Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)

Darüber hinaus können Sie moderation für einen Kanal einrichten und bestimmten Benutzern Moderatorfunktionen bieten, damit sie steuern können, wer Kanalbeiträge erstellen und auf sie reagieren kann. Weitere [Informationen finden Sie unter](manage-channel-moderation-in-teams.md) Einrichten und Verwalten der Microsoft Teams In-Moderieren.

## <a name="security-and-compliance"></a>Sicherheit und Compliance

Teams auf den erweiterten Sicherheits- und Compliancefunktionen von Microsoft 365 und Office 365 und unterstützt Überwachung und Berichterstellung, Complianceinhaltssuche, E-Discovery, gesetzliche Aufbewahrungspflicht und Aufbewahrungsrichtlinien.

> [!Important]
> Wenn Ihre Organisation Compliance- und Sicherheitsanforderungen erfüllt, lesen Sie den ausführlichen Inhalt zu diesem Thema im Artikel Übersicht über Sicherheit und Compliance [in Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Verwandte Themen

[Governance-Schnellstart für Teams](teams-adoption-governance-quick-start.md)

[Microsoft 365 Lizenzierungsrichtlinien für Sicherheit und & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->