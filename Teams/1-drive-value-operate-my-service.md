---
title: Betriebshandbuch für Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Aufgaben und Aktivitäten, die für die Dienstverwaltung von Teams erforderlich sind, einschließlich überwachung des Dienstzustands sowie Bewertung und Sicherstellung der Netzwerkqualität und -nutzung.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5684ad62107fa61af7c9f2f22c6f15b4bfe1da30
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112651"
---
# <a name="operate-my-service"></a>Verwenden des Diensts

Dieser Artikel enthält einen Überblick über die Anforderungen für den erfolgreichen Betrieb von Cloud voice services für Ihre Organisation. Wenn Sie Ihre Cloud voice services ordnungsgemäß verwenden, können Sie sicher sein, dass Sie eine qualitativ hochwertige und zuverlässige Benutzererfahrung für Ihre Organisation bereitstellen.

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Im Handbuch "Vorgänge" erhalten Sie einen Überblick über alle Aufgaben und Aktivitäten, die als Teil der Dienstverwaltungsfunktion für Microsoft Teams erforderlich sind.

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Teams-Dienst umfasst Microsoft 365 oder Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt werden (z. B. Netzwerke).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Möglicherweise haben Sie bereits Prozesse und Aufgaben implementiert, die vorhandenen Diensten zugeordnet sind. Dies bedeutet, dass Sie Ihre aktuellen Prozesse wahrscheinlich erweitern können, wenn Sie die Dienstverwaltung heute planen, um Teams in Zukunft zu unterstützen.

Die Dienstverwaltung umfasst alle Aktivitäten und Prozesse, die an der Verwaltung von Teams end-to-end beteiligt sind. Wie bereits erwähnt, sind einige Komponenten der Dienstverwaltung – die Infrastruktur, die der Microsoft 365- oder Office 365-Dienst selbst umfasst – in der Verantwortung von Microsoft, während Sie, der Kunde, gegenüber Ihren Benutzern zur Verwaltung der verschiedenen Aspekte von Teams, des Netzwerks und der von Ihnen angegebenen Endpunkte verantwortlich sind.

Die Aufgaben und Aktivitäten in diesem Leitfaden sind in acht Kategorien unterteilt, wie in der folgenden Abbildung dargestellt. Jede dieser Kategorien wird in den folgenden Abschnitten erweitert.

