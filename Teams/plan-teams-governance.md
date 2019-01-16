---
title: Planen der Governance in Microsoft Teams – Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Erhalten Sie Informationen zur Planung der Implementierung von Governance-Funktionen in Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: db98b9b5ab460207b2dd9f9a793a486402ec29fd
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326866"
---
# <a name="plan-for-governance-in-teams"></a>Planen der Steuerung in Teams

Teams bietet einen umfassenden Satz von Tools, die alle Governance-Funktionen, die Ihre Organisation erfordern möglicherweise implementieren. In diesem Artikel wird beschrieben, wie IT-Spezialisten die richtigen Fragen zum Ermitteln der ihren Anforderungen für die Unternehmensleitung und wie diese entsprechen. 

> [!Tip] 
> Sehen Sie sich die folgenden Sitzung lernen Sie mehr über Steuerung in Microsoft-Teams: [Steuerung und Verwaltung Lebenszyklus im Microsoft-Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Erstellung von Gruppe und Team, benennen, Klassifizierung und Gastzugriff

Ihre Organisation erfordern möglicherweise, exakte Steuerelemente wie Teams mit dem Namen und klassifiziert werden, ob Gäste als Teammitglieder hinzugefügt werden können und Benutzer, Teams erstellen können zu implementieren. Sie können jeden dieser Bereiche mithilfe von Azure Active Directory (AD Azure) konfigurieren. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Ist Ihre Organisation eine spezielle Benennungskonvention für Teams erforderlich?</li><li>Benötigen Teams Ersteller die Möglichkeit, Teams organisationsspezifischen Klassifikationen zugewiesen?</li><li>Benötigen Sie die Möglichkeit, Teams auf Basis-Team Gäste hinzufügen einschränken?</li><li>Benötigt Ihre Organisation die einschränken, wer Teams erstellen kann?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Team erstellen, benennen, Klassifizierung und Gastzugriff.</li><li>Planen der Implementierung von diesen Anforderungen als Teil des Teams nahezubringen.</li><li>Kommunizieren Sie und veröffentlichen Sie Ihrer Richtlinien um Teams Benutzer des Verhaltens zu informieren, die sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie in der folgenden Tabelle, um den Anforderungen der Organisation zu erfassen.

|Funktion |Beschreibung |Azure AD-Premium <br> Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Team Benennungsrichtlinie | Verwenden Sie Präfix-Suffix-basierten, benutzerdefinierte blockierte Wörter. |P1 |TBD |
|Team-Klassifizierung |Klassifikationen in der Teams zuweisen. |P1 |TBD |
|Team Gastzugriff |Ermöglichen oder verhindern, dass Gäste Teams hinzugefügt wird. |Nein |TBD |
|Teamerstellung |Team Erstellung für Administratoren zu begrenzen. |Nein |TBD|
|Teamerstellung |Team erstellen auf Mitglieder der Gruppe Sicherheit zu begrenzen. |P1 |TBD|

> [!NOTE]
> Um im voraus, [erfahren Sie mehr über das Festlegen dieser Richtlinien und welche Lizenzen benötigten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)planen.
> 
> [!NOTE]
> Beschränken der Gruppe und Teamwebsites erstellen kann Produktivität der Benutzer und verlangsamen, da viele Office 365-Dienste erfordern, dass für das Funktionieren des Diensts Gruppen erstellt werden. Zusätzliche Informationen navigieren Sie zu, und erweitern Sie, [Warum steuern, wer auf Office 365 Gruppen erstellt](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Weitere Informationen

Nachdem Sie den Standarddateispeicherort bestimmt haben, können Sie diese mithilfe von Azure AD-Steuerelementen implementieren. Technische Anleitungen diese Einstellungen zu implementieren finden Sie unter:

-   [Azure Active Directory-Cmdlets zum Konfigurieren von gruppeneinstellungen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

-   [Erzwingen Sie eine Namensrichtlinie für Office 365-Gruppen im Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

-   [Office 365 Gruppen naming Policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Gruppe und Team Ablauf, Aufbewahrung und Archivierung

Ihre Organisation möglicherweise zusätzliche Anforderungen für das Einrichten von Richtlinien für Ablauf, Archivierung, und Archivierung teams und teams, die Daten (DDE Kanalnachrichten und Channel-Dateien). Sie können Ablaufrichtlinien Gruppe, um die automatische Verwaltung des Lebenszyklus der Gruppe und Aufbewahrung Richtlinien für das beibehalten oder Löschen von Informationen nach Bedarf, und konfigurieren Sie können Teams archivieren (diese auf schreibgeschützt festgelegt), die eine Point-in-Time-Ansicht eines Teams beibehalten, der nicht mehr aktiv.

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Benötigt Ihre Organisation die ein Ablaufdatum für Teams angeben?</li><li>Benötigt Ihre Organisation bestimmte Daten Aufbewahrungsrichtlinien auf Teams angewendet werden?</li><li>Erwartet Ihrer Organisation erfordern die Möglichkeit zum Archivieren von inaktiven Teams den Inhalt in einem schreibgeschützten Zustand erhalten?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Team Ablauf, Daten Aufbewahrung und Archivierung.</li><li>Planen der Implementierung von diesen Anforderungen als Teil des Teams nahezubringen.</li><li>Kommunizieren Sie und veröffentlichen Sie Ihrer Richtlinien um Teams Benutzer des Verhaltens zu informieren, die sie erwarten können.</li></ul>|

> [!TIP]
> Verwenden Sie in der folgenden Tabelle, um den Anforderungen der Organisation zu erfassen.

|Funktion |Beschreibung |Azure AD-Premium-Lizenz erforderlich |Entscheidung |
|---------|---------|---------|---------|
|Ablaufrichtlinie |Verwalten des Lebenszyklus der Office 365-Gruppen eine Ablaufrichtlinie festlegen. |P1 |TBD|
|Aufbewahrungsrichtlinie |Beibehalten oder Löschen von Daten für einen bestimmten Zeitraum Aufbewahrungsrichtlinien für Teams im Compliance Center Sicherheit & festlegen. **Hinweis**: Diese Funktion erfordert Lizenzierung der Office 365 Enterprise E3 oder höher. |Nein |TBD |
|Archivieren und Wiederherstellen |Archivieren Sie ein Team aus, wenn nicht mehr aktiv ist, aber es als Referenz beibehalten oder in der Zukunft erneut aktivieren möchten. |Nein |TBD |

> [!Note]
> Gruppe Ablauf ist eine Azure AD Premium-Funktion. Für dieses Feature verfügbar sein soll müssen Ihre Mandanten ein Abonnement für Azure AD Premium und Lizenzen für den Administrator, die die Einstellungen und die Mitglieder der betroffenen Gruppen konfiguriert.

#### <a name="additional-information"></a>Weitere Informationen

Technische Anleitungen diese Einstellungen zu implementieren finden Sie unter:

-   [Einrichten von Office 365 Gruppen Ablauf](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

-   [Einrichten von Teams Aufbewahrungsrichtlinien](retention-policies.md).

-   [Archivierung oder Wiederherstellung ein Team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Teams Feature management

Ein weiterer wichtiger Aspekt der Unternehmensleitung und Anwendungslebenszyklus-Verwaltung für Teams ist die Möglichkeit, die steuern, welche Features Zugriff auf Ihre Benutzer haben. Sie können messaging, der Einhaltung und Anruffunktionen, entweder auf die Office 365-Mandanten Ebene oder pro Benutzer verwalten. 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Benötigt Ihre Organisation die Einschränkung von Teams Features für Ihre gesamte Mandanten?</li><li>Benötigt Ihre Organisation die Teams Features für bestimmte Benutzer beschränken?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Dokumentieren Sie die Anforderungen Ihrer Organisation für Teams Features Ebene der Mandanten und Benutzer beschränken.</li><li>Ihre spezifischen Anforderungen als Teil des Teams nahezubringen implementieren möchten.</li><li>Kommunizieren Sie und veröffentlichen Sie Ihrer Richtlinien um Teams Benutzer des Verhaltens zu informieren, die sie erwarten können.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams Featurebereiche Management Fokus

Teams bietet detaillierte Funktionen zur Kontrolle messaging, Besprechung, aufrufende und live Ereignis Features und mehr über Richtlinien. Verschiedene Richtlinien können auf alle Benutzer in der Standardeinstellung oder pro Benutzer nach Bedarf Ihrer Organisation angewendet werden. 

Eine detaillierte Liste aller Einstellungen, einschließlich technische Anleitungen für Implementierungsmethode für Ihre Organisation finden Sie unter den folgenden Artikeln:

-   [Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation](enable-features-office-365.md)
-   [Verwalten von Teams während des Übergangs auf die neuen Microsoft-Teams und Skype für Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
-   [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>Sicherheit und compliance

Teams basiert auf Erweiterte Sicherheit und Compliance-Funktionen von Office 365 und Überwachung und reporting, Inhaltssuche Compliance, eDiscovery, rechtlichen Aufbewahrungspflicht und Aufbewahrungsrichtlinien unterstützt. 

> [!Important]
> Wenn Ihre Organisation die Einhaltung von Vorschriften und sicherheitsanforderungen verfügt, Informationen Sie zur fundierte bereitgestellt, in der [Übersicht über Sicherheit und Einhaltung von Vorschriften in Microsoft-Teams,](security-compliance-overview.md)Artikel in diesem Thema.

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
