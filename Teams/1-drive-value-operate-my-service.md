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
description: Aufgaben und Aktivitäten, die für Teams Dienstverwaltung erforderlich sind, einschließlich der Überwachung des Dienststatus sowie der Bewertung und Sicherstellung der Netzwerkqualität und -nutzung.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 614b3a16a5c0d59a63f06d1328c68f42e3497af5
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823420"
---
# <a name="operate-my-service"></a>Verwenden des Diensts

Dieser Artikel enthält eine Übersicht über die Anforderungen für den erfolgreichen Betrieb von Cloud-VoIP-Diensten für Ihre Organisation. Durch den ordnungsgemäßen Betrieb Ihrer Cloud-VoIP-Dienste können Sie sicher sein, dass Sie eine qualitativ hochwertige und zuverlässige Erfahrung für Ihre Organisation bereitstellen.

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Der Betriebsleitfaden bietet Ihnen einen Überblick über alle Aufgaben und Aktivitäten, die im Rahmen der Dienstverwaltungsfunktion für Microsoft Teams erforderlich sind.

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Teams-Dienst umfasst Microsoft 365 oder Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt werden (z. B. Netzwerk).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Möglicherweise haben Sie bereits Prozesse und Aufgaben implementiert, die vorhandenen Diensten zugeordnet sind. Allerdings können Sie wahrscheinlich Ihre aktuellen Prozesse erweitern, wenn Sie heute service management planen, um Teams in Zukunft zu unterstützen.

Die Dienstverwaltung umfasst alle Aktivitäten und Prozesse, die an der Verwaltung Teams Ende-zu-Ende beteiligt sind. Wie bereits erwähnt, liegen einige Komponenten der Dienstverwaltung – die Infrastruktur, die der Microsoft 365 oder Office 365 Dienst selbst umfasst – in der Verantwortung von Microsoft, während Sie, der Kunde, ihren Benutzern gegenüber verantwortlich sind, die verschiedenen Aspekte von Teams, des Netzwerks und der Von Ihnen bereitgestellten Endpunkte zu verwalten.

Die Aufgaben und Aktivitäten in diesem Leitfaden sind in acht Kategorien gruppiert, wie im folgenden Diagramm dargestellt. Jede dieser Kategorien wird in den folgenden Abschnitten erweitert.