![Ein Diagramm mit einer Liste von Kategorien von Aufgaben und Aktivitäten](media/operate-my-service-image1.png "Ein Diagramm mit einer Liste der Kategorien von Aufgaben und Aktivitäten, die die Dienstverwaltung für Teams umfasst. Das Diagramm zeigt außerdem, dass die Dienstverwaltung größtenteils eine Kundenaufgabe ist.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie Vorgänge für Teams implementiert werden.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Lesen Sie den Betriebsleitfaden vollständig.</li><li>Implementieren Sie eine Betriebsstrategie, die den Zielen Ihrer Organisation entspricht, um die Qualität und Zuverlässigkeit von Cloud-Voice-Workloads zu gewährleisten.</li><li>Überprüfen [Sie Die Anrufqualität überwachen.](monitor-call-quality-qos.md)</li><li> Implementieren Sie eine Betriebsstrategie, um regelmäßig Überprüfungen zur Qualität der Benutzererfahrung durchzuführen, um sicherzustellen, dass Ihre Cloud-Sprachbereitstellung mit spitzen Funktionen ausgeführt wird.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die Planung, die Sie für Vorgänge während der Envisionsphase unternehmen, ist von entscheidender Bedeutung, da die Betriebsaktivitäten beginnen, wenn die ersten Pilotbenutzer aktiviert sind. In diesem Leitfaden werden die Aktivitäten und Aufgaben aufgeführt, die täglich, wöchentlich, monatlich oder bei Bedarf ausgeführt werden müssen, um eine qualitativ hochwertige Teams-Bereitstellung zu erhalten. Dieser Leitfaden enthält Kenntnisse und Anleitungen zum Ausführen dieser kritischen Aktivitäten und Aufgaben.

Eine wichtige Komponente einer erfolgreichen Bereitstellung besteht in der Sicherstellung, dass die Planung, die Sie zu Beginn der Envisionsphase durchführen, auch die Ermittlung umfasst, wer für die Durchführung bestimmter Aktivitäten zuständig ist. Nachdem Sie herausfinden, welche Aufgaben und Aktivitäten für Ihre Bereitstellung gelten, müssen sie verstanden und von den Gruppen oder Personen gefolgt werden, die Sie ihnen zuweisen.

Jedes von Ihnen identifizierte Team muss die ermittelten Aufgaben und Zuständigkeiten überprüfen und vereinbaren und mit der Vorbereitung beginnen. Dies kann schulungen und bereitschaftsbereit sein, Aktualisierungen des Personalplans bereitstellen oder sicherstellen, dass externe Anbieter bereit für die Bereitstellung sind.

Die in diesem Handbuch definierten Aktivitäten und Rollen sollten in den meisten Szenarien gültig sein, aber jede #A0 ist eindeutig. Daher können Sie dieses Handbuch als Ausgangspunkt verwenden, um die Aktivitäten und Standardrollen an Ihre Anforderungen anzupassen.

Stellen Sie sicher, dass jedes berücksichtigungsfähige Team über ein gutes Verständnis der Aktivitäten verfügt, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass jedes Team seine Verantwortlichkeit in Ihrer Organisation akzeptiert und abschreibt, bevor der erste Pilot gestartet wird.

Nachdem eine Vereinbarung besteht, sollten die entsprechenden Teams mit der Operationalisierung ihrer Rollen beginnen.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument, um die Übung zur funktionsbereiten Rollenzuordnung zu vereinfachen.</li><li>Treffen Sie sich mit den jeweiligen Supportteams, um jedem Element in der Liste der erforderlichen Aktivitäten Namen zuzuordnen.</li><li>Gewinnen Sie Akzeptanz oder Abmelden für die zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams über die entsprechenden Schulungen, Bereitschaft und Ressourcen verfügen, um die erforderlichen Aktivitäten zu vervollständigen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Abhängigkeiten von Teams-Diensten

Microsoft Teams bringt Technologien in Microsoft 365 oder Office 365 zusammen, um einen Hub für Teamarbeit zu bieten. Beispiele hierfür sind:

-   Azure Active Directory (Azure AD) stellt Authentifizierungs- und Autorisierungsdienste für Teams bereit.

-   Exchange Online bietet erweiterte Features wie rechtliches In-Hand-Halten und E-Discovery.

-   SharePoint Online bietet die Möglichkeit zum Freigeben von Dateien in Kanälen, und OneDrive for Business stellt einen Mechanismus zum Freigeben von Dateien in einem privaten Chat zur Verfügung.

Organisationen können auch vorhandene Investitionen in lokale Infrastruktur nutzen. Beispielsweise können vorhandene lokale Active Directory-Konten für die Authentifizierung verwendet werden, indem Azure AD Connect verwendet wird. Bestimmte Versionen von Exchange Server können an Stelle von Exchange Online verwendet werden.

Diese Technologien kommen zusammen, um benutzern eine umfassende, kollaborative und intelligente Kommunikationssuite zu bieten. Diese enge Integration ist ein wesentlicher Vorteil von Teams, aber sie führt auch zu einer Anforderung an die Dienstverwaltung für alle diese Technologien.

Dieser Leitfaden befasst sich mit den wichtigsten Schwerpunktbereichen zum Verwalten des Teams-Diensts. Höchstwahrscheinlich verfügen Sie über Dienstverwaltungspläne für die unterstützenden Technologien, von der Teams abhängt. Andern falls nicht, müssen Sie auch geeignete Dienstverwaltungspläne für diese Technologiekomponenten (lokal und online) erstellen. Dadurch können Sie sicherstellen, dass Ihre Benutzer eine qualitativ hochwertige und zuverlässige Erfahrung mit Teams haben.

#### <a name="references"></a>Referenzen 

[Übersicht über Microsoft Teams](teams-overview.md)

[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

[Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Aktivitäten des Betriebsleitfadens

In den folgenden Abschnitten finden Sie einen Überblick über die Aktivitäten, die erforderlich sind, um den Microsoft Teams-Dienst erfolgreich zu betreiben. Sie enthalten Verweise auf Tools, Kontextinformationen und zusätzliche Inhalte, die Ihnen helfen sollen, die Aktivität zu verstehen und bereitschaftsbezogene Initiativen zu unterstützen.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Überwachen des Dienstzustands

Es ist wichtig, dass Sie den Gesamtzustand des Microsoft Teams-Diensts verstehen, damit Sie andere Personen in Ihrer Organisation proaktiv über alle Ereignisse, die sich auf den Dienst auswirkt, warnen können. Wie zuvor beschrieben, ist Teams von anderen Microsoft 365- oder Office 365-Diensten wie Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business abhängig. Aus diesem Grund ist es ebenso wichtig, dass Sie den Zustand der abhängigen Dienste überwachen.

Integrieren Sie diese Aktivität in Ihren Vorfallverwaltungsprozess, um Benutzer, den Helpdesk und Ihre Betriebsteams proaktiv zu informieren, um sich auf die Handhabung von Benutzereskalationsvorgängen vorzubereiten.

In den folgenden Abschnitten werden die Tools beschrieben, die Sie zum Überwachen von Dienstvorfällen nutzen [können,](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) die sich auf den Teams-Dienst auswirken. Eine Zusammenfassung der Vorteile der einzelnen Tools und der Verwendung der einzelnen Tools ist in der folgenden Tabelle enthalten.

| Überwachungstool                       | Vorteile                                            | Verwendungs-                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 Admin Center                     | Verfügbar auf jedem Gerät mit einem unterstützten Browser. | Verwenden Sie diese Verwendung, wenn Sie keine Echtzeitbenachrichtigungen benötigen.                                          |
| Microsoft 365- oder Office 365-Administrator-App                  | Stellt Pushbenachrichtigungen für Ihr mobiles Gerät zur  | Verwenden Sie diese, wenn Sie unterwegs über Dienstvorfälle benachrichtigt werden müssen.                  |
| Microsoft System Center               | Integration in Microsoft System Center.           | Verwenden Sie diese Funktion, wenn Sie erweiterte Überwachungsfunktionen und Benachrichtigungsunterstützung benötigen.                       |
| Microsoft 365- oder Office 365-Dienstkommunikations-API | Programmgesteuerter Zugriff auf den Dienstzustand von Microsoft 365 oder Office 365.   | Verwenden Sie dies, wenn Sie die Integration in ein Überwachungstool eines Drittanbieters benötigen oder eine eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, denen die Rolle des **globalen Administrators** oder **Dienstadministrators** zugewiesen ist, können den Dienstzustand anzeigen.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Überwachung mit dem Microsoft 365 Admin Center

Das [Microsoft 365 Admin Center](https://portal.office.com/) stellt ein [Dienstintehashboard](https://portal.office.com/adminportal/home#/servicehealth) zur Verfügung, in dem Sie den aktuellen Status des Teams-Diensts zusätzlich zu den abhängigen Diensten anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachung mit der mobilen App

Die Microsoft 365- oder Office 365-Administrator-App ist unter Apple iOS, Android und Windows (PC und Mobile) verfügbar. Die App stellt Dienstadministratoren Informationen über den Dienstzustand und anstehende Änderungen zur Verfügung. Die App unterstützt Pushbenachrichtigungen, die Sie fast unmittelbar nach der Benachrichtigung informieren können. Dies hilft Ihnen, über den Status, den Status und alle anstehenden Änderungen am Dienst auf dem laufenden zu bleiben. Die Benachrichtigungsunterstützung macht sie zum empfohlenen Überwachungstool für Administratoren. Weitere Informationen finden Sie unter:

[Office 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Herunterladen der mobilen Office 365 Admin App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Überwachung mit Microsoft System Center

Microsoft System Center ist eine integrierte Verwaltungsplattform, mit der Sie Rechenzentrums-, Clientgeräte- und Hybrid-Cloud-IT-Umgebungen verwalten können. Office 365-Administratoren, die System Center verwenden, haben jetzt die Möglichkeit, das Office 365 Management Pack zu importieren, wodurch alle Dienstkommunikationen in Operations Manager in System Center angezeigt werden können. Mit diesem Tool erhalten Sie Zugriff auf den Status Ihrer abonnierten Dienste, aktive und aufgelöste Dienstvorfälle und Ihre Nachrichtencenterkommunikation (anstehende Änderungen). Weitere Informationen finden Sie im folgenden [Blogbeitrag.](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)

Wenn Sie System Center verwenden, um den Dienstzustand (und die abhängigen Dienste) von Teams zu überwachen, können Sie das Management Pack weiter anpassen, um bestimmte Gruppen oder Personen zu benachrichtigen oder zu benachrichtigen, die identifiziert wurden, um auf Vorfälle zu reagieren.
Diese Gruppen können Dienstbesitzer, Helpdesks, Supportgruppen der zweiten und dritten Ebene sowie Vorfallmanager in Ihrer Organisation umfassen.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachung für erweiterte Szenarien

Sie können den Dienstzustand und anstehende Änderungen überwachen, indem Sie die Office 365 Service Communications-API für den Zugriff auf den Office 365-Dienstzustand und Programmänderungen nutzen. Verwenden Sie diese API, um ein eigenes Überwachungstool zu erstellen oder Ihre vorhandenen Überwachungstools mit der Office 365-Dienstkommunikation zu verbinden, was möglicherweise die Überwachung Ihrer Umgebung vereinfacht. Weitere Informationen finden Sie unter [Office 365 für Enterprise-Entwickler.](https://developer.microsoft.com/office)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                               | Cadence   | Team zugewiesen |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen des Dienstzustands | Überwachen Sie den Dienstzustand (und die abhängigen Dienste) von Microsoft Teams proaktiv mithilfe der verfügbaren Tools. Abhängige Dienste sind: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Echtzeit |               |
| Vorfallbenachrichtigung  | Benachrichtigen Sie interne Projektbeteiligten über Ereignisse, die sich auf den Teams-Dienst auswirken. Interne Projektbeteiligten können Benutzer, Helpdesks und Vorfallmanager sein.                                                                          | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Überprüfen des Office 365-Dienstzustands](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Dienstinte health and continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von Organisationsänderung

Microsoft Teams ist ein cloudbasierter Dienst. Dazu kommt die Möglichkeit, neue Features und Funktionen in einem schnellen Tempo bereitzustellen. Die Bereitstellung fortlaufender Innovationen bietet einen offensichtlichen Vorteil für Organisationen, doch müssen diese Änderungen in Ihrer Organisation entsprechend verwaltet werden, um Benutzerwehren oder Eskalationen gegenüber Ihrem Helpdesk zu vermeiden.

Updates für Teams werden automatisch für Ihre Benutzer ausgeführt. Ihre Benutzer verfügen immer über die neuesten Clients und Features, die im Teams-Dienst verfügbar sind. Es ist nicht möglich, den Rollout von Teams-Updates für Ihre Benutzer zu verwalten, daher ist es von entscheidender Bedeutung, änderungen durch effektive Kommunikationsprogramme, Schulungen und Einführungsprogramme zu verwalten. Wenn Ihre Benutzer die Änderung kennen, sich über die Vorteile ausbilden und in der Lage sind, die neuen Funktionen zu nutzen, können sie sich schneller anpassen und die Änderung &mdash; begrüßen.

### <a name="monitoring-for-change"></a>Überwachung auf Änderungen

Der erste Schritt in der Änderungsverwaltung besteht in der Überwachung der änderungen, die für Teams geplant sind. Die beste Quelle für die Überwachung dieser Änderungen ist die [Office 365-Roadmap,](https://products.office.com/business/office-365-roadmap)in der Features aufgeführt werden, die derzeit in der Entwicklung sind, für Kunden eingeführt oder vollständig gestartet wurden. Sie können mithilfe des bereitgestellten Filters nach teamsspezifischen Features suchen oder die Roadmap zur weiteren Analyse in eine Excel-Datei herunterladen. Für jedes Feature enthält die Roadmap eine kurze Beschreibung sowie das voraussichtliche Veröffentlichungsdatum.

Im [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)erfahren Sie mehr über bewährte Methoden, Trends und Neuigkeiten zu Microsoft Teams-Produktupdates. Erwarten Sie, dass hier wichtige Featureupdates für Teams angekündigt werden. Sie können den Blog auch über einen RSS-Feed abonnieren. Sie können den [RSS-Feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) dann direkt zu einem Teams-Kanal hinzufügen, sodass alle wichtigen Nachrichten direkt in Teams zugestellt werden.

Alle veröffentlichten Features sind in den [Versionshinweisen für Microsoft Teams dokumentiert.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Hier finden Sie eine Liste der Features, die für Desktop-, Web- und mobile Geräte veröffentlicht wurden. Der gleiche Satz von Versionshinweisen ist auch auf der Registerkarte Neues in **der** [Hilfe verfügbar.](get-help-in-microsoft-teams.md)

Machen Sie sich mit den verfügbaren Ressourcen vertraut, und stellen Sie sicher, dass Sie die entsprechenden Besitzer zur Überwachung auf Änderungen zuweisen.

### <a name="planning-for-change"></a>Planen von Änderungen

Da Sie nun über bevorstehende Änderungen am Teams-Dienst wissen, besteht der nächste Schritt in der Vorbereitung und Planung entsprechend. Bewerten Sie jede Änderung, um zu bestimmen, welche Änderungen die Kommunikation mit Benutzern erfordern, Bewusstseinskampagnen, Schulungen für Supportteams oder -benutzer oder Funktionsauswertungs- und Einführungskampagnen. Dies ist die primäre Rolle eines Änderungsverwaltungsteams in Ihrer Organisation. Im Folgenden finden Sie eine Sammlung von Beispieltabellen, die Ihnen bei der Planung von Änderungen helfen können.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloudaufzeichnung (Veröffentlichungsdatum: Januar 2018)

**Allgemeine Nachverfolgung**

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Rechtliche Überprüfung   | Abgeschlossen     | Dieses Feature ist eine Voraussetzung für das Onboarding des Schulungsteams. | Projektteam  |

**Verwaltung technischer Änderungen**

|       Ändern der Bereitschaft       | Status |                      Notizen/nächste Schritte                      |    Besitzer     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     ERFORDERLICHE IT-Änderungen      |  Ja   | Der Administrator muss die Aufzeichnung nur für identifizierte Benutzer aktivieren. | Supportteam |
| Technische Bereitschaft abgeschlossen |  Ja   |                                                            | Supportteam |
|                              |        |                                                            |              |

**Benutzeränderungsverwaltung** 

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Auswirkungen des Benutzers                  | Niedrig                  |                                                                 |                        |
| Benutzerbereitschaft erforderlich      | Ja                  |                                                                 |                        |
| Kommunikation bereit         | Nein                   | Kommunikations-E-Mails wurden entworfen – ausstehend.            | Kommunikationsteam    |
| Schulung bereit               | Ja                  | Die Schulung nutzt vorhandenes Microsoft-Video.                | Schulungsteam          |

**Statusspur**

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Veröffentlichungsstatus               | in Bearbeitung          | Ausstehende Überprüfung durch den Sponsor der Geschäftsleitung.               | Change Management Team |
| Release sign-off             |                      |                                                                 |                        |
| Veröffentlichungsdatum                 |                      |                                                                 |                        |

Weitere Informationen zur Planung der Änderungsverwaltung mit Teams finden Sie unter [Erstellen einer Änderungsverwaltungsstrategie für Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                                | Cadence   | Team zugewiesen |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitor für Änderungen     | Überwachen Sie auf bevorstehende Änderungen am Microsoft Teams-Dienst.                                                                                                                                                                   | Täglich     |               |
| Planen von Änderungen    | Bewerten und planen Sie neue Features und Funktionen, einschließlich Kommunikationsplänen, Bewusstseinskampagnen und Schulungen.                                                                                                     | Nach Bedarf |               |
| Benutzerbereitschaft             | Führen Sie gezielte Kommunikations-, Bewusstseins- oder Schulungskampagnen durch, um sicherzustellen, dass die Benutzer für die bevorstehende Änderung bereit sind.                                                                                                        | Nach Bedarf |               |
| Supportteambereitschaft | Führen Sie gezielte Kommunikations-, Bewusstseins- oder Schulungskampagnen durch, um sicherzustellen, dass das Supportteam bereit ist. Supportteams können das "white glove"-Team, Helpdesks, Support der Stufe 2 oder Stufe 3, externe Partner und vieles mehr umfassen. | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten der Nutzung von Teams

Nachdem der erste Pilot gestartet wurde, ist es wichtig, einen regelmäßigen Trittfrequenz zum Messen der tatsächlichen Nutzung von Teams zu erstellen. Auf diese Weise kann Ihre Organisation Einblicke in die Ausrichtung der tatsächlichen Nutzung an die Nutzung gewinnen, die Sie während der Envision-Phase vorhergesagt haben. Obwohl sich dieser Abschnitt auf die Nutzung von Teams konzentriert, sollte dies Teil einer breiteren Anstrengung zur Gesamtmessung und Bewertung der Office 365-Nutzung sein.

Die häufige Überprüfung der Nutzung zu beginn der Bereitstellung bietet Ihnen die Möglichkeit:

-   Überprüfen Sie, ob Benutzer Teams verwenden.

-   Identifizieren Sie potenzielle Herausforderungen bei der Einführung, bevor kritische Probleme in der gesamten Organisation auftreten.

-   Verstehen Sie, ob es Unterschiede zwischen den Anforderungen an die Envision-Phase und der tatsächlichen Nutzung gibt.

Wenn die Nutzung nicht ihren Fälligkeitsermaus darstellt, kann dies auf ein Bereitstellungsproblem oder eine nicht ordnungsgemäß ausgeführte Einführungsplanung oder ein anderes Problem hindehnen. Je nach dem tatsächlichen Grund für die geringe Nutzung muss der Dienstadministrator mit den zugehörigen Teams zusammenarbeiten, um Nutzungsbarrieren zu beseitigen.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Messen der Nutzung mit dem Microsoft 365 Admin Center

Nutzungsdaten von Teams sind im Dashboard "Berichterstellung" verfügbar. Die Nutzungsdaten von Teams finden Sie in drei verschiedenen Berichten. Der erste Bericht bietet eine produktübergreifende Ansicht, wie Benutzer mithilfe der verschiedenen Dienste in Office 365 kommunizieren und zusammenarbeiten. Dieser Bericht finden Sie hier: [Bericht aktiver Office 365-Benutzer](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Die anderen beiden Berichte sind teamsspezifisch und bieten weitere Details zur Nutzung von Teams aus Benutzer- und Gerätesicht. Beide Berichte finden Sie hier:

[Microsoft Teams – Gerätenutzungsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams – Benutzeraktivitätsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Auf die Nutzungsberichte im Admin Center können Personen  zugreifen, denen eine rolle des globalen Administrators oder eine produktspezifische Administratorrolle **(Exchange-Administrator,** **Skype for Business-Administrator,** SharePoint-Administrator) zugewiesen **wurde.**

Darüber hinaus steht **die** Rolle des Lesers Berichte für Benutzer zur Verfügung, die Zugriff auf die Berichte benötigen, aber keine Aufgaben ausführen, die Berechtigungen auf Administratorebene erfordern. Sie weisen diese Rolle zu, um nutzungsberichte an alle Beteiligten zu geben, um die Einführung zu überwachen und zu unterstützen. Weitere Informationen zu den verschiedenen verfügbaren Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Bewerten der Nutzung

Nachdem Sie das Berichtsdashboard zum Messen der Nutzung verwendet haben, ist es wichtig, die gemessene Nutzung mit allen wichtigen Erfolgsindikatoren (Key Success Indicators, KSIs) zu vergleichen, die Sie während der Envisionsphase des Projekts definiert haben. Sie können ein KSI definieren, das möglicherweise als aktive Nutzung definiert ist, oder ein KSI, das indirekt mit der aktiven Nutzung verknüpft ist.

Es ist wichtig, alle Abweichungen zwischen der tatsächlichen und der geplanten Nutzung zu identifizieren, bevor Sie den Rollout auf weitere Websites oder Benutzer fortsetzen. Wahrscheinlich identifizieren Sie organisationsorganisatorische Lernergebnisse als Teil dieser Aktivität, die Sie nutzen können, um sicherzustellen, dass beim nächsten Batch von Websites oder Benutzern nicht dieselben Probleme auftreten.

Zunächst sollten Sie genau bestimmen, ob es sich um eine Einführung oder ein technisches Problem handelt. Beginnen Sie, indem Sie die folgenden Elemente untersuchen, um zu ermitteln, wo das Problem liegt.

1.  Überprüfen Sie die Qualität, indem Sie eine Überprüfung der Qualität der Benutzererfahrung durchführen (weitere Informationen finden Sie unter Verbessern und Überwachen der Anrufqualität für [Teams).](monitor-call-quality-qos.md)

2.  Arbeiten Sie mit dem Helpdeskteam zusammen, um zu überprüfen, ob es keine trendenden technischen Probleme gibt, die verhindern, dass Benutzer auf den Dienst zugreifen oder diesen nutzen können. Wenn Problemtrends vorhanden sind, verwenden Sie den Abschnitt zur Problembehandlung für Endpunkte weiter in diesem Artikel, um zu versuchen, das Problem zu beheben, bevor Sie den Support ins Land setzen. [](#endpoint-troubleshooting)

3.  Arbeiten Sie mit dem Schulungs- und Einführungsteam zusammen, um direktes Feedback von Benutzern zu sammeln (siehe Bewerten der Benutzerstimmung weiter weiter in diesem Artikel), und um die Effektivität von Bewusstseins- und Adoptionsaktivitäten zu überprüfen. [](#assess-user-sentiment)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität                         | Beschreibung                                                                                                                      | Cadence   | Team zugewiesen |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Messen der Nutzung (Aktivierungsphase) | Messen und bewerten Sie die Nutzung von Teams, da Websites während der Aktivierungsphase weiterhin onboarded sind. Beheben Sie Nutzungsprobleme nach Bedarf. | Wöchentlich    |               |
| Messen der Nutzung (Phase des Laufwerkwerts)                           | Messen und bewerten Sie die Nutzung von Teams in der Phase "Drive Value" (nach Abschluss der Bereitstellung). Beheben Sie Nutzungsprobleme nach Bedarf. | Zweiwochen  |               |
| Plan zur Aktualisierung der Einführung             | Aktualisieren Sie Ihren Einführungsplan basierend darauf, wie sich die gemessene Nutzung mit Ihren Planungszielen vergleicht.                                         | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Informationen zum Microsoft 365 Admin Center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Bewerten der Benutzerstimmung

Das Verständnis der Benutzerstimmung kann als wichtiger Indikator für die Verdingung des Erfolgs Ihrer Teams-Bereitstellung fungieren. Benutzerfeedback kann Änderungen in Ihrer Organisation anfingen. Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder der Art und Weise umfassen, in der Sie Ihren Benutzern Support anbieten.

Es ist wichtig, frühzeitig Feedback zu erhalten und die Einschätzung der Benutzerstimmung während des gesamten Lebenszyklus des Projekts und darüber hinaus fortzufahren. Verwenden Sie die folgenden Anleitungen, um das Intervall zu bestimmen, in dem Ihre Organisation Feedback sucht:

-   **Anfang des Projekts:** Wenn Sie die Benutzerstimmung zu Beginn des Projekts bewerten, können Sie sich frühzeitig ein Bild davon machen, wie ihre Benutzer ihre Teams-Erfahrung einschätzen.

-   **Nach wichtigen Meilensteinen:** Durch das Sammeln von Feedback während des gesamten Projektlebenszyklus können Sie die Benutzerstimmung kontinuierlich messen und bei Bedarf Änderungen vornehmen. Dies ist besonders nach wichtigen Meilensteinen hilfreich.

-   **Projektabschluss:** Wenn Sie die Benutzerstimmung am Ende eines Projekts bewerten, erfahren Sie, wie gut Sie fertig sind und wo noch Arbeit zu erledigen ist, und Sie können die Ergebnisse mit der vorherigen Umfrage vergleichen.

-   **Fortlaufend:** Die Benutzerstimmung wird weiterhin unbegrenzt gemessen. Änderungen in der Benutzerstimmung können auf Änderungen in der Umgebung Ihrer Organisation oder auf Änderungen am Teams-Dienst fällig sein. Wenn Sie die Benutzerstimmung in regelmäßigen Abständen abarbeiten, können Sie verstehen, wie gut Ihre Dienstverwaltungsteams arbeiten und wie Ihre Organisation auf Änderungen im Teams-Dienst reagiert.

Die Benutzerstimmung kann mit vielen verschiedenen Methoden bewertet werden. Dazu können E-Mail-Umfragen, persönliche oder telefonische Vorstellungsgespräche gehören oder einfach nur einen Feedbackkanal in Teams oder Yammer. Weitere Informationen finden Sie unter [Bewährte Methoden für Benutzerfeedbackmethoden in Microsoft Teams.](best-practices-feedback.md)

Sie können auch einen branchenweiten Ansatz verwenden, um die Benutzerstimmung mit dem Namen Net Promotor Score (NPS) zu bewerten. Dies wird im folgenden Abschnitt beschrieben.

### <a name="nps"></a>NPS 

Net Promoter Score (NPS) ist eine branchenweite Kundenbindungsmetrik und ein guter Ansatz zur Bewertung der Benutzerstimmung. NPS kann berechnet werden, indem zwei Fragen gestellt werden: "Wie wahrscheinlich ist es, dass Sie Teams einem Kollegen empfehlen?", gefolgt von der Frage "Warum?"

NPS ist ein Index zwischen -100 und 100, der die Bereitschaft eines Kunden misst, das Produkt oder die Dienstleistung eines Unternehmens zu empfehlen. NPS basiert auf einer anonymen Umfrage, die benutzern per E-Mail oder auf andere elektronischem Weg zugestellt wird. NPS misst die Loyalität zwischen einem Anbieter und einem Verbraucher. Es besteht nur aus einer Frage, die Benutzer fragt, wie sie ihre Erfahrung von 1 bis 10 bewerten können, mit der Möglichkeit, zusätzliche Kommentare zu geben. Die Benutzer werden dann basierend auf den folgenden Bewertungen klassifiziert:

-   9 oder 10 sind Promoter: Loyale Enthusiasten, die Ihren Dienst bewerben und andere befeuern.

-   7 oder 8 sind passiv: Zufrieden, aber unenthusiastisch, anfällig für andere Dienste oder Angebote.

-   Von 1 bis 6 sind "Detractors": Unzufriedene Kunden, die Ihren Dienst beschädigen und das Wachstum behindern können.

![Ein Diagramm, das die NPS-Skala veranschaulicht](media/operate-my-service-image2.png "In diesem Diagramm wird die NPS-Skala veranschaulicht. Es wird gezeigt, dass Die Rangfolge von 0 bis 6 Verfolger sind, 7 bis 8 passive und 9 bis 10 Projektträger sind.")

Obwohl die Basis-NPS-Nummer nützlich ist, erhalten Sie den größten Nutzen aus der Analyse von Benutzerkommentaren. Sie helfen Ihnen zu verstehen, warum der Benutzer Teams anderen Personen empfehlen würde (oder nicht). Diese Kommentare können wertvolles Feedback liefern, um den Projekt- oder Servicemanagementteams zu helfen, die Anpassungen zu verstehen, die erforderlich sind, um einen qualitativ hochwertigen Dienst zu bieten.

Zum Bereitstellen von NPS-Umfragen für Ihre Organisation können Sie Ihr bevorzugtes Onlineumfragetool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf Aufgaben

| Aktivität              | Beschreibung                                                                                                                                                                         | Cadence   | Team zugewiesen |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Bewerten der Benutzerstimmung | Erfassen und bewerten Sie die Benutzerstimmung mithilfe von Umfragen oder Vorstellungsgesprächen oder über einen Feedbackkanal in Teams oder Yammer.                                                                 | Nach Bedarf |               |
| Aktualisieren von Einführungsplänen | Die Änderung in Ihrer Organisation basierend auf Benutzerfeedback vordrücken; Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder der Art und Weise umfassen, in der Sie Ihren Benutzern Support anbieten. | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden Yammer zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzerfeedback](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Viele wichtige Planungselemente gehen in die Optimierung, richtige Größenanpassung und Behebung Ihrer Netzwerkinfrastruktur ein, um einen qualitativ hochwertigen und effizienten Weg zum Microsoft Teams-Dienst sicherzustellen. Die Planungsaufgaben und -anforderungen werden in unseren Richtlinien für [die Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#network-readiness) behandelt. Netzwerke entwickeln sich häufig im Laufe der Zeit aufgrund von Upgrades, Erweiterungen oder anderen geschäftlichen Anforderungen. Es ist wichtig, dass Sie Ihre Anforderungen für Teams in Ihren Netzwerkplanungsaktivitäten berücksichtigen.

Obwohl die Netzwerkplanung ein kritischer Aspekt einer Teams-Bereitstellung ist, ist es ebenso wichtig sicherzustellen, dass das Netzwerk fehlerfrei bleibt und auf der Grundlage geänderter geschäftlicher oder technischer Anforderungen aktuell bleibt.

Um die Integrität Ihres Netzwerks sicherzustellen, müssen in regelmäßigen Abständen eine Reihe von Vorgängen ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität                                                       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                 | Cadence                | Team zugewiesen |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Überwachen von Office 365-IPs und URLs                                | Überwachen Sie alle Änderungen an [den Office 365-URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges) und -IP-Adressbereichen mithilfe des bereitgestellten [RSS-Feeds,](https://go.microsoft.com/fwlink/p/?linkid=236301) und initiieren Sie eine Änderungsanforderung an die entsprechenden Netzwerkgruppen.                                                                                                                                | Täglich                  |               |
| Aktualisieren des Netzwerks basierend auf Änderungen an Office 365-IPs und URLs | Aktualisieren Sie die anwendbaren Netzwerkkomponenten (Firewalls, Proxyserver, VPNs, clientseitige Firewalls und so weiter), um Änderungen an [den Office 365-URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges)und -IP-Adressbereichen widerspiegeln zu können.                                                                                                                                                              | Nach Bedarf              |               |
| Bereitstellen von Gebäudedaten                                          | Stellen Sie dem Qualitätschampion (oder den relevanten Projektbeteiligten) aktualisierte Subnetzinformationen zur Verfügung, um sicherzustellen, dass die [Gebäudedefinitionen in CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem neuesten Stand gehalten werden. | Nach Bedarf              |               |
| Implementieren von Änderungen                                               | Implementieren Sie Änderungen im Netzwerk, um änderungen der geschäftlichen und technischen Anforderungen von Teams zu unterstützen. Netzwerkelemente können Folgendes umfassen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>     | Nach Bedarf              |               |
| Netzwerküberwachung und -berichterstellung                               | Überwachen Sie das Netzwerkende bis zum Ende auf Verfügbarkeits-, Auslastungs- und Kapazitätstrends, indem Sie ihre vorhandenen Netzwerkverwaltungstools und Berichterstellungsfunktionen von Drittanbietern verwenden, die von Ihren Netzwerkanbietern zur Verfügung stehen. Verwenden Sie Trenddaten für die Netzwerkkapazitätsplanung.                                                                                                            | Täglich, wöchentlich, monatlich |               |
| Kapazitätsplanung                                              | Arbeiten Sie mit den Teams-Dienstbesitzern zusammen, um die sich ändernden geschäftlichen und technischen Anforderungen zu verstehen, die zusätzliche Kapazitätsänderungen zur Verfügung stehen könnten.                                | Nach Bedarf              |               |
| Problembehandlung und Behebung des Netzwerks                        | Unterstützen Sie die Teams-Helpdesks, Dienstbesitzer und wichtigen Projektbeteiligten bei der Problembehandlung und Behebung von Problemen im Zusammenhang mit der Konnektivität, Zuverlässigkeit oder Qualität von Teams. Netzwerkelemente können Folgendes umfassen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>    | Nach Bedarf              |               |
| Notfallwiederherstellung und Tests mit hoher Verfügbarkeit                | Führen Sie regelmäßige Tests für hohe Verfügbarkeit und Notfallwiederherstellung in der Netzwerkinfrastruktur durch, um sicherzustellen, dass die angegebenen Service Level Objectives (SLOs) oder Service Level Agreements (SLAs) für den Teams-Dienst erfüllt werden.                                                                                                                                                  | Monatlich                |               |


### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Erstellen eines Datenschemas](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und Sicherstellen der Qualität 

Alle Organisationen benötigen eine Gruppe oder einzelne Person, um für die Qualität zur Rechenschaft zu ziehen. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Die Rolle "Qualitätsmeister" wird einer Person oder Gruppe zugewiesen, die sich für die Benutzererfahrung begeistert.
Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität der Organisation kann dies eine beliebige Person oder Gruppe sein, die sich für eine hohe Benutzerfreundlichkeit ausdingt.

Der Qualitätschampion nutzt vorhandene Tools und dokumentierte Prozesse, z. B. das Anrufqualitätsdashboard (CQD), um die Benutzererfahrung zu überwachen, Qualitätstrends zu identifizieren und bei Bedarf die Behebung zu beschleunigen.
Der Qualitätsmeister sollte mit den jeweiligen Teams zusammenarbeiten, um Behebungsaktionen zu steuern, und einem Lenkungsgremium über den Fortschritt und alle offenen Probleme berichten.

Lesen Sie Verbessern und Überwachen der Anrufqualität für [Teams.](monitor-call-quality-qos.md)In diesem Artikel werden Aktivitäten beschrieben, die Anleitungen zur Bewertung und Bereitstellung von Behebungshilfen in wichtigen Bereichen bereitstellen, die die größte Auswirkung auf die Verbesserung der Benutzerfreundlichkeit haben. Die in diesem Artikel bereitgestellten Anleitungen konzentrieren sich auf die Verwendung von CQD als primäres Tool zum Melden und Untersuchen der einzelnen Bereich mit einem Fokus auf Audio, um die Akzeptanz und Wirkung zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Wir empfehlen dringend, den Qualitätsmeister frühzeitig zu nominieren. Nachdem sie benannt wurden, sollten sie [](monitor-call-quality-qos.md) damit beginnen, sich mit inhalten der Anrufqualität überwachen und den zugehörigen Schulungsmaterialien vertraut zu machen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität                               | Beschreibung                                                                                                                                                                                                                                                                                                 | Cadence                             | Team zugewiesen |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominieren und Trainieren von Qualitätsmeistern | Nominieren und schulen Sie einen Qualitätsmeister.                                                                                                                                                                                                                                                                   | Nach Bedarf                           |               |
| Durchführen von Qualitätsüberprüfungen (QERs)     | Führen Sie eine QER aus, um Qualitäts- und Zuverlässigkeitstrends zu identifizieren, definierte Ziele zu überprüfen und wichtige Projektbeteiligten in der Organisation zu melden.                                                                                                                            | Monatlich (wöchentlich während der Bereitstellungen) |               |
| Laufwerksanierung                      | Koordinieren Sie die Behebungsbemühungen in der gesamten Organisation basierend auf den FER-Bewertungen und -Ergebnissen.                                                                                                                                                                                                           | Nach Bedarf                           |               |
| Aktualisieren von Gebäudedaten in CQD            | Aktualisieren oder Hinzufügen neuer Gebäudedefinitionen in CQD, wenn Änderungen am Netzwerk vorgenommen werden (siehe [Hochladen von Gebäudeinformationen](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Nach Bedarf                           |               |
| Ausfüllen der Rolle "Qualitätsmeister"      | End-to-End-Verantwortung für die Qualität in der Organisation. Dazu gehören:<ul><li>Stellen Sie sicher, dass die QER regelmäßig durchgeführt wird.</li><li>Berichten Sie wichtigen Projektbeteiligten über den Qualitätsstatus.</li><li>Stellen Sie sicher, dass die Gebäudedatendefinitionen auf dem neuesten Stand sind.</li><li>Koordinieren Sie die Behebungsbemühungen in der gesamten Organisation, um sicherzustellen, dass Die Benutzer über eine qualitativ hochwertige Erfahrung mit Teams verfügen.</li></ul>          | Täglich                               |               |



### <a name="references"></a>Referenzen 


[Hochladen von Mandanten- und Gebäudedaten in CQD](CQD-upload-tenant-building-data.md)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft Teams-Endpunkte können als alle PCs, Macs, Tablets oder mobilen (oder anderen) Geräte definiert werden, auf der der Teams-Client ausgeführt wird. Der  Ausdrucksendpunkt umfasst nicht nur das Gerät selbst, sondern auch die Art und Weise, wie ein Benutzer eine Verbindung mit dem Gerät herstellt , z. B. mithilfe des integrierten Mikrofons oder Lautsprechers des Geräts, Ohrhörer oder eines optimierten Headsets. Nach der Bereitstellung dürfen Endpunkte nicht vergessen werden. Die Endpunkte von Teams erfordern fortlaufende Pflege und Wartung. In den folgenden Abschnitten werden bestimmte Bereiche beschrieben, auf die Sie sich konzentrieren müssen.

### <a name="endpoint-requirements"></a>Endpunktanforderungen

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die mobilen Teams-Apps werden über ihre jeweiligen App-Stores auf dem laufenden gehalten.

Der Teams-Client hat Mindestanforderungen an die zugrunde liegende Softwareplattform. Diese Anforderungen können sich im Laufe der Zeit ändern, daher ist es wichtig, dass Sie sie auf Änderungen überwachen. Der Teams-Client verfügt beispielsweise über eine iOS-Mindestversion. Wenn der Client einen Internetbrowser verwendet, muss auch der Browser auf dem aktuellen Stand gehalten werden. Eine Liste der unterstützten Plattformen finden Sie unter [Clients für Microsoft Teams erhalten.](get-clients.md)

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können sich auf die Anrufqualität auswirken und sogar verhindern, dass ein Anruf eingerichtet wird. Nachdem die entsprechenden Ausschlüsse für die Clientfirewall konfiguriert wurden, müssen sie basierend auf den Informationen in [Office 365-URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges)und -IP-Adressbereichen auf dem neuesten Stand gehalten werden. Ihr Drittanbieter hat spezifische Anleitungen zum Aktualisieren der Ausschlüsse.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Wi-Fi Treiber sind möglicherweise problematisch. Beispielsweise kann ein Treiber ein sehr aggressives Roamingverhalten zwischen Access Points haben, das zu unnötigen Zugriffspunktwechseln führen kann, was zu einer schlechten Anrufqualität führt. Ein nicht Wi-Fi treiber kann durch eine Überprüfung der Qualität der Benutzererfahrung ermittelt werden (weitere Informationen finden Sie unter Verbessern und Überwachen der Anrufqualität für [Teams).](monitor-call-quality-qos.md) Es ist wichtig, einen qualitätsgesteuerten Prozess zu implementieren, der neue treiber Wi-Fi überwacht und sicherstellt, dass sie getestet werden, bevor sie für die allgemeine Benutzerpopulation bereitgestellt werden.

### <a name="endpoint-management"></a>Endpunktverwaltung

Ein Katalog mit unterstützten Endpunkten und Schnittstellengeräten (z. B. Headsets) sollte verfügbar und gewartet werden. Dieser Katalog enthält eine Liste der genehmigten Geräte, die im Rahmen der Phasen "Envision" und "Onboard" ausgewählt und überprüft wurden. In der Regel werden bestimmte Geräte für jeden Personentyp in Ihrer Organisation ausgewählt, um die Anforderungen der Attribute dieser Persona zu erfüllen. Alle Endpunkte haben einen Lebenszyklus, und Sie müssen die lieferantenvertrags-, garantie-, ersatz-, verteilungs- und reparaturrichtlinien verwalten, die diesen Geräten zugeordnet sind.

### <a name="endpoint-troubleshooting"></a>Problembehandlung für Endpunkte

Selbst wenn Sie die vorherigen Anleitungen befolgt haben, können benutzer in Ihrer Organisation weiterhin Probleme mit Teams haben. Obwohl das Problem möglicherweise nicht mit dem Endpunkt selbst liegt, werden die Symptome des Problems normalerweise über den Client für den Benutzer angezeigt. Die folgenden Anleitungen sollen allgemeine Schritte zum Beheben des Problems enthalten. Es ist nicht als umfassendes Handbuch zur Problembehandlung gedacht. Die Schritte werden in einer bestimmten Reihenfolge bereitgestellt, müssen jedoch nicht explizit befolgt werden und sind je nach Art des Problems möglicherweise nicht anwendbar.

1.  **Überprüfen des Dienstzustands:** Das Problem, das einem Benutzer möglicherweise auftritt, kann mit einem Ereignis verknüpft sein, das sich negativ auf den Teams-Dienst oder seine abhängigen Dienste auswirkt. Im ersten Schritt wird empfohlen, dass Sie bestätigen, dass keine aktiven Dienstprobleme auftreten. Weitere Informationen finden Sie unter Überprüfen [des Office 365-Dienstzustands.](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)
    Denken Sie daran, den Status der abhängigen Dienste (z. B. Exchange, SharePoint, OneDrive for Business) zu überprüfen. Die Überwachung des Dienstzustands wird im vorherigen Abschnitt Überwachen des [Dienstzustands ausführlicher erläutert.](#monitor-service-health)

2.  **Überprüfen der Clientkonnektivität:** Konnektivitätsprobleme verursachen Funktionalität oder Anmeldeprobleme in Teams. Wir empfehlen (insbesondere für neue Websites oder Speicherorte), die Verbindung mit dem Dienst zu überprüfen. Stellen Sie sicher, dass die folgenden [Office 365-URLs und IP-Adressbereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges) für jede Website befolgt werden. Sie können das [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) verwenden, um einen Konnektivitätstest durchzuführen, um zu überprüfen, ob die Medienports für Cloud-Sprachfunktionen ordnungsgemäß geöffnet wurden. Ausführliche Schritte zum Ausführen der Konnektivitätstests finden Sie im Leitfaden [zur Netzwerkbereitschaft.](3-envision-evaluate-my-environment.md#network-readiness)

3.  **Überprüfen Sie die Liste der bekannten Probleme:** Wenden [Sie sich an Teams Troubleshooting,](/MicrosoftTeams/troubleshoot/teams) um festzustellen, ob der Benutzer von einem dieser Probleme negativ betroffen ist. Folgen Sie der bereitgestellten Problemumgehung (falls vorhanden), um das Problem zu beheben.

4.  **Besuchen Sie die Microsoft Teams-Community:** Die [Microsoft Teams-Community bietet](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) dedizierte Räume für Teams. Die Teams-Community bietet eine Diskussionsliste, Blogbeiträge und Ankündigungen, die sich um Teams herum zentriert haben. Sie können eine Frage posten oder frühere Diskussionen nach Lösungen für Ihr Problem durchsuchen.

5.  **Wenden Sie sich an den Microsoft-Support:** Sie können den Microsoft-Support kontaktieren, wenn Sie Probleme mit Teams online oder telefonisch haben. Informationen finden Sie unter [Kontaktieren des Support für Geschäftsprodukte](/microsoft-365/admin/contact-support-for-business-products).
    Für Premier-Kunden können Supportanfragen initiiert werden, indem Sie den Anweisungen unter Kontaktsupport [für Microsoft Teams (Premier-Kunden) folgen.](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität                 | Beschreibung                                                                                                                                                                                                                                                                                                                                                                     | Cadence   | Team zugewiesen |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Endpunktanforderungen    | Stellen Sie sicher, dass der Endpunkt von Teams weiterhin alle Softwareanforderungen für Teams erfüllt, die unter Clients für Microsoft Teams herunterladen [aufgeführt sind.](get-clients.md)                                                                                                                                                                                       | Monatlich   |               |
| Endpunktfirewalls       | Verwalten Sie die geeigneten Ausschlüsse für die Endpunktfirewall basierend auf den Informationen in [Office 365-URLs und -IP-Adressbereichen.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Ihr Drittanbieter hat spezifische Anleitungen zum Beibehalten der Ausschlüsse. Abonnieren Sie den [RSS-Feed,](https://support.office.com/o365ip/rss) um automatisch über Änderungen benachrichtigt zu werden. | Nach Bedarf |               |
| WLAN-Treiber            | Testen und aktualisieren Wi-Fi Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe von CQD ( Verbessern und Überwachen der[Anrufqualität für Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Nach Bedarf |               |
| Endpunktverwaltung      | Verwalten Sie den Katalog der unterstützten Endpunkte und Schnittstellengeräte (z. B. Headsets). Verwalten sie Lieferantenverträge, Garantie-, Vertriebs-, Ersatz- und Reparaturrichtlinien.                                                                                                                                                                                                        | Monatlich   |               |
| Problembehandlung für Endpunkte | Problembehandlungsaufgaben können die Überprüfung der Konnektivität, die Überprüfung der Liste bekannter Probleme, die Protokollsammlung, die Analyse und die Eskalation für den Microsoft-Support oder Drittanbieter umfassen.                                                                                                                                                                                               | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Clients für Microsoft Teams abrufen](get-clients.md)

[Microsoft Teams-Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products)

[Kontaktieren des Premier-Support](https://support.microsoft.com/premier/contacts)

[Video zur Problembehandlung in Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Microsoft Teams-Dienst bereitgestellt wurde, müssen Sie mehrere Aktivitäten im Zusammenhang mit seiner Administration ausführen. Die Aktivitäten reichen von der Verwaltung des Diensts und einzelner Benutzer bis zu Kapazitätsplanung und Bereitstellungslizenzierung und Telefonnummern. In den folgenden Abschnitten werden einige dieser allgemeinen Verwaltungsaufgaben beschrieben.

### <a name="service-administration"></a>Dienstverwaltung

Der Teams-Dienst verfügt über mehrere Einstellungen, die mandantenweit konfiguriert werden können.
An den Mandanteneinstellungen vorgenommene Änderungen wirken sich auf alle Benutzer aus, die für Teams aktiviert wurden. Eine detaillierte Liste dieser Einstellungen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation.](enable-features-office-365.md)

### <a name="user-administration"></a>Benutzerverwaltung

Um Benutzer zu unterstützen, benötigt eine Organisation möglicherweise eine beliebige Anzahl verwandter Aufgaben– die jeweiligen Aufgaben variieren von Organisation zu Organisation. Letztendlich müssen diese Aufgaben von einem Supportteam verwaltet werden, dem diese betrieblichen Aufgaben zugewiesen wurden. Die folgenden Aufgaben sind häufig erforderlich, um Benutzer in Teams zu unterstützen.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Allgemeine Aufgaben für das Telefonsystem

[[Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](./assign-change-or-remove-a-phone-number-for-a-user.md).](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Zuweisen oder Ändern einer Notfalladresse für einen Benutzer](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Allgemeine Aufgaben für Audiokonferenzen

[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Lizenzverwaltung

Wenn Ihre Organisation wächst oder verträge, ist es wichtig, dass Sie die Lizenzierung für aktuelle und zukünftige Anforderungen planen. Neben der Lizenzierung für Cloud-Sprachfunktionen[(Telefonsystem](here-s-what-you-get-with-phone-system.md) und [Audiokonferenzen)](https://products.office.com/skype-for-business/audio-conferencing)gibt es eine Basislizenz für Teams.

Für Teams sind für Telefonsystemlizenzen [zugeordnete Anrufplanlizenzen](calling-plan-landing-page.md) erforderlich. Die Lizenzierung des Anrufplans ermöglicht Ihnen, in- und/oder internationale Telefonanrufe zu machen und zu empfangen. Diese Pläne sind nutzungsbasierte Und verfügen über Minutenpools, die ihnen zugeordnet sind. Die Bereitstellung von [Guthaben für](what-are-communications-credits.md) Kommunikationen stellt sicher, dass Sie nie den Dienst auslaufen lassen.

Audiokonferenzen ermöglichen tolle Einwahlkonferenzen und heimische Einwahlkonferenzdienste. Gebührenfreie Einwahlkonferenzen oder Nicht-Inlands-Einwahlszenarien können dazu führen, dass zusätzliche Gebühren anfallen, für die Guthaben [für](what-are-communications-credits.md) Kommunikationen erforderlich sind.

Guthaben für Kommunikationen kann sowohl die Lizenzen für Anrufplan als auch Audiokonferenzen ergänzen. Sowohl Anrufplanlizenzen als auch Kommunikationsguthaben sind nutzungsbasierte Lizenzen und müssen daher entsprechend überwacht und bereitgestellt werden.

Sie können den [PstN-Nutzungsbericht verwenden,](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) um Ihre Nutzung von Anrufplanminuten und Guthaben für Kommunikationen zu überwachen. Basierend auf den Ergebnissen dieser Aktivität können Sie Ihre Lizenzierung entsprechend anpassen. In Kürze bieten wir einen Bericht für [PSTN-Minutenpools](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) an, um diese Aufgabe effektiver zu unterstützen.

### <a name="telephone-number-management"></a>Verwaltung von Telefonnummern

Es gibt zwei Methoden zum Erfassen von Nummern in Teams: Sie können Telefonnummern von einem anderen Anbieter portieren oder die Nummern direkt aus dem Nummernbestand von Microsoft bereitstellen. Beide Methoden werden unter [Abrufen von Telefonnummern für Ihre Benutzer beschrieben.](getting-phone-numbers-for-your-users.md)

Die Anzahl der Telefonnummern, die Sie aus dem Nummernbestand von Microsoft bereitstellen können, ist begrenzt. Die Grenzwerte werden durch eine Reihe von Faktoren bestimmt, die unter [Wie viele Telefonnummern können Sie erhalten? detailliert festgelegt werden.](how-many-phone-numbers-can-you-get.md)
Die Grenzwerte hängen vom Typ der Nummern ab – gebührenfreie Servicenummern, gebührenpflichtige Servicenummern und Abonnentennummern (Benutzernummern). Jedes hat eigene Grenzwerte und muss unabhängig verwaltet werden. Wenn Sie sich dem Grenzwert nähern (oder das Limit erreicht haben), können Sie eine Inkrementierung des Grenzwerts beantragen. Dieser Vorgang wird im Artikel im vorherigen Absatz beschrieben.

Es kann zu Zeiten kommen, in denen eine Zahl nicht verfügbar ist, um in einer Region bereitgestellt zu werden, in der der Dienst verfügbar ist. Informationen zum Verfahren zum Anfordern von Nummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

### <a name="team-creation-optional"></a>Teamerstellung (optional)

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigungen zum Erstellen von Microsoft 365-Gruppen und somit eines Teams in Microsoft Teams. Wenn Sie eine engere Kontrolle haben und die Erstellung neuer Teams [(und](assign-roles-permissions.md#permissions-to-create-teams) damit die Erstellung neuer Microsoft 365-Gruppen) einschränken möchten, können Sie Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Administratoren delegieren. Wenn Ihre Organisation diese Option verwenden möchte, lesen Sie den in diesem Artikel beschriebenen Prozess, um Benutzern das Übermitteln von Anforderungen zu ermöglichen, die von einem zugewiesenen Team verarbeitet werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf benötigte Aufgaben

| Aktivität                    | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                             | Cadence   | Team zugewiesen |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Dienstverwaltung      | Verwaltung mandantenweiter Teams-Einstellungen.                                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Benutzerverwaltung         | Verwaltung benutzerbasierter Einstellungen und Lizenzierung in Teams.                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Lizenzverwaltung          | Planen Sie den aktuellen und zukünftigen Bedarf für benutzer- und verbrauchsbasierte Lizenzierung (Anrufpläne und Kommunikationsguthaben), indem Sie den [Bericht "PSTN-Nutzung"](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) und den Bericht ["PSTN-Minutenpools"](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) verwenden. | Wöchentlich    |               |
| Verwaltung von Telefonnummern | Verwalten Sie die Telefonnummern, die für zukünftiges Wachstum verfügbar sind, und passen Sie die Lagerbestände an Ihre Organisationsanforderungen an.                                                                                                                                                                                                                                                                                                | Wöchentlich    |               |
| Teamerstellung (optional)    | Überprüfen und Verarbeiten von Anforderungen für die Teamerstellung.                                                                                                                                                                                                                                                                                                                                                                          | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Verbessern und Überwachen der Anrufqualität

[Die Verbesserung und Überwachung](monitor-call-quality-qos.md) der Anrufqualität für Teams umfasst eine Reihe von Aktivitäten, die Anleitungen zur Behebung in wichtigen Bereichen bewerten und bereitstellen, die die größte Auswirkung auf die Verbesserung der Benutzerfreundlichkeit haben, wie unten dargestellt.

![Diagramm der Bereiche, die während einer Überprüfung der Qualität der Erfahrung zu untersuchen sind](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während einer Überprüfung der Qualität der Benutzerfreundlichkeit zu untersuchen sind: Audio, Zuverlässigkeit und Ergebnisse der Benutzerumfrage.")

Durch die kontinuierliche Bewertung und Behebung der im Leitfaden beschriebenen Bereiche können Sie deren Potenzial verringern, sich negativ auf die Benutzerfreundlichkeit zu auswirken. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration

-   Schlechte WLAN-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Verwendung nicht optimierter oder integrierter Audiogeräte

-   Problematische Subnetze oder Netzwerkgeräte

Die unter Verbessern und Überwachen der Anrufqualität für [Teams](monitor-call-quality-qos.md) bereitgestellten Anleitungen konzentrieren sich auf die Verwendung des Anrufqualitätsdashboards (CQD) Online als primäres Tool zum Melden und Untersuchen der einzelnen beschriebenen Bereich mit einem Fokus auf Audio, um die Akzeptanz und Auswirkung zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Es wird dringend empfohlen, den Qualitätsmeister frühzeitig zu nominieren. Nachdem sie benannt wurden, sollten sie sich mit den Inhalten unter Verbessern und Überwachen der Anrufqualität [für Teams vertraut machen.](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->