![Ein Diagramm, das eine Liste von Kategorien von Aufgaben und Aktivitäten darstellt.](media/operate-my-service-image1.png "Ein Diagramm, das eine Liste von Kategorien von Aufgaben und Aktivitäten darstellt, die die Dienstverwaltung für Teams umfasst. Das Diagramm zeigt auch, dass die Dienstverwaltung weitgehend eine Kundenaufgabe ist.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie Vorgänge für Teams implementiert werden sollen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Lesen Sie den Betriebsleitfaden vollständig durch.</li><li>Implementieren Sie eine Betriebsstrategie, die den Zielen Ihrer Organisation entspricht, um die Qualität und Zuverlässigkeit von Cloud-VoIP-Workloads bereitzustellen.</li><li>Überprüfen sie [die Anrufqualität des Monitors](monitor-call-quality-qos.md).</li><li> Implementieren Sie eine Betriebsstrategie, um regelmäßig Quality of Experience Reviews durchzuführen, um sicherzustellen, dass Ihre Cloud-VoIP-Bereitstellung ihre Spitzenfunktionen erreicht.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die Planung, die Sie während der Planungsphase für Vorgänge vorgenommen haben, ist wichtig, da die Betriebsaktivitäten beginnen, wenn die ersten Pilotbenutzer aktiviert sind. In diesem Leitfaden werden die Aktivitäten und Aufgaben aufgeführt, die täglich, wöchentlich, monatlich oder nach Bedarf ausgeführt werden müssen, um eine qualitativ hochwertige Teams Bereitstellung aufrechtzuerhalten. Dieser Leitfaden enthält Wissen und Anleitungen zum Ausführen dieser kritischen Aktivitäten und Aufgaben.

Eine wichtige Komponente einer erfolgreichen Bereitstellung besteht darin, sicherzustellen, dass die Planung, die Sie früh in der Envision-Phase durchführen, die Bestimmung umfasst, wer für die Durchführung bestimmter Aktivitäten verantwortlich ist. Nachdem Sie herausgefunden haben, welche Aufgaben und Aktivitäten für Ihre Bereitstellung gelten, müssen sie von den Gruppen oder Personen verstanden und gefolgt werden, die Sie ihnen zuweisen.

Jedes Team, das Sie identifizieren, muss die identifizierten Aufgaben und Verantwortlichkeiten überprüfen und vereinbaren und mit der Vorbereitung beginnen. Dies kann Schulungen und Bereitschaften umfassen, Aktualisierungen des Personalplans bereitstellen oder sicherstellen, dass externe Anbieter bereit für die Bereitstellung sind.

Die in diesem Leitfaden definierten Aktivitäten und Rollen sollten in den meisten Szenarien gültig sein, aber jede Teams Bereitstellung ist eindeutig. Daher können Sie diesen Leitfaden als Ausgangspunkt verwenden, um die Aktivitäten und Standardrollen an Ihre Anforderungen anzupassen.

Stellen Sie sicher, dass jedes rechenschaftspflichtige Team über ein gutes Verständnis der Aktivitäten verfügt, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass jedes Team seine Verantwortlichkeit in Ihrer Organisation akzeptiert und abzeichnet, bevor das erste Pilotprojekt beginnt.

Nachdem eine Vereinbarung getroffen wurde, sollten die entsprechenden Teams mit der Operationalisierung ihrer Rollen beginnen.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument, um die Zuordnung der operativen Rollen zu vereinfachen.</li><li>Treffen Sie sich mit den jeweiligen Supportteams, um jedem Element in der Liste der erforderlichen Aktivitäten Namen zuzuweisen.</li><li>Erhalten Sie Akzeptanz oder Abmeldung für die zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams über die entsprechenden Schulungen, Bereitschaften und Ressourcen verfügen, um die erforderlichen Aktivitäten auszuführen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams Dienstabhängigkeiten

Microsoft Teams bringt Technologien Microsoft 365 oder Office 365 zusammen, um einen Hub für Teamarbeit bereitzustellen. Beispiele hierfür sind:

-   Azure Active Directory (Azure AD) bietet Authentifizierungs- und Autorisierungsdienste für Teams.

-   Exchange Online bietet erweiterte Features wie gesetzliche Aufbewahrungspflichten und E-Discovery.

-   SharePoint Online bietet die Möglichkeit, Dateien in Kanälen freizugeben, und OneDrive for Business bietet einen Mechanismus zum Freigeben von Dateien innerhalb eines privaten Chats.

Organisationen können auch vorhandene Investitionen in lokale Infrastruktur nutzen. Beispielsweise können vorhandene lokales Active Directory-Konten für die Authentifizierung verwendet werden, indem Azure AD-Verbinden verwendet wird. Bestimmte Versionen von Exchange Server können anstelle von Exchange Online verwendet werden.

Diese Technologien kommen zusammen, um eine umfassende, kollaborative und intelligente Kommunikationssuite für Benutzer bereitzustellen. Diese enge Integration ist ein wesentlicher Vorteil von Teams, aber sie treibt auch eine Anforderung für die Dienstverwaltung über diese Technologien hinweg an.

In diesem Leitfaden werden die wichtigsten Schwerpunktbereiche für die Verwaltung des Teams-Diensts behandelt. Höchstwahrscheinlich verfügen Sie über Dienstverwaltungspläne für die unterstützenden Technologien, von denen Teams abhängt. Andernfalls müssen Sie auch geeignete Dienstverwaltungspläne für diese Technologiekomponenten (sowohl lokal als auch online) einrichten. Dies trägt dazu bei, dass Ihre Benutzer eine qualitativ hochwertige und zuverlässige Erfahrung mit Teams genießen.

#### <a name="references"></a>Referenzen 

[Übersicht über Microsoft Teams](teams-overview.md)

[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Aktivitäten des Betriebsleitfadens

Die folgenden Abschnitte geben einen Überblick über die Aktivitäten, die für den erfolgreichen Betrieb des Microsoft Teams-Diensts erforderlich sind. Sie enthalten Verweise auf Tools, Kontextinformationen und zusätzliche Inhalte, die Ihnen helfen, die Aktivität zu verstehen und bei Bereitschaftsinitiativen zu unterstützen.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Überwachen des Dienststatus

Es ist wichtig, dass Sie den allgemeinen Status des Microsoft Teams-Diensts verstehen, damit Sie andere Personen in Ihrer Organisation proaktiv über alle Ereignisse informieren können, die sich auf den Dienst auswirken. Wie weiter oben beschrieben, ist Teams von anderen Microsoft 365 oder Office 365 Diensten wie Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business. Aus diesem Grund ist es ebenso wichtig, dass Sie den Status der abhängigen Dienste überwachen.

Integrieren Sie diese Aktivität in Ihren Vorfallverwaltungsprozess, um Benutzer, den Helpdesk und Ihre Betriebsteams proaktiv zu informieren, um sich auf die Behandlung von Benutzereskalationen vorzubereiten.

In den folgenden Abschnitten werden die Tools beschrieben, die Sie verwenden können, um [auf Dienstvorfälle](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) zu überwachen, die sich auf den Teams-Dienst auswirken. Eine Zusammenfassung der Vorteile der einzelnen Tools und wann Sie jedes tool verwenden sollten, ist in der folgenden Tabelle enthalten.

| Überwachungstool                       | Vorteile                                            | Verwendung                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 Admin Center                     | Verfügbar von jedem Gerät mit einem unterstützten Browser. | Verwenden Sie diese App, wenn Sie keine Echtzeitbenachrichtigungen benötigen.                                          |
| Microsoft 365- oder Office 365 Admin-App                  | Stellt Pushbenachrichtigungen für Ihr mobiles Gerät bereit.  | Verwenden Sie diese Informationen, wenn Sie unterwegs über Dienstvorfälle benachrichtigt werden müssen.                  |
| Microsoft System Center               | Integration in Microsoft System Center.           | Verwenden Sie diese Funktion, wenn Sie erweiterte Überwachungsfunktionen und Benachrichtigungsunterstützung benötigen.                       |
| Microsoft 365- oder Office 365-Dienstkommunikations-API | Programmgesteuerter Zugriff auf Microsoft 365 oder Office 365 Dienststatus.   | Verwenden Sie dies, wenn Sie eine Integration mit einem Drittanbieterüberwachungstool benötigen oder Eine eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, denen die Rolle des **globalen Administrators** oder **Dienstadministrators** zugewiesen ist, können den Dienststatus anzeigen.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Überwachung mit dem Microsoft 365 Admin Center

Die [Microsoft 365 Admin Center](https://portal.office.com/) bietet ein [Dienststatusdashboard](https://portal.office.com/adminportal/home#/servicehealth), in dem Sie neben abhängigen Diensten auch den aktuellen Status des Teams-Diensts anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachung mit der mobilen App

Die Microsoft 365- oder Office 365 Admin-App ist auf Apple iOS, Android und Windows (PC und Mobilgerät) verfügbar. Die App stellt Dienstadministratoren Informationen zum Dienststatus und bevorstehenden Änderungen bereit. Die App unterstützt Pushbenachrichtigungen, die Sie fast unmittelbar nach der Bereitstellung einer Empfehlung benachrichtigen können. Dies hilft Ihnen, über den Status, den Status und alle bevorstehenden Änderungen am Dienst auf dem Laufenden zu bleiben. Die Benachrichtigungsunterstützung macht es zum empfohlenen Überwachungstool für Administratoren. Weitere Informationen finden Sie unter:

[Office 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Herunterladen der Office 365 Admin Mobile App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Überwachung mit Microsoft System Center

Microsoft System Center ist eine integrierte Verwaltungsplattform, die Sie beim Verwalten von Rechenzentren, Clientgeräten und hybriden Cloud-IT-Umgebungen unterstützt. Office 365 Administratoren, die System Center verwenden, haben jetzt die Möglichkeit, das Office 365 Management Pack zu importieren, wodurch sie die gesamte Dienstkommunikation innerhalb von Operations Manager in System Center anzeigen können. Mit diesem Tool erhalten Sie Zugriff auf den Status Ihrer abonnierten Dienste, aktive und gelöste Dienstvorfälle und Ihre Nachrichtencenterkommunikation (bevorstehende Änderungen). Weitere Informationen finden Sie im folgenden [Blogbeitrag](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Wenn Sie System Center nutzen, um Teams Dienststatus (und abhängige Dienste) zu überwachen, können Sie das Management Pack weiter anpassen, um bestimmte Gruppen oder Personen zu benachrichtigen oder zu benachrichtigen, die identifiziert wurden, um auf Vorfälle zu reagieren.
Zu diesen Gruppen können Dienstbesitzer, Helpdesks, Supportgruppen der zweiten und dritten Ebene sowie Vorfallmanager in Ihrer Organisation gehören.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachung für erweiterte Szenarien

Sie können den Dienststatus und bevorstehende Änderungen überwachen, indem Sie die Office 365 Dienstkommunikations-API verwenden, um programmgesteuert auf Office 365 Dienststatus und Änderungen zuzugreifen. Verwenden Sie diese API, um ein eigenes Überwachungstool zu erstellen, oder verbinden Sie Ihre vorhandenen Überwachungstools mit Office 365 Dienstkommunikation, wodurch die Überwachung Ihrer Umgebung möglicherweise vereinfacht wird. Weitere Informationen finden Sie [unter Office 365 für Enterprise-Entwickler](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität               | Beschreibung                                                                                                                                                                                                               | Trittfrequenz   | Team zugewiesen |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen des Dienststatus | Überwachen Sie proaktiv Microsoft Teams Dienststatus (und abhängige Dienste) mithilfe der verfügbaren Tools. Abhängige Dienste umfassen: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Echtzeit |               |
| Vorfallbenachrichtigung  | Benachrichtigen Sie interne Projektbeteiligte über Ereignisse, die sich auf den Teams-Dienst auswirken. Interne Projektbeteiligte können Benutzer, Helpdesks und Vorfallmanager umfassen.                                                                          | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[So überprüfen Sie Office 365 Dienstintegrität](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Dienststatus und -kontinuität](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von Organisationsänderungen

Microsoft Teams ist ein cloudbasierter Dienst. Dies bietet die Möglichkeit, neue Features und Funktionen in einem schnellen Tempo bereitzustellen. Die Bereitstellung fortlaufender Innovationen ist ein offensichtlicher Vorteil für Organisationen, aber diese Änderungen müssen in Ihrer Organisation entsprechend verwaltet werden, um Widerstand der Benutzer oder Eskalationen für Ihren Helpdesk zu vermeiden.

Updates für Teams werden automatisch für Ihre Benutzer bereitgestellt. Ihre Benutzer verfügen immer über den neuesten Client und die neuesten Features, die im Teams-Dienst verfügbar sind. Es ist nicht möglich, den Rollout von Teams Updates für Ihre Benutzer zu verwalten, daher ist es von entscheidender Bedeutung, Veränderungen durch effektive Kommunikations-, Schulungs- und Einführungsprogramme zu verwalten. Wenn Ihre Benutzer sich der Änderung bewusst sind, über die Vorteile informiert sind und die neuen Funktionen&mdash;nutzen können, können sie sich schneller anpassen und die Änderung begrüßen.

### <a name="monitoring-for-change"></a>Überwachung auf Änderungen

Der erste Schritt im Change Management ist die Überwachung der Änderungen, die für Teams geplant sind. Die beste Quelle für die Überwachung dieser Änderungen ist die [Office 365 Roadmap](https://products.office.com/business/office-365-roadmap), die Features auflistet, die sich derzeit in der Entwicklung befinden, für Kunden eingeführt werden oder vollständig eingeführt wurden. Sie können mithilfe des bereitgestellten Filters nach Teams spezifischen Features suchen oder die Roadmap zur weiteren Analyse in eine Excel Datei herunterladen. Für jedes Feature enthält die Roadmap eine kurze Beschreibung zusammen mit dem erwarteten Veröffentlichungsdatum.

Im [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog) erfahren Sie mehr über bewährte Methoden, Trends und Neuigkeiten zu Teams Produktupdates. Erwarten Sie, dass Sie wichtige Featureupdates finden, die hier Teams angekündigt werden. Sie können den Blog auch über einen RSS-Feed abonnieren. Anschließend können Sie [den RSS-Feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direkt in einem Teams Kanal hinzufügen, sodass alle wichtigen Nachrichten direkt innerhalb von Teams übermittelt werden.

Alle veröffentlichten Features sind in den [Versionshinweisen für Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de) dokumentiert.
Hier finden Sie eine Liste der Features, die für Desktop-, Web- und mobile Geräte veröffentlicht wurden. Die gleichen Versionshinweise sind auch auf der Registerkarte **"Neuigkeiten** " in der [Hilfe](get-help-in-microsoft-teams.md) verfügbar.

Machen Sie sich mit den verfügbaren Ressourcen vertraut, und stellen Sie sicher, dass Sie entsprechende Besitzer zuweisen, die auf Änderungen überwacht werden sollen.

### <a name="planning-for-change"></a>Planen von Änderungen

Nachdem Sie sich der bevorstehenden Änderungen am Teams-Dienst bewusst sind, besteht der nächste Schritt darin, eine entsprechende Vorbereitung und Planung vorzunehmen. Bewerten Sie jede Änderung, um zu bestimmen, welche Änderungen eine Kommunikation mit Benutzern, Sensibilisierungskampagnen, Schulungen für Supportteams oder Benutzer oder Kampagnen zur Bewertung und Einführung von Features erfordern. Dies ist die primäre Rolle eines Änderungsverwaltungsteams in Ihrer Organisation. Im Folgenden finden Sie eine Sammlung von Beispieltabellen, die Ihnen bei der Planung von Änderungen helfen können.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloudaufzeichnung (Veröffentlichungsdatum: Januar 2018)

**Allgemeiner Titel**

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Rechtliche Überprüfung   | Abgeschlossen     | Dieses Feature ist eine Voraussetzung für das Onboarding des Schulungsteams. | Project Team  |

**Technisches Change Management**

|       Änderungsbereitschaft       | Status |                      Hinweise/nächste Schritte                      |    Besitzer     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     IT-Änderungen erforderlich      |  Ja   | Admin muss die Aufzeichnung nur für identifizierte Benutzer aktivieren. | Supportteam |
| Technische Bereitschaft abgeschlossen |  Ja   |                                                            | Supportteam |
|                              |        |                                                            |              |

**Benutzeränderungsverwaltung** 

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Auswirkungen des Benutzers                  | Niedrig                  |                                                                 |                        |
| Benutzerbereitschaft erforderlich      | Ja                  |                                                                 |                        |
| Kommunikation bereit         | Nein                   | Die E-Mail-Adresse der Kommunikation wurde entworfen – eine Überprüfung steht aus.            | Kommunikationsteam    |
| Schulung bereit               | Ja                  | Die Schulung nutzt vorhandenes Microsoft-Video.                | Schulungsteam          |

**Statusnachverfolgung**

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Veröffentlichungsstatus               | wird ausgeführt          | Ausstehende Überprüfung durch executive sponsor.               | Änderungsverwaltungsteam |
| Freigabeabmeldung             |                      |                                                                 |                        |
| Veröffentlichungsdatum                 |                      |                                                                 |                        |

Weitere Informationen zur Planung des Änderungsmanagements mit Teams finden [Sie unter Erstellen einer Change Management-Strategie für Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität               | Beschreibung                                                                                                                                                                                                                | Trittfrequenz   | Team zugewiesen |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Auf Änderungen überwachen     | Überwachen sie auf bevorstehende Änderungen an Microsoft Teams Dienst.                                                                                                                                                                   | Täglich     |               |
| Planen von Änderungen    | Bewerten und planen Sie neue Features und Funktionen, einschließlich Kommunikationsplänen, Sensibilisierungskampagnen und Schulungen.                                                                                                     | Nach Bedarf |               |
| Benutzerbereitschaft             | Führen Sie gezielte Kommunikations-, Bewusstseins- oder Schulungskampagnen durch, um sicherzustellen, dass Die Benutzer für die bevorstehende Änderung bereit sind.                                                                                                        | Nach Bedarf |               |
| Teambereitschaft unterstützen | Führen Sie gezielte Kommunikations-, Bewusstseins- oder Schulungskampagnen durch, um sicherzustellen, dass das Supportteam bereit ist. Supportteams können das "weiße Handschuh"-Team, Helpdesks, Unterstützung der Stufe 2 oder Stufe 3, externe Partner usw. umfassen. | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten Teams Nutzung

Nach beginn des ersten Pilotprojekts ist es wichtig, einen regelmäßigen Rhythmus für die Messung der tatsächlichen Teams Nutzung festzulegen. Auf diese Weise erhält Ihre Organisation Einblicke in die Ausrichtung der tatsächlichen Nutzung an die Nutzung, die Sie während der Envisionsphase vorhergesagt haben. Obwohl sich dieser Abschnitt auf Teams Nutzung konzentriert, sollte dies Teil eines umfassenderen Aufwands sein, um Office 365 Nutzung insgesamt zu messen und zu bewerten.

Wenn Sie die Nutzung häufig früh in der Bereitstellung überprüfen, haben Sie die Möglichkeit:

-   Überprüfen Sie, ob Benutzer Teams verwenden.

-   Identifizieren Sie potenzielle Herausforderungen bei der Einführung, bevor sie kritische Probleme in der gesamten Organisation schaffen.

-   Verstehen Sie, ob es Abweichungen zwischen den Anforderungen der Envision-Phase und der tatsächlichen Nutzung gibt.

Wenn die Verwendung nicht ihren Erwartungen entspricht, kann dies auf ein Bereitstellungsproblem zurückzuführen sein, oder der Einführungsplan wird nicht ordnungsgemäß ausgeführt, oder es gibt ein anderes Problem. Je nach dem tatsächlichen Grund für die geringe Nutzung muss der Dienstadministrator mit den zugehörigen Teams zusammenarbeiten, um Nutzungsbarrieren zu beseitigen.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Messen der Nutzung mit dem Microsoft 365 Admin Center

Nutzungsdaten aus Teams sind im Berichterstellungsdashboard verfügbar. Teams Nutzungsdaten finden Sie in drei verschiedenen Berichten. Der erste Bericht bietet eine produktübergreifende Ansicht der Kommunikation und Zusammenarbeit von Benutzern mithilfe der verschiedenen Dienste in Office 365. Dieser Bericht finden Sie hier: [bericht "Office 365 aktive Benutzer"](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Die beiden anderen Berichte sind Teams-spezifisch und enthalten weitere Details über Teams Nutzung aus Benutzer- und Geräteperspektive. Beide Berichte finden Sie hier:

[Microsoft Teams – Gerätenutzungsbericht](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Microsoft Teams – Benutzeraktivitätsbericht](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Auf die Nutzungsberichte im Admin Center können Personen zugreifen, denen eine **globaler Administrator** Rolle zugewiesen wurde, oder eine produktspezifische Administratorrolle (**Exchange Administrator**, **Skype for Business Administrator**, **SharePoint Administrator**).

Darüber hinaus ist die Leserrolle **"Berichte** " für Benutzer verfügbar, die Zugriff auf die Berichte benötigen, aber keine Aufgaben ausführen, für die Berechtigungen auf Administratorebene erforderlich sind. Sie weisen diese Rolle zu, um Nutzungsberichte für alle Beteiligten bereitzustellen, um die Einführung zu überwachen und voranzutreiben. Weitere Informationen zu den verschiedenen verfügbaren Rollen finden [Sie unter "Informationen Office 365 Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)".

### <a name="assessing-usage"></a>Bewerten der Nutzung

Nachdem Sie das Berichterstellungsdashboard zum Messen der Nutzung verwendet haben, ist es wichtig, die gemessene Nutzung mit allen wichtigen Erfolgsindikatoren (Key Success Indicators, KSIs) zu vergleichen, die Sie während der Envisionsphase des Projekts definiert haben. Sie können eine KSI definieren, die als aktive Nutzung definiert werden kann, oder eine, die indirekt mit der aktiven Nutzung verknüpft ist.

Es ist wichtig, abweichungen zwischen der tatsächlichen und der geplanten Nutzung zu identifizieren, bevor Sie das Rollout für weitere Websites oder Benutzer fortsetzen. Wahrscheinlich identifizieren Sie organisatorische Erkenntnisse als Teil dieser Aktivität, die Sie nutzen können, um sicherzustellen, dass die nächsten Stapel von Websites oder Benutzern nicht auf dieselben Probleme stoßen.

Stellen Sie zunächst fest, ob es sich um ein Adoptions- oder technisches Problem handelt. Beginnen Sie, indem Sie die folgenden Elemente untersuchen, um zu ermitteln, wo sich das Problem befindet.

1.  Überprüfen Sie die Qualität, indem Sie eine Überprüfung der Qualität der Erfahrung durchführen (weitere Details finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)).

2.  Arbeiten Sie mit dem Helpdeskteam zusammen, um zu überprüfen, ob es keine technischen Probleme gibt, die Benutzer daran hindern, auf den Dienst zuzugreifen oder diesen zu verwenden. Wenn Problemtrends vorhanden sind, verwenden Sie den Abschnitt [zur Endpunktproblembehandlung](#endpoint-troubleshooting) weiter unten in diesem Artikel, um zu versuchen, das Problem zu lösen, bevor Sie supporten.

3.  Arbeiten Sie mit dem Schulungs- und Einführungsteam zusammen, um direktes Feedback von Benutzern zu sammeln (siehe [Bewerten der Benutzerstimmung](#assess-user-sentiment) weiter unten in diesem Artikel) und um die Effektivität von Sensibilisierungs- und Einführungsaktivitäten zu überprüfen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                         | Beschreibung                                                                                                                      | Trittfrequenz   | Team zugewiesen |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Messen der Nutzung (Aktivierungsphase) | Messen und bewerten Sie Teams Nutzung, wenn Während der Aktivierungsphase weiterhin Websites integriert werden. Behandeln Sie Nach Bedarf Nutzungsprobleme. | Wöchentlich    |               |
| Messen der Nutzung (Drive Value Phase)                           | Messen und bewerten Sie Teams Nutzung in der Drive Value-Phase (nach Abschluss der Bereitstellung). Behandeln Sie Nach Bedarf Nutzungsprobleme. | Zweiwöchentlich  |               |
| Update adoption plan             | Aktualisieren Sie Ihren Einführungsplan basierend auf dem Vergleich der gemessenen Nutzung mit Ihren Planungszielen.                                         | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Informationen zum Microsoft 365 Admin Center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Bewerten der Benutzerstimmung

Das Verständnis der Benutzerstimmung kann als Schlüsselindikator für die Messung des Erfolgs Ihrer Teams-Bereitstellung dienen. Benutzerfeedback kann Änderungen in Ihrer Organisation vorantreiben. Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise umfassen, wie Sie Ihren Benutzern Support anbieten.

Es ist wichtig, frühzeitig Feedback zu erhalten und die Bewertung der Benutzerstimmung während des gesamten Lebenszyklus des Projekts und darüber hinaus fortzusetzen. Verwenden Sie die folgenden Anleitungen, um das Intervall zu bestimmen, in dem Ihre Organisation Feedback einholen wird:

-   **Anfang des Projekts**: Indem Sie die Benutzerstimmung zu Beginn des Projekts bewerten, können Sie einen frühen Einblick erhalten, wie sich Ihre Benutzer über ihre Teams-Erfahrung fühlen.

-   **Nach wichtigen Meilensteinen**: Durch das Sammeln von Feedback während des gesamten Projektlebenszyklus können Sie die Benutzerstimmung kontinuierlich messen und bei Bedarf Änderungen vornehmen. Dies ist besonders nützlich nach wichtigen Meilensteinen.

-   **Project Schlussfolgerung**: Wenn Sie die Benutzerstimmung am Ende eines Projekts bewerten, erfahren Sie, wie gut Sie gearbeitet haben und wo noch Arbeit geleistet werden muss, und ermöglichen Es Ihnen, die Ergebnisse mit der vorherigen Umfrage zu vergleichen.

-   **Fortlaufend**: Messen Sie die Benutzerstimmung auf unbestimmte Zeit. Änderungen der Benutzerstimmung können auf Änderungen in der Umgebung Ihrer Organisation oder auf Änderungen im Teams-Dienst zurückzuführen sein. Wenn Sie die Benutzerstimmung in regelmäßigen Abständen messen, können Sie verstehen, wie gut Ihre Service Management-Teams funktionieren und wie Ihre Organisation auf Änderungen im Teams-Dienst reagiert.

Die Benutzerstimmung kann mit vielen verschiedenen Methoden bewertet werden. Dazu können E-Mail-Umfragen, persönliche oder telefonische Interviews oder einfach das Erstellen eines Feedbackkanals in Teams oder Yammer gehören. Weitere Informationen finden Sie [unter Bewährte Methoden für Benutzerfeedbackmethoden in Microsoft Teams](best-practices-feedback.md).

Sie können auch einen branchenweiten Ansatz verwenden, um die Benutzerstimmung zu bewerten, die als Net Promotor Score (NPS) bezeichnet wird, was im folgenden Abschnitt beschrieben wird.

### <a name="nps"></a>NPS 

Net Promoter Score (NPS) ist eine branchenweite Kundenbindungsmetrik und ein guter Ansatz zur Bewertung der Benutzerstimmung. NPS kann berechnet werden, indem zwei Fragen gestellt werden: "Wie wahrscheinlich ist es, dass Sie einem Kollegen Teams empfehlen?", gefolgt von der Freihandformfrage "Warum?"

NPS ist ein Index von -100 bis 100, der die Bereitschaft eines Kunden misst, das Produkt oder die Dienstleistung eines Unternehmens zu empfehlen. NPS basiert auf einer anonymen Umfrage, die an Benutzer per E-Mail oder auf andere elektronische Weise übermittelt wird. NPS misst die Loyalität zwischen einem Anbieter und einem Verbraucher. Es besteht nur aus einer Frage, in der Benutzer aufgefordert werden, ihre Erfahrung von 1 bis 10 zu bewerten, mit der Möglichkeit, zusätzliche Kommentare bereitzustellen. Benutzer werden dann basierend auf den folgenden Bewertungen klassifiziert:

-   9 oder 10 sind Promoter: Loyale Enthusiasten, die Ihren Service fördern und andere befeuern.

-   7 oder 8 sind passiv: Zufrieden, aber unenthusiastisch, anfällig für einen anderen Dienst oder ein anderes Angebot.

-   Von 1 bis 6 sind Detractors: Unglückliche Kunden, die Ihren Service beschädigen und das Wachstum behindern können.

![Ein Diagramm, das die NPS-Skalierung veranschaulicht.](media/operate-my-service-image2.png "Dieses Diagramm veranschaulicht die NPS-Skalierung. Es zeigt, dass Rankings von 0 bis 6 Detractors sind, 7 bis 8 passiv und 9 bis 10 Promoter sind.")

Obwohl die BASIS-NPS-Nummer nützlich ist, erhalten Sie den größten Nutzen aus der Analyse von Benutzerkommentaren. Sie helfen Ihnen zu verstehen, warum der Benutzer anderen Teams empfehlen würde (oder nicht). Diese Kommentare können wertvolles Feedback liefern, um den Projekt- oder Dienstverwaltungsteams zu helfen, die Anpassungen zu verstehen, die für die Bereitstellung eines Qualitätsdienstes erforderlich sind.

Um NPS-Umfragen für Ihre Organisation bereitzustellen, können Sie Ihr bevorzugtes Online-Umfragetool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität              | Beschreibung                                                                                                                                                                         | Trittfrequenz   | Team zugewiesen |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Bewerten der Benutzerstimmung | Erfassen und bewerten Sie die Benutzerstimmung mithilfe von Umfragen oder Interviews oder über einen Feedbackkanal in Teams oder Yammer.                                                                 | Nach Bedarf |               |
| Aktualisieren von Einführungsplänen | Fördern Sie Änderungen in Ihrer Organisation basierend auf Benutzerfeedback; Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise umfassen, wie Sie Ihren Benutzern Support anbieten. | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden von Yammer zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzerfeedback](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Viele wichtige Planungselemente gehen in die Optimierung, Größenanpassung und Behebung Ihrer Netzwerkinfrastruktur ein, um einen qualitativ hochwertigen, effizienten Weg zum Microsoft Teams-Dienst sicherzustellen. Die Planungsaufgaben und -anforderungen werden in unserer [Anleitung zur Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#network-readiness) behandelt. Netzwerke entwickeln sich häufig im Laufe der Zeit aufgrund von Upgrades, Erweiterungen oder anderen Geschäftsanforderungen. Es ist wichtig, dass Sie Ihre Anforderungen an Teams in Ihren Netzwerkplanungsaktivitäten berücksichtigen.

Obwohl die Netzwerkplanung ein wichtiger Aspekt einer Teams Bereitstellung ist, ist es ebenso wichtig, sicherzustellen, dass das Netzwerk fehlerfrei bleibt und auf der Grundlage sich ändernder geschäftlicher oder technischer Anforderungen auf dem neuesten Stand bleibt.

Um die Integrität Ihres Netzwerks sicherzustellen, müssen in regelmäßigen Abständen eine Reihe von Betriebsaktivitäten ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                                                       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                 | Trittfrequenz                | Team zugewiesen |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Überwachen Office 365 IPs und URLs                                | Überwachen Sie alle Änderungen an den [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges) mithilfe des bereitgestellten [RSS-Feeds](https://go.microsoft.com/fwlink/p/?linkid=236301), und initiieren Sie eine Änderungsanforderung an die entsprechenden Netzwerkgruppen.                                                                                                                                | Täglich                  |               |
| Aktualisieren des Netzwerks basierend auf Änderungen an Office 365 IPs und URLs | Aktualisieren Sie die entsprechenden Netzwerkkomponenten (Firewalls, Proxyserver, VPNs, clientseitige Firewalls usw.), um Änderungen an den [Office 365 URLs und IP-Adressbereichen widerzuspiegeln](/microsoft-365/enterprise/urls-and-ip-address-ranges).                                                                                                                                                              | Nach Bedarf              |               |
| Bereitstellen von Gebäudedaten                                          | Stellen Sie dem Qualitätspionier (oder den relevanten Beteiligten) aktualisierte Subnetzinformationen bereit, um sicherzustellen, dass die [Gebäudedefinitionen in CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem neuesten Stand gehalten werden. | Nach Bedarf              |               |
| Implementieren von Änderungen                                               | Implementieren Sie Änderungen im Netzwerk, um Änderungen Teams geschäftlichen und technischen Anforderungen zu unterstützen. Netzwerkelemente können Folgendes umfassen:<ul><li>Firewalls</li><li>Vpns</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>     | Nach Bedarf              |               |
| Netzwerküberwachung und -berichterstellung                               | Überwachen Sie das Ende des Netzwerks auf Verfügbarkeits-, Auslastungs- und Kapazitätstrends, indem Sie ihre vorhandenen Netzwerkverwaltungstools und Berichterstellungsfunktionen von Drittanbietern verwenden, die von Ihren Netzwerkanbietern zur Verfügung stehen. Verwenden Sie Trenddaten für die Netzwerkkapazitätsplanung.                                                                                                            | Täglich, wöchentlich, monatlich |               |
| Kapazitätsplanung                                              | Arbeiten Sie mit den Teams Dienstbesitzern zusammen, um die sich ändernden geschäftlichen und technischen Anforderungen zu verstehen, die zusätzliche Kapazitätsänderungen fördern können.                                | Nach Bedarf              |               |
| Netzwerkproblembehandlung und -behebung                        | Unterstützen Sie die Teams Helpdesks, Dienstbesitzern und wichtigen Beteiligten bei der Problembehandlung und Behebung von Problemen im Zusammenhang mit Teams Konnektivität, Zuverlässigkeit oder Qualität. Netzwerkelemente können Folgendes umfassen:<ul><li>Firewalls</li><li>Vpns</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>    | Nach Bedarf              |               |
| Notfallwiederherstellung und Hochverfügbarkeitstests                | Führen Sie regelmäßige Tests für hohe Verfügbarkeit und Notfallwiederherstellung in der Netzwerkinfrastruktur durch, um sicherzustellen, dass sie die angegebenen Service Level Objectives (SLOs) oder Service Level Agreements (SLAs) für den Teams-Dienst erfüllt.                                                                                                                                                  | Monatlich                |               |


### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Erstellen eines Datenschemas](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und Sicherstellen der Qualität 

Alle Organisationen benötigen eine Gruppe oder eine Einzelperson, um für die Qualität verantwortlich zu sein. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Die Rolle des Qualitätspioniers wird einer Person oder Gruppe zugewiesen, die sich für die Benutzererfahrung begeistert.
Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität der Organisation kann dies jede Person oder Gruppe sein, die die Leidenschaft hat, eine qualitativ hochwertige Benutzererfahrung sicherzustellen.

Der Qualitätspionier nutzt vorhandene Tools und dokumentierte Prozesse, z. B. das Anrufqualitätsdashboard (Call Quality Dashboard, CQD), um die Benutzererfahrung zu überwachen, Qualitätstrends zu identifizieren und bei Bedarf abhilfe zu sorgen.
Der Qualitätspionier sollte mit den jeweiligen Teams zusammenarbeiten, um Abhilfemaßnahmen voranzutreiben, und einem Lenkungsausschuss Über den Fortschritt und alle offenen Probleme berichten.

Lesen [Sie "Verbessern" und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md), in der unter anderem Aktivitäten beschrieben werden, die In den wichtigsten Bereichen, die den größten Einfluss auf die Verbesserung der Benutzerfreundlichkeit haben, Bewerten und Bereitstellen von Anleitungen zur Behebung bieten. Der In diesem Artikel bereitgestellte Leitfaden konzentriert sich auf die Verwendung von CQD als primäres Tool zum Melden und Untersuchen der einzelnen Bereiche, wobei der Schwerpunkt auf Audio liegt, um die Akzeptanz und Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Es wird dringend empfohlen, den Qualitätsmeister frühzeitig zu nominieren. Nachdem sie nominiert wurden, sollten sie beginnen, sich mit den Inhalten der [Monitor-Anrufqualität](monitor-call-quality-qos.md) und den zugehörigen Schulungsmaterialien vertraut zu machen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                               | Beschreibung                                                                                                                                                                                                                                                                                                 | Trittfrequenz                             | Team zugewiesen |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Qualitätspionier(en) nominieren und trainieren | Nominieren und trainieren Sie einen Qualitätspionier.                                                                                                                                                                                                                                                                   | Nach Bedarf                           |               |
| Durchführen von Quality of Experience Reviews (QERs)     | Führen Sie einen QER durch, um Trends in Bezug auf Qualität und Zuverlässigkeit zu identifizieren, anhand definierter Ziele zu überprüfen und wichtige Interessengruppen in der Organisation zu informieren.                                                                                                                            | Monatlich (wöchentlich während bereitstellungen) |               |
| Laufwerksbehebung                      | Koordinieren Sie die Wartungsanstrengungen in der gesamten Organisation basierend auf den QER-Bewertungen und -Ergebnissen.                                                                                                                                                                                                           | Nach Bedarf                           |               |
| Aktualisieren von Gebäudedaten in CQD            | Aktualisieren oder Hinzufügen neuer Gebäudedefinitionen im CQD, wenn Änderungen am Netzwerk vorgenommen werden (siehe [Hochladen Gebäudeinformationen](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Nach Bedarf                           |               |
| Ausfüllen der Rolle des Qualitätspioniers      | End-to-End-Verantwortung für die Qualität in der Organisation. Dazu gehören:<ul><li>Stellen Sie sicher, dass der QER regelmäßig durchgeführt wird.</li><li>Melden Sie wichtige Interessengruppen über den Qualitätsstatus.</li><li>Stellen Sie sicher, dass die Gebäudedatendefinitionen auf dem neuesten Stand sind.</li><li>Koordinieren Sie die Wartungsanstrengungen in der gesamten Organisation, um sicherzustellen, dass Benutzer über eine qualitativ hochwertige Erfahrung mit Teams verfügen.</li></ul>          | Täglich                               |               |



### <a name="references"></a>Referenzen 


[Hochladen von Mandanten- und Gebäudedaten in CQD](CQD-upload-tenant-building-data.md)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft Teams Endpunkte können als beliebiger PC, Mac, Tablet oder mobiles (oder anderes) Gerät definiert werden, auf dem der Teams-Client ausgeführt wird. Der Begriff *Endpunkt* umfasst nicht nur das Gerät selbst, sondern auch die Verbindung eines Benutzers mit dem Gerät, z. B. mithilfe des integrierten Mikrofons oder Lautsprechers des Geräts, ohrhörer oder eines optimierten Headsets. Nachdem sie bereitgestellt wurden, dürfen Endpunkte nicht vergessen werden. Die Teams Endpunkte erfordern eine fortlaufende Pflege und Wartung. In den folgenden Abschnitten werden bestimmte Bereiche beschrieben, auf die sie sich konzentrieren müssen.

### <a name="endpoint-requirements"></a>Endpunktanforderungen

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die Teams mobilen Apps werden über ihre jeweiligen App Stores auf dem neuesten Stand gehalten.

Der Teams Client hat Mindestanforderungen hinsichtlich der zugrunde liegenden Softwareplattform. Diese Anforderungen können sich im Laufe der Zeit ändern, und daher ist es wichtig, dass Sie sie auf Änderungen überwachen. Beispielsweise verfügt der Teams-Client über mindestens iOS Version. Wenn der Client einen Internetbrowser verwendet, muss der Browser ebenfalls auf dem neuesten Stand gehalten werden. Eine Liste der unterstützten Plattformen finden Sie unter [Get clients for Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können sich auf die Anrufqualität auswirken und sogar verhindern, dass ein Anruf eingerichtet wird. Nachdem die entsprechenden Ausschlüsse in der Clientfirewall konfiguriert wurden, müssen sie basierend auf den Informationen in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges) auf dem neuesten Stand gehalten werden. Ihr Drittanbieter enthält spezifische Anleitungen zum Aktualisieren der Ausschlüsse.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Wi-Fi Treiber sind möglicherweise problematisch. Ein Treiber kann beispielsweise ein sehr aggressives Roamingverhalten zwischen Zugriffspunkten aufweisen, das zu einem unnötigen Zugriffspunktwechsel führen kann, was zu einer schlechten Anrufqualität führt. Ein leistungsschwacher Wi-Fi Treiber kann durch eine Überprüfung der Erfahrungsqualität ermittelt werden (weitere Details finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)). Es ist wichtig, einen qualitätsgesteuerten Prozess zu implementieren, der neue Wi-Fi Treiber überwacht und sicherstellt, dass sie getestet werden, bevor sie für die allgemeine Benutzerpopulation bereitgestellt werden.

### <a name="endpoint-management"></a>Endpunktverwaltung

Ein Katalog unterstützter Endpunkte und Schnittstellengeräte (z. B. Headsets) sollte verfügbar und verwaltet werden. Dieser Katalog enthält eine Liste der genehmigten Geräte, die im Rahmen der Phasen "Envision" und "Onboarding" ausgewählt und überprüft wurden. In der Regel werden für jeden Personatyp in Ihrer Organisation bestimmte Geräte ausgewählt, um die Anforderungen der Attribute dieser Persona zu erfüllen. Alle Endpunkte haben einen Lebenszyklus, und Sie müssen die Lieferantenverträge, Garantie-, Ersatz-, Verteilungs- und Reparaturrichtlinien verwalten, die diesen Geräten zugeordnet sind.

### <a name="endpoint-troubleshooting"></a>Endpunkt-Problembehandlung

Selbst wenn Sie die vorherigen Anleitungen befolgt haben, treten bei Benutzern in Ihrer Organisation möglicherweise weiterhin Probleme mit Teams auf. Obwohl das Problem möglicherweise nicht mit dem Endpunkt selbst besteht, werden die Symptome des Problems in der Regel über den Client für den Benutzer angezeigt. Die folgenden Anleitungen sollen allgemeine Schritte zur Behebung des Problems bereitstellen. es ist nicht als umfassende Anleitung zur Problembehandlung gedacht. Die Schritte werden in einer bestimmten Reihenfolge bereitgestellt, müssen jedoch nicht explizit befolgt werden und sind je nach Art des Problems möglicherweise nicht anwendbar.

1.  **Überprüfen des Dienststatus:** Das Problem, das ein Benutzer möglicherweise hat, kann mit einem Ereignis zusammenhängen, das sich negativ auf den Teams Dienst oder seine abhängigen Dienste auswirkt. Als ersten Schritt empfehlen wir Ihnen, zu bestätigen, dass keine aktiven Dienstprobleme vorliegen. Weitere Informationen [finden Sie unter "Überprüfen Office 365 Dienststatus](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)".
    Denken Sie daran, den Status abhängiger Dienste zu überprüfen (z. B. Exchange, SharePoint, OneDrive for Business). Die Überwachung der Dienstintegrität wird im vorherigen Abschnitt ["Überwachen des Dienststatus"](#monitor-service-health) ausführlicher erläutert.

2.  **Überprüfen der Clientkonnektivität:** Verbindungsprobleme verursachen Funktionalitäts- oder Anmeldeprobleme in Teams. Wir empfehlen (insbesondere für neue Websites oder Standorte), die Konnektivität mit dem Dienst zu überprüfen. Stellen Sie sicher, dass für jede Website die folgenden [Office 365 URLs und IP-Adressbereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges) befolgt werden. Sie können das [Microsoft-Netzwerkbewertungstool](https://www.microsoft.com/download/details.aspx?id=53885) nutzen, um einen Konnektivitätstest durchzuführen, um zu überprüfen, ob die Medienports ordnungsgemäß für Cloud-VoIP-Funktionen geöffnet wurden. Detaillierte Schritte zum Ausführen der Konnektivitätstests finden Sie in den [Anleitungen zur Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#network-readiness) .

3.  **Überprüfen Sie die Liste der bekannten Probleme:** Lesen Sie [Teams Problembehandlung](/MicrosoftTeams/troubleshoot/teams), um festzustellen, ob der Benutzer von einem dieser Probleme negativ betroffen ist. Folgen Sie der bereitgestellten Problemumgehung (sofern vorhanden), um das Problem zu beheben.

4.  **Besuchen Sie die Microsoft Teams Community:** Die [Microsoft Teams Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) bietet dedizierte Räume für Teams. Die Teams-Community bietet eine Diskussionsliste, Blogbeiträge und Ankündigungen rund um Teams. Sie können eine Frage posten oder vorherige Diskussionen nach Lösungen für Ihr Problem durchsuchen.

5.  **Kontakt Microsoft-Support:** Sie können sich bei Problemen mit Teams online oder telefonisch an Microsoft-Support wenden. Weitere Informationen finden [Sie unter Kontaktieren des Supports für Geschäftsprodukte](/microsoft-365/admin/contact-support-for-business-products).
    Für Premier-Kunden können Supportanfragen initiiert werden, indem Sie den Anleitungen unter ["Kontaktieren des Supports für Microsoft Teams (Premier-Kunden)](https://support.microsoft.com/premier/contacts)" folgen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                 | Beschreibung                                                                                                                                                                                                                                                                                                                                                                     | Trittfrequenz   | Team zugewiesen |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Endpunktanforderungen    | Stellen Sie sicher, dass der Teams Endpunkt weiterhin alle Softwareanforderungen für Teams erfüllt, die unter ["Clients für Microsoft Teams abrufen](get-clients.md)" aufgeführt sind.                                                                                                                                                                                       | Monatlich   |               |
| Endpunktfirewalls       | Verwalten Sie die entsprechenden Ausschlüsse in der Endpunktfirewall basierend auf den Informationen in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges). Ihr Drittanbieter hat spezifische Anleitungen für die Aufrechterhaltung der Ausschlüsse. Abonnieren Sie den [RSS-Feed](https://support.office.com/o365ip/rss) , um automatisch über Änderungen benachrichtigt zu werden. | Nach Bedarf |               |
| WLAN-Treiber            | Testen und aktualisieren Sie Wi-Fi Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe von CQD ([Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Nach Bedarf |               |
| Endpunktverwaltung      | Verwalten Sie den Katalog der unterstützten Endpunkte und Schnittstellengeräte (z. B. Headsets). Verwalten von Lieferantenverträgen, Garantie-, Verteilungs-, Ersatz- und Reparaturrichtlinien.                                                                                                                                                                                                        | Monatlich   |               |
| Endpunkt-Problembehandlung | Problembehandlungsaufgaben können die Überprüfung der Konnektivität, die Konsultation der Liste bekannter Probleme, das Sammeln von Protokollen, die Analyse und die Eskalation bei Microsoft-Support oder Drittanbietern umfassen.                                                                                                                                                                                               | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Clients für Microsoft Teams abrufen](get-clients.md)

[Microsoft Teams Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products)

[Premier-Support kontaktieren](https://support.microsoft.com/premier/contacts)

[Problembehandlung bei Teams Video](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Microsoft Teams Dienst bereitgestellt wurde, müssen Sie mehrere Aktivitäten im Zusammenhang mit seiner Verwaltung ausführen. Die Aktivitäten reichen von der Verwaltung des Dienstes und einzelner Benutzer bis hin zur Kapazitätsplanung und Bereitstellung von Lizenzen und Telefonnummern. In den folgenden Abschnitten werden einige dieser allgemeinen Verwaltungsaufgaben behandelt.

### <a name="service-administration"></a>Dienstverwaltung

Der Teams-Dienst verfügt über mehrere Einstellungen, die mandantenweit konfiguriert werden können.
Änderungen an den Mandanteneinstellungen wirken sich auf alle Benutzer aus, die für Teams aktiviert wurden. Eine detaillierte Liste dieser Einstellungen finden [Sie unter Verwalten Microsoft Teams Einstellungen für Ihre Organisation](enable-features-office-365.md).

### <a name="user-administration"></a>Benutzerverwaltung

Um Benutzer zu unterstützen, benötigt eine Organisation möglicherweise eine beliebige Anzahl verwandter Aufgaben – die spezifischen Aufgaben variieren von Organisation zu Organisation. Letztendlich müssen diese Aufgaben von einem Supportteam verwaltet werden, dem diese operativen Aufgaben zugewiesen wurden. Die folgenden Aufgaben sind häufig erforderlich, um Benutzer in Teams zu unterstützen.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Allgemeine Aufgaben für Telefonsystem

[Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Zuweisen oder Ändern einer Notfalladresse für einen Benutzer](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Allgemeine Aufgaben für Audiokonferenz

[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Lizenzverwaltung

Wenn Ihre Organisation wächst oder verträget, ist es wichtig, dass Sie die Lizenzierung für aktuelle und zukünftige Anforderungen planen. Neben der Lizenzierung für Cloud-VoIP-Funktionen Telefonsystem und [Audiokonferenz](here-s-what-you-get-with-phone-system.md) gibt es eine Basislizenz Teams.[](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing)

Für Teams benötigen Telefonsystem Lizenzen zugeordnete [Anrufpläne.For](calling-plan-landing-page.md) Teams, Telefonsystem licenses require associated Calling Plans licenses. Mit der Anrufplanlizenzierung können Sie Inlands- und/oder Auslandsanrufe tätigen und empfangen. Diese Pläne sind nutzungsbasiert und weisen minutenbasierte Pools auf. Durch die Bereitstellung von [Guthaben für Kommunikationen](what-are-communications-credits.md) wird sichergestellt, dass Ihnen der Dienst nie ausgeht.

Audiokonferenz ermöglicht gebührenpflichtige Einwahlkonferenzen und Inlands-Einwahlkonferenzdienste. Gebührenfreie Einwahlkonferenzen oder Einwahlszenarien außerhalb des Landes können dazu führen, dass zusätzliche Gebühren anfallen, für die [Kommunikationsguthaben](what-are-communications-credits.md) erforderlich sind.

Kommunikationsguthaben kann sowohl den Anrufplan als auch Audiokonferenz Lizenzen ergänzen. Sowohl Anrufplanlizenzen als auch Kommunikationsguthaben sind nutzungsbasiert und müssen daher entsprechend überwacht und bereitgestellt werden.

Sie können den [PSTN-Nutzungsbericht](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) nutzen, um Ihre Verwendung von Anrufplanminuten und Kommunikationsguthaben zu überwachen. Basierend auf den Ergebnissen dieser Aktivität können Sie Ihre Lizenzierung entsprechend anpassen. In Kürze werden wir einen Bericht über [PSTN-Minutenpools](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) anbieten, um diese Aufgabe effektiver zu unterstützen.

### <a name="telephone-number-management"></a>Telefonnummernverwaltung

Es gibt zwei Methoden zum Abrufen von Nummern in Teams: Sie können Telefonnummern von einem anderen Anbieter portieren oder die Nummern direkt aus dem Nummernbestand von Microsoft bereitstellen. Beide Methoden werden unter [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md) beschrieben.

Die Anzahl der Telefonnummern, die Sie aus dem Nummernbestand von Microsoft bereitstellen können, ist begrenzt. Die Grenzwerte werden durch eine Reihe von Faktoren bestimmt, die in ["Wie viele Telefonnummern können Sie erhalten?"](how-many-phone-numbers-can-you-get.md) aufgeführt sind.
Die Grenzwerte hängen von der Art der Nummern ab– gebührenfreie Servicenummern, gebührenpflichtige Servicenummern und Abonnentennummern (Benutzernummern). Jeder hat seine eigenen Grenzen und muss unabhängig verwaltet werden. Wenn Sie sich dem Grenzwert nähern (oder den Grenzwert erreicht haben), können Sie eine Erhöhung auf den Grenzwert anwenden. Dieser Vorgang wird im Artikel im vorherigen Absatz beschrieben.

Es kann vorkommen, dass eine Nummer nicht verfügbar ist, um in einer Region bereitgestellt zu werden, in der der Dienst verfügbar ist. Informationen zum Verfahren zum Anfordern von Telefonnummern finden Sie unter ["Verwalten von Telefonnummern für Ihre Organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)".

### <a name="team-creation-optional"></a>Teamerstellung (optional)

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über Berechtigungen zum Erstellen Microsoft 365 Gruppen und damit eines Teams in Microsoft Teams. Wenn Sie eine engere Kontrolle haben und [die Erstellung neuer Teams](assign-roles-permissions.md#permissions-to-create-teams) (und damit die Erstellung neuer Microsoft 365 Gruppen) einschränken möchten, können Sie Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Administratoren delegieren. Wenn Ihre Organisation diese Option weiterverfolgen möchte, lesen Sie den in diesem Artikel beschriebenen Prozess, um Benutzern das Übermitteln von Anforderungen zu ermöglichen, die von einem zugewiesenen Team verarbeitet werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                    | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                             | Trittfrequenz   | Team zugewiesen |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Dienstverwaltung      | Verwaltung von mandantenweiten Teams-Einstellungen.                                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Benutzerverwaltung         | Verwaltung von benutzerbasierten Einstellungen und Lizenzierung in Teams.                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Lizenzverwaltung          | Planen Sie aktuelle und zukünftige Anforderungen für benutzer- und verbrauchsbasierte Lizenzierung (Anrufpläne und Kommunikationsguthaben), indem Sie den [PSTN-Nutzungsbericht](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) und den [Bericht über PSTN-Minutenpools](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) nutzen. | Wöchentlich    |               |
| Telefonnummernverwaltung | Verwalten Sie die für zukünftiges Wachstum verfügbaren Telefonnummern, und passen Sie die Lagerbestände an Ihre Organisatorischen Anforderungen an.                                                                                                                                                                                                                                                                                                | Wöchentlich    |               |
| Teamerstellung (optional)    | Überprüfen und Verarbeiten von Anforderungen für die Teamerstellung.                                                                                                                                                                                                                                                                                                                                                                          | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Verbessern und Überwachen der Anrufqualität

[Die Verbesserung und Überwachung der Anrufqualität für Teams](monitor-call-quality-qos.md) umfasst eine Reihe von Aktivitäten, die In den wichtigsten Bereichen, die den größten Einfluss auf die Verbesserung der Benutzerfreundlichkeit haben, bewerten und Anleitungen zur Behebung bereitstellen, wie unten dargestellt.

![Diagramm der Bereiche, die während einer Überprüfung der Erfahrungsqualität untersucht werden sollen.](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während einer Quality of Experience Review untersucht werden sollten: Audio, Zuverlässigkeit und Benutzerumfrageergebnisse.")

Durch die kontinuierliche Bewertung und Behebung der im Leitfaden beschriebenen Bereiche können Sie deren Potenzial verringern, sich negativ auf die Benutzererfahrung zu auswirken. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration

-   Schlechte WLAN-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Verwendung nicht optimierter oder integrierter Audiogeräte

-   Problematische Subnetze oder Netzwerkgeräte

Die Anleitungen zur [Verbesserung und Überwachung der Anrufqualität für Teams](monitor-call-quality-qos.md) konzentrieren sich auf die Verwendung des Anrufqualitäts-Dashboards (CQD) Online als primäres Tool zum Melden und Untersuchen jedes beschriebenen Bereichs, wobei der Schwerpunkt auf Audio liegt, um die Akzeptanz und Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Wir empfehlen dringend, den Qualitätspionier frühzeitig zu nominieren. Nachdem sie nominiert wurden, sollten sie beginnen, sich mit den Inhalten in ["Verbessern" vertraut zu machen und die Anrufqualität für Teams zu überwachen](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->