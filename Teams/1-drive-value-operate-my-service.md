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
description: Aufgaben und Aktivitäten, die für Teams Dienstverwaltung erforderlich sind, einschließlich Überwachung des Dienstzustands sowie Bewerten und Sicherstellen der Netzwerkqualität und -nutzung.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8376f6d2c385f2c7feee3c7051d7978e1deb04b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633449"
---
# <a name="operate-my-service"></a>Verwenden des Diensts

Dieser Artikel bietet eine Übersicht über die Anforderungen für den erfolgreichen Betrieb von Cloud-Sprachdiensten für Ihre Organisation. Durch die ordnungsgemäßen Betrieb Ihrer Cloud-Sprachdienste können Sie sicher sein, dass Sie eine qualitativ hochwertige und zuverlässige Erfahrung für Ihre Organisation bereitstellen.

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Im Betriebshandbuch erhalten Sie eine Übersicht über alle Aufgaben und Aktivitäten, die als Teil der Dienstverwaltungsfunktion für die Microsoft Teams.

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Teams umfasst Microsoft 365 oder Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt werden (z. B. Netzwerk).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Möglicherweise haben Sie bereits Prozesse und Aufgaben implementiert, die vorhandenen Diensten zugeordnet sind. Dies bedeutet, dass Sie Ihre aktuellen Prozesse wahrscheinlich erweitern können, wenn Sie das Dienstmanagement heute zur Unterstützung Teams Zukunft planen.

Die Dienstverwaltung umfasst alle Aktivitäten und Prozesse, die mit der Verwaltung von Teams End-to-End-Vorgängen involviert sind. Wie bereits erwähnt, liegen einige Komponenten der Dienstverwaltung – die Infrastruktur, die der Microsoft 365- oder Office 365-Dienst selbst umfasst – in der Verantwortung von Microsoft, wohingegen Sie, der Kunde, Ihren Benutzern die Verantwortung für die Verwaltung der verschiedenen Aspekte von Teams, des Netzwerks und der Endpunkte, die Sie bereitstellen, tragen.

Die Aufgaben und Aktivitäten in diesem Leitfaden sind in acht Kategorien unterteilt, wie im folgenden Diagramm dargestellt. Jede dieser Kategorien wird in den folgenden Abschnitten erweitert.

![A diagram depicting a list of categories of tasks and activities](media/operate-my-service-image1.png "Ein Diagramm mit einer Liste von Kategorien von Aufgaben und Aktivitäten, die die Dienstverwaltung für Teams umfasst. Das Diagramm zeigt auch, dass die Dienstverwaltung größtenteils eine Kundenaufgabe ist.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie Vorgänge für vorgänge implementiert Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Den vollständigen Überblick über das Betriebshandbuch</li><li>Implementieren Sie eine Betriebsstrategie, die auf den Zielen Ihrer Organisation ausgerichtet ist, um die Qualität und Zuverlässigkeit von Cloud-Voice Workloads zu gewährleisten.</li><li>Lesen [Sie Überwachen der Anrufqualität.](monitor-call-quality-qos.md)</li><li> Implementieren Sie eine Betriebsstrategie, um regelmäßig Überprüfungen zur Qualität der Benutzererfahrung durchzuführen, um sicherzustellen, dass Ihre Cloud-Sprachbereitstellung mit Ihren Spitzenfunktionen ausgeführt wird.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die Planung, die Sie für Vorgänge während der Zielphase unterplanen, ist von entscheidender Bedeutung, da Betriebsaktivitäten beginnen, wenn die ersten Pilotbenutzer aktiviert werden. In diesem Leitfaden sind die Aktivitäten und Aufgaben aufgeführt, die täglich, wöchentlich, monatlich oder nach Bedarf ausgeführt werden müssen, um eine qualitativ hochwertige und Teams verwalten zu können. Dieses Handbuch enthält Wissen und Anleitungen zum Ausführen dieser kritischen Aktivitäten und Aufgaben.

Eine wichtige Komponente einer erfolgreichen Bereitstellung besteht in der Sicherstellung, dass Die Planung, die Sie frühzeitig in der Planungsphase durchführen, umfasst das Bestimmen der Personen, die für die Durchführung bestimmter Aktivitäten verantwortlich sein sollen. Nachdem Sie herausgegangen sind, welche Aufgaben und Aktivitäten auf Ihre Bereitstellung angewendet werden, müssen sie verstanden werden und von den Gruppen oder Personen gefolgt werden, die Sie ihnen zuweisen.

Jedes von Ihnen identifizierte Team muss die identifizierten Aufgaben und Zuständigkeiten überprüfen und zustimmen und mit der Vorbereitung beginnen. Dies kann Schulungen und Bereitschaft, die Bereitstellung von Updates für den Personalplan oder die Sicherstellung umfassen, dass externe Anbieter für die Bereitstellung bereit sind.

Die in diesem Handbuch definierten Aktivitäten und Rollen sollten in den meisten Szenarien gültig sein, aber jede Teams ist eindeutig. daher können Sie dieses Handbuch als Ausgangspunkt verwenden, um die Aktivitäten und Standardrollen an Ihre Anforderungen anzupassen.

Stellen Sie sicher, dass jedes verständige Team über ein gutes Verständnis der Aktivitäten verfügt, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass jedes Team seine Verantwortlichkeit in Ihrer Organisation annimmt und abschreibt, bevor das erste Pilotprojekt beginnt.

Nachdem eine Vereinbarung in Betrieb ist, sollten die entsprechenden Teams damit beginnen, ihre Rollen zu operationalisieren.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument, um die Übung zur Rollenzuordnung zu vereinfachen.</li><li>Treffen Sie sich mit den jeweiligen Supportteams, um jedem Element in der Liste der erforderlichen Aktivitäten Namen zuzuordnen.</li><li>Gewinnen Sie die Annahme oder Abmelden der zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams über geeignete Schulungen, Bereitschafts- und Ressourcen verfügen, um die für sie erforderlichen Aktivitäten zu vervollständigen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams von Dienstabhängigkeiten

Microsoft Teams bringt Technologien aus allen Microsoft 365 oder Office 365 zusammen, um einen Hub für Teamarbeit zu bieten. Beispiele:

-   Azure Active Directory (Azure AD) stellt Authentifizierungs- und Autorisierungsdienste für Teams.

-   Exchange Online bietet erweiterte Features wie gesetzliche Vorschriften und e Discovery.

-   SharePoint Online bietet die Möglichkeit, Dateien in Kanälen zu teilen, und OneDrive for Business stellt einen Mechanismus zum Freigeben von Dateien in einem privaten Chat zur Verfügung.

Organisationen können auch vorhandene Investitionen in die lokale Infrastruktur nutzen. So können beispielsweise vorhandene lokale Active Directory-Konten zur Authentifizierung verwendet werden, indem Azure AD-Konten Verbinden. Bestimmte Versionen von Exchange Server können an Stelle einer Exchange Online.

Diese Technologien sind eine umfassende, gemeinsame und intelligente Kommunikationssuite für Benutzer. Diese enge Integration ist ein wesentlicher vorteil Teams, aber sie ist auch Voraussetzung für die Dienstverwaltung über diese Technologien hinweg.

Dieser Leitfaden befasst sich mit den wichtigsten Schwerpunktbereichen für die Verwaltung Teams Diensts. Höchstwahrscheinlich verfügen Sie über Serviceverwaltungspläne für die unterstützenden Technologien, von Teams abhängig sind. Andern falls nicht, müssen Sie auch geeignete Dienstverwaltungspläne für diese Technologiekomponenten (sowohl lokal als auch online) einrichten. Dadurch wird sichergestellt, dass Ihre Benutzer eine qualitativ hochwertige und zuverlässige Benutzererfahrung Teams.

#### <a name="references"></a>Referenzen 

[Übersicht über Microsoft Teams](teams-overview.md)

[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Aktivitäten des Betriebsleitfadens

Die folgenden Abschnitte bieten eine Übersicht über die Aktivitäten, die für den erfolgreichen Betrieb des Diensts Microsoft Teams sind. Sie enthalten Verweise auf Tools, Kontextinformationen und zusätzliche Inhalte, damit Sie die Aktivitäten besser verstehen und bei Bereitschaftsinitiativen helfen können.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Überwachen des Dienstzustands

Es ist wichtig, dass Sie den Gesamtzustand des Microsoft Teams-Diensts verstehen, damit Sie andere Personen in Ihrer Organisation proaktiv über jedes Ereignis warnen können, das sich auf den Dienst auswirkt. Wie zuvor beschrieben, hängt Teams von anderen Microsoft 365- oder Office 365-Diensten wie Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business. Aus diesem Grund ist es ebenso wichtig, dass Sie die Integrität der abhängigen Dienste überwachen.

Integrieren Sie diese Aktivität in Ihren Vorfallverwaltungsprozess, um Benutzer, den Helpdesk und Ihre Betriebsteams proaktiv zur Vorbereitung auf Benutzereskalation zu informieren.

In den folgenden Abschnitten werden die Tools beschrieben, die Sie zur Überwachung auf [Servicevorfälle](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) verwenden können, die sich auf Teams auswirken. Eine Zusammenfassung der Vorteile der einzelnen Tools und deren Verwendung ist in der folgenden Tabelle enthalten.

| Überwachungstool                       | Vorteile                                            | Verwendung                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 Admin Center                     | Von jedem Gerät mit einem unterstützten Browser aus verfügbar. | Verwenden Sie , wenn Sie keine Echtzeitbenachrichtigungen benötigen.                                          |
| Microsoft 365- oder Office 365 Admin-App                  | Stellt Pushbenachrichtigungen für Ihr mobiles Gerät zur  | Verwenden Sie diese Benachrichtigung, wenn Sie unterwegs über Servicevorfälle benachrichtigt werden müssen.                  |
| Microsoft System Center               | Integration in Microsoft System Center.           | Verwenden Sie , wenn Sie erweiterte Überwachungsfunktionen und Benachrichtigungsunterstützung benötigen.                       |
| Microsoft 365 oder Office 365 Service Communications API | Programmgesteuerter Zugriff auf Microsoft 365 oder Office 365 Dienstinte health.   | Verwenden Sie diese, wenn Sie die Integration mit einem Drittanbieter-Überwachungstool benötigen oder Ihre eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, denen die Rolle des **globalen Administrators** oder **Dienstadministrators zugewiesen** ist, können den Dienstzustand anzeigen.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Überwachen mit Microsoft 365 Admin Center

Das [Microsoft 365 Admin Center](https://portal.office.com/) stellt ein [Dienstinte health-Dashboard](https://portal.office.com/adminportal/home#/servicehealth) zur Verfügung, in dem Sie den aktuellen Status des Teams-Diensts zusätzlich zu abhängigen Diensten anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachen mit der mobilen App

Die app Microsoft 365 oder Office 365 Admin ist unter Apple iOS, Android und Windows (PC und mobile Geräte) verfügbar. Die App stellt Dienstadministratoren Informationen zum Dienstzustand und zu bevorstehenden Änderungen zur Verfügung. Die App unterstützt Pushbenachrichtigungen, mit deren Unterstützung Sie fast sofort benachrichtigt werden können, nachdem eine Empfehlung veröffentlicht wurde. Dies hilft Ihnen, den Status, den Status und alle anstehenden Änderungen am Dienst auf dem Laufenden zu halten. Die Benachrichtigungsunterstützung macht sie zum empfohlenen Überwachungstool für Administratoren. Weitere Informationen finden Sie unter:

[Office 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Herunterladen der Office 365 Admin Mobile-App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Überwachen mit Microsoft System Center

Microsoft System Center ist eine integrierte Verwaltungsplattform, die Ihnen hilft, Rechenzentrums-, Clientgeräte- und hybride Cloud-IT-Umgebungen zu verwalten. Office 365 Administratoren, die System Center verwenden, haben jetzt die Möglichkeit, das Office 365 Management Pack zu importieren, wodurch sie die gesamte Dienstkommunikation innerhalb von Operations Manager in ihrer System Center. Mit diesem Tool erhalten Sie Zugriff auf den Status Ihrer abonnierten Dienste, aktive und behobene Dienstvorfälle und Ihre Nachrichtencenterkommunikation (anstehende Änderungen). Weitere Informationen finden Sie im folgenden [Blogbeitrag](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Wenn Sie System Center zum Überwachen des Teams-Diensts (und abhängiger Dienste) nutzen, können Sie das Management Pack weiter anpassen, um bestimmte Gruppen oder Personen, die identifiziert wurden, zu benachrichtigen oder zu benachrichtigen, um auf Vorfälle zu reagieren.
Diese Gruppen können Dienstbesitzer, Helpdesks, Supportgruppen auf zweiter und dritter Ebene sowie Vorfallmanager in Ihrer Organisation umfassen.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachung für erweiterte Szenarien

Sie können den Dienstzustand und anstehende Änderungen überwachen, indem Sie die Office 365 Service Communications API nutzen, um programmgesteuert auf Office 365 Dienstinte health und Änderungen zu zugreifen. Verwenden Sie diese API, um ein eigenes Überwachungstool zu erstellen oder Ihre vorhandenen Überwachungstools mit Office 365 Dienstkommunikation zu verbinden, was die Überwachung Ihrer Umgebung vereinfacht. Weitere Informationen finden Sie [unter Office 365 für Enterprise Entwickler.](https://developer.microsoft.com/office)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität               | Beschreibung                                                                                                                                                                                                               | Cadence   | Team zugewiesen |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen des Dienstzustands | Überwachen Sie Microsoft Teams (und abhängigen Dienste) mithilfe der verfügbaren Tools proaktiv. Abhängige Dienste: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Echtzeit |               |
| Vorfallbenachrichtigung  | Benachrichtigen Sie die internen Beteiligten über Ereignisse, die Auswirkungen auf Teams haben. Zu den internen Beteiligten können Benutzer, Helpdesks und Vorfallmanager gehören.                                                                          | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[So wird's Office 365 dienstinte health](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Dienstinte health and continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von Organisationsänderung

Microsoft Teams ist ein cloudbasierter Dienst. Dies bietet die Möglichkeit, neue Features und Funktionen in einem schnellen Tempo bereitzustellen. Die Bereitstellung fortlaufender Innovationen ist für Organisationen ein offensichtlicher Vorteil, aber diese Änderungen müssen in Ihrer Organisation entsprechend verwaltet werden, um Benutzerstände oder -eskalationen für Ihren Helpdesk zu vermeiden.

Updates für Teams werden automatisch für Ihre Benutzer veröffentlicht. Ihre Benutzer verfügen immer über den neuesten Client und die neuesten Features, die im Dienst Teams sind. Es ist nicht möglich, den Rollout von Teams-Updates für Ihre Benutzer zu verwalten, daher ist es von entscheidender Bedeutung, den Wandel durch effektive Kommunikationsprogramme, Schulungs- und Einführungsprogramme zu verwalten. Wenn ihre Benutzer sich der Veränderung bewusst sind, sich über die Vorteile freuen und die neuen Funktionen nutzen können, können sie sich schneller anpassen und die Änderung &mdash; begrüßen.

### <a name="monitoring-for-change"></a>Überwachung auf Änderungen

Der erste Schritt im Änderungsmanagement besteht in der Überwachung der Änderungen, die für die Änderung geplant Teams. Die beste Quelle für die Überwachung dieser Änderungen ist die [Office 365 Roadmap,](https://products.office.com/business/office-365-roadmap)in der Features aufgeführt werden, die sich derzeit in der Entwicklung befinden, für Kunden eingeführt oder vollständig gestartet wurden. Sie können mithilfe Teams bereitgestellten Filters nach bestimmten Features suchen, oder Sie können die Roadmap in eine Excel datei herunterladen, um sie weiter zu analysieren. Für jedes Feature enthält die Roadmap eine kurze Beschreibung sowie das voraussichtliche Veröffentlichungsdatum.

Im Microsoft Teams [Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)erfahren Sie mehr über bewährte Methoden, Trends und Neuigkeiten zu Teams Produktupdates. Erwarten Sie, dass Sie wichtige Featureupdates finden, Teams hier angekündigt werden. Sie können den Blog auch über einen RSS-Feed abonnieren. Anschließend können Sie den [RSS-Feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direkt einem Kanal Teams hinzufügen, sodass alle wichtigen Nachrichten direkt in einem Kanal Teams.

Alle veröffentlichten Features sind in den [Anmerkungen zu dieser Version für Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Hier finden Sie eine Liste der Features, die für Desktop, Web und mobile Geräte veröffentlicht wurden. Der gleiche Satz von Anmerkungen zu dieser Version ist auch auf der **Registerkarte** Neues in der Hilfe [verfügbar.](get-help-in-microsoft-teams.md)

Machen Sie sich mit den verfügbaren Ressourcen vertraut, und stellen Sie sicher, dass Sie die geeigneten Besitzer zuweisen, um Änderungen zu überwachen.

### <a name="planning-for-change"></a>Planen von Änderungen

Da Ihnen nun anstehende Änderungen am Dienst Teams sind, besteht der nächste Schritt in der Vorbereitung und Planung. Bewerten Sie jede Änderung, um zu bestimmen, welche Änderungen die Kommunikation mit Benutzern, Informationskampagnen, Schulungen für Supportteams oder -benutzer oder Kampagnen zur Bewertung und Einführung von Features erfordern. Dies ist die primäre Rolle eines Change Management-Teams in Ihrer Organisation. Im Folgenden finden Sie eine Sammlung von Beispieltabellen, die Ihnen bei der Planung von Änderungen helfen können.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloudaufzeichnung (Veröffentlichungsdatum: Januar 2018)

**Allgemeine Nachverfolgung**

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Rechtliche Überprüfung   | Abgeschlossen     | Dieses Feature ist Voraussetzung für das Onboarding des Schulungsteams. | Project-Team  |

**Verwaltung technischer Änderungen**

|       Änderungsbereitschaft       | Status |                      Hinweise/nächste Schritte                      |    Besitzer     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     IT-Änderungen erforderlich      |  Ja   | Der Administrator muss die Aufzeichnung nur für identifizierte Benutzer aktivieren. | Supportteam |
| Technische Bereitschaft abgeschlossen |  Ja   |                                                            | Supportteam |
|                              |        |                                                            |              |

**Verwaltung von Benutzeränderung** 

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Auswirkungen des Benutzers                  | Niedrig                  |                                                                 |                        |
| Benutzerbereitschaft erforderlich      | Ja                  |                                                                 |                        |
| Kommunikation bereit         | Nein                   | Kommunikations-E-Mails wurden erstellt – ausstehende Überprüfung.            | Kommunikationsteam    |
| Schulung bereit               | Ja                  | In der Schulung wird das vorhandene Microsoft-Video genutzt.                | Schulungsteam          |

**Statusanzeige**

| Änderungsbereitschaft | Status   | Hinweise/nächste Schritte | Besitzer |
|----|----|----|-----|
| Veröffentlichungsstatus               | wird ausgeführt          | Ausstehende Überprüfung durch den Executive Sponsor.               | Change Management Team |
| Freigabe-Abmeldung             |                      |                                                                 |                        |
| Veröffentlichungsdatum                 |                      |                                                                 |                        |

Weitere Informationen zur Planung des Change Managements mit Teams finden Sie unter Erstellen einer [Änderungsverwaltungsstrategie für Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität               | Beschreibung                                                                                                                                                                                                                | Cadence   | Team zugewiesen |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen auf Änderungen     | Überwachen Sie bevorstehende Änderungen am Microsoft Teams Diensts.                                                                                                                                                                   | Täglich     |               |
| Planen von Änderungen    | Bewerten und planen Sie neue Features und Funktionen, einschließlich Kommunikationsplänen, Informationskampagnen und Schulungen.                                                                                                     | Nach Bedarf |               |
| Benutzerbereitschaft             | Führen Sie gezielte Kommunikation, Informationen oder Schulungskampagnen durch, um sicherzustellen, dass die Benutzer für die bevorstehende Änderung bereit sind.                                                                                                        | Nach Bedarf |               |
| Unterstützungsbereitschaft für das Team | Führen Sie gezielte Kommunikation, Information und Schulungskampagnen durch, um sicherzustellen, dass das Supportteam bereit ist. Supportteams können das "weiße" Team, Helpdesks, Support der Stufe 2 oder Stufe 3, externe Partner und so weiter umfassen. | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten Teams Nutzung

Nachdem das Pilotprojekt gestartet wurde, ist es wichtig, einen regelmäßigen Zeitfluss zum Messen der tatsächlichen Teams festlegen. Auf diese Weise kann Ihre Organisation Einblicke in die tatsächliche Nutzung an der Nutzung gewinnen, die Sie in der Zielphase vorhergesagt haben. Obwohl der Schwerpunkt dieses Abschnitts auf der Teams liegt, sollte dies Teil einer umfangreicheren Maßnahme sein, um die Office 365 zu messen und zu bewerten.

Durch eine häufige Überprüfung der Nutzung zu einem frühen Anfang der Bereitstellung haben Sie die Möglichkeit:

-   Überprüfen Sie, ob Benutzer Teams.

-   Identifizieren Sie potenzielle Herausforderungen bei der Einführung, bevor sie kritische Probleme in der gesamten Organisation schaffen.

-   Verstehen Sie, ob es Abweichungen zwischen den Anforderungen an die Zielphase und der tatsächlichen Verwendung gibt.

Wenn die Nutzung nicht Ihren Erwartungs wegen steht, könnte dies auf ein Bereitstellungsproblem oder die Ausführung des Einführungsplans oder ein anderes Problem gerechnet werden. Je nach dem tatsächlichen Grund für die geringe Nutzung muss der Dienstadministrator mit den zugehörigen Teams zusammenarbeiten, um Verwendungsbarrieren zu beseitigen.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Messen der Nutzung mit Microsoft 365 Admin Center

Nutzungsdaten aus Teams sind im Berichtsdashboard verfügbar. Teams Verwendungsdaten finden Sie in drei verschiedenen Berichten. Der erste Bericht bietet eine produktübergreifende Ansicht der Kommunikation und Zusammenarbeit der Benutzer mithilfe der verschiedenen Dienste in Office 365. Dieser Bericht ist hier zu finden: [Bericht Office 365 Benutzer](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Die anderen beiden Berichte sind Teams und liefern aus Benutzer- und Geräteperspektive weitere Details zur Teams Nutzung. Beide Berichte finden Sie hier:

[Microsoft Teams – Gerätenutzungsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams – Benutzeraktivitätsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Auf die Verwendungsberichte im Admin Center können Personen  zugreifen, denen eine globale Administratorrolle oder eine produktspezifische Administratorrolle zugewiesen wurde **(Exchange-Administrator,** **Skype for Business-Administrator,** **SharePoint-Administrator).**

Darüber hinaus  steht die Leserrolle "Berichte" für Benutzer zur Verfügung, die Zugriff auf die Berichte benötigen, aber keine Aufgaben ausführen, die Berechtigungen auf Administratorebene erfordern. Sie weisen diese Rolle zu, um allen Beteiligten Nutzungsberichte zur Verfügung zu stellen, um die Akzeptanz zu überwachen und vordingen zu können. Weitere Informationen zu den verschiedenen verfügbaren Rollen finden Sie unter Informationen [Office 365 Administratorrollen.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Bewerten der Nutzung

Nachdem Sie das Berichterstellungsdashboard verwendet haben, um die Nutzung zu messen, ist es wichtig, die gemessene Nutzung mit allen Key Success Indicators (KSIs) zu vergleichen, die Sie während der Projekterteilungsphase definiert haben. Sie können eine KSI definieren, die möglicherweise als aktive Nutzung definiert ist, oder eine, die indirekt mit der aktiven Nutzung verknüpft ist.

Es ist wichtig, alle Abweichungen zwischen ist der tatsächlichen und der geplanten Nutzung zu ermitteln, bevor Sie das Rollout auf weitere Websites oder Benutzer fortsetzen. Wahrscheinlich identifizieren Sie im Rahmen dieser Aktivität die Lernergebnisse der Organisation, die Sie nutzen können, um sicherzustellen, dass für die nächste Gruppe von Websites oder Benutzern keine gleichen Probleme auftreten.

Als Erstes sollten Sie genau bestimmen, ob es sich um eine Verbreitung oder ein technisches Problem handelt. Beginnen Sie, indem Sie die unten aufgeführten Elemente untersuchen, um zu ermitteln, wo das Problem liegt.

1.  Überprüfen Sie die Qualität, indem Sie eine Überprüfung der Qualität der Gesprächsqualität durchführen (weitere Teams finden Sie unter Verbessern und Überwachen [der](monitor-call-quality-qos.md) Anrufqualität).

2.  Arbeiten Sie mit dem Helpdesk-Team zusammen, um zu überprüfen, ob es keine trendenden technischen Probleme gibt, die benutzer am Zugriff auf oder die Verwendung des Diensts verhindern. Wenn Problemtrends vorhanden sind, versuchen Sie im Abschnitt Problembehandlung des Endpunkts weiter später in diesem Artikel, das Problem zu beheben, bevor Sie Unterstützung erhalten. [](#endpoint-troubleshooting)

3.  Arbeiten Sie mit dem Schulungs- und Einführungsteam zusammen, um direktes Feedback von Benutzern zu sammeln (siehe Bewerten der Benutzerwahrnlichkeiten weiter später in diesem Artikel) und um die Effektivität von Bewusstsein und Verbreitungsaktivitäten zu überprüfen. [](#assess-user-sentiment)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                         | Beschreibung                                                                                                                      | Cadence   | Team zugewiesen |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Messen der Nutzung (Aktivierungsphase) | Messen und bewerten Teams Nutzung, da Websites während der Aktivierungsphase weiterhin onboarded werden. Beheben Sie Nutzungsprobleme nach Bedarf. | Wöchentlich    |               |
| Nutzung der Messung (Laufwerkwertphase)                           | Messen und bewerten Teams Nutzung in der Drive Value-Phase (nach Abschluss der Bereitstellung). Beheben Sie Nutzungsprobleme nach Bedarf. | Biweekly  |               |
| Plan zur Aktualisierung der Einführung             | Aktualisieren Sie Ihren Einführungsplan basierend darauf, wie sich die gemessene Nutzung mit den Planungszielen vergleichen lassen.                                         | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Informationen zur Microsoft 365 Admin Center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Bewerten der Benutzerstimmung

Das Verständnis der Benutzerstimmung kann ein wichtiger Indikator dafür sein, wie erfolgreich Ihre Bereitstellung Teams ist. Benutzerfeedback kann Änderungen in Ihrer Organisation vor sich haben. Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder der Art und Weise umfassen, in der Sie Ihren Benutzern Support bieten.

Es ist wichtig, frühzeitig Feedback zu erhalten und das Benutzerfeedback während des gesamten Lebenszyklus des Projekts und darüber hinaus zu bewerten. Verwenden Sie die folgenden Anleitungen, um das Intervall zu ermitteln, in dem Ihre Organisation Feedback einssuchet:

-   **Projektanfang:** Indem Sie die Benutzerstimmung zu Projektbeginn bewerten, erhalten Sie einen frühen Einblick in das Benutzererlebnis Teams Erfahrung.

-   **Nach wichtigen Meilensteinen:** Indem Sie während des gesamten Projektlebenszyklus Feedback sammeln, können Sie die Benutzerstimmung kontinuierlich messen und bei Bedarf Änderungen vornehmen. Dies ist besonders nach größeren Meilensteinen hilfreich.

-   **Project** Abschluss: Die Bewertung der Benutzerstimmung am Ende eines Projekts gibt auf, wie gut Sie fertig sind und wo noch Arbeit zu erledigen ist, und ermöglicht es Ihnen, die Ergebnisse mit der vorherigen Umfrage zu vergleichen.

-   **Fortlaufend:** Messen Sie die Benutzererwartungen weiterhin auf unbestimmte Zeit. Änderungen der Benutzerstimmung können auf Änderungen in der Umgebung Ihrer Organisation oder an Änderungen im Dienst Teams sein. Indem Sie die Benutzerstimmung in regelmäßigen Abständen überprüfen, können Sie verstehen, wie gut Ihre Dienstverwaltungsteams gut sind und wie Ihre Organisation auf Änderungen im Dienst Teams reagiert.

Benutzerstimmungen können mit vielen verschiedenen Methoden bewertet werden. Dazu können E-Mail-Umfragen, Vorstellungsgespräche im persönlichen oder Telefonstil gehören oder einfach nur ein Feedbackkanal im Teams oder Yammer. Weitere Informationen finden Sie unter [Bewährte Methoden für Benutzerfeedbackmethoden in Microsoft Teams.](best-practices-feedback.md)

Sie können auch einen branchenweiten Ansatz verwenden, um die Benutzerstimmung als Net Pro score score (NPS) zu bewerten, die im folgenden Abschnitt beschrieben wird.

### <a name="nps"></a>NPS 

Der Net Promoter Score (NPS) ist eine branchenweite Kundentreuemetrik und ein guter Ansatz, um die Benutzerstimmung zu bewerten. NPS kann berechnet werden, indem zwei Fragen gestellt werden: "Wie wahrscheinlich ist es, dass Sie Teams einem Kollegen empfehlen?", gefolgt von der Freihandfrage "Warum?"

NPS ist ein Index im Bereich von -100 bis 100, der die Indizes eines Kunden misst, um das Produkt oder den Dienst eines Unternehmens zu empfehlen. NPS basiert auf einer anonymen Umfrage, die den Benutzern per E-Mail oder auf anderem elektronischen Weg zugestellt wird. NPS misst die Kundentreue zwischen einem Anbieter und einem Consumer. Sie besteht aus nur einer Frage, bei der die Benutzer gefragt werden, ob sie ihre Erfahrung von 1 bis 10 bewerten müssen, mit der Möglichkeit, zusätzliche Kommentare eins zu geben. Die Benutzer werden dann basierend auf den folgenden Bewertungen klassifiziert:

-   9 oder 10 sind Promoters: Loyale Fans, die für Ihren Dienst werben und andere benennen.

-   7 oder 8 sind passive: Zufrieden, aber unenthustic, anfällig für einen anderen Dienst oder ein anderes Angebot.

-   Von 1 bis 6 sind Leistungsbehinderte: Unzufriedene Kunden, die Ihren Dienst beschädigen können und ein beeinträchtigtes Wachstum haben.

![Ein Diagramm, das die NPS-Skala veranschaulicht](media/operate-my-service-image2.png "Dieses Diagramm veranschaulicht die NPS-Skalierung. Es zeigt, dass Rangordnungen von 0 bis 6Tractoren, 7 bis 8 passive und 9 bis 10 Organisatoren sind.")

Obwohl die NPS-Basisnummer nützlich ist, erhalten Sie den größten Nutzen aus der Analyse von Benutzerkommentaren. Sie helfen Ihnen zu verstehen, warum der Benutzer andere Benutzer Teams empfehlen oder nicht. Diese Kommentare können wertvolles Feedback liefern, damit die Projekt- oder Dienstverwaltungsteams die Anpassungen verstehen, die zur Bereitstellung eines qualitativ hochwertigen Diensts erforderlich sind.

Um NPS-Umfragen für Ihre Organisation zur Verfügung zu stellen, können Sie Ihr bevorzugtes Online-Umfragetool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf Aufgaben

| Aktivität              | Beschreibung                                                                                                                                                                         | Cadence   | Team zugewiesen |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Bewerten der Benutzerstimmung | Erfassen und bewerten Sie das Benutzerfeedback mithilfe von Umfragen oder Vorstellungsgesprächen oder über einen Feedbackkanal in Teams oder Yammer.                                                                 | Nach Bedarf |               |
| Aktualisieren von Einführungsplänen | Laufwerkänderung in Ihrer Organisation auf der Grundlage von Benutzerfeedback; dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise umfassen, in der Sie Ihren Benutzern Support bieten. | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden Yammer zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzerfeedback](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Viele wichtige Planungselemente werden in die Optimierung, die richtige Größenanpassung und die Behebung Ihrer Netzwerkinfrastruktur eingesetzt, um einen qualitativ hochwertigen und effizienten Weg zum Microsoft Teams sicherzustellen. Die Planungsaufgaben und Anforderungen werden in unserem [Leitfaden für die Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#network-readiness) behandelt. Netzwerke entwickeln sich im Laufe der Zeit häufig aufgrund von Upgrades, der Erweiterung oder anderen geschäftlichen Anforderungen. Es ist wichtig, dass Sie ihre Anforderungen für die Teams in Ihren Netzwerkplanungsaktivitäten berücksichtigen.

Obwohl die Netzwerkplanung ein kritischer Aspekt einer Teams-Bereitstellung ist, ist es gleichermaßen wichtig sicherzustellen, dass das Netzwerk fehlerfrei bleibt und auf der Grundlage sich änderner geschäftlicher oder technischer Anforderungen auf dem Laufenden bleibt.

Um den Netzwerkzustand sicherzustellen, müssen eine Reihe von Vorgängen in regelmäßigen Abständen ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                                                       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                 | Cadence                | Team zugewiesen |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Überwachen Office 365 IPs und URLs                                | Überwachen Sie alle Änderungen an den [Office 365 URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges) und IP-Adressbereichen, indem Sie den bereitgestellten [RSS-Feed](https://go.microsoft.com/fwlink/p/?linkid=236301) verwenden und eine Änderungsanforderung an entsprechende Netzwerkgruppen initiieren.                                                                                                                                | Täglich                  |               |
| Aktualisieren des Netzwerks auf der Grundlage von Änderungen Office 365 IPs und URLs | Aktualisieren Sie die anwendbaren Netzwerkkomponenten (Firewalls, Proxyserver, VPNs, clientseitige Firewalls und so weiter), um Änderungen an [den OFFICE 365-URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges)und IP-Adressbereichen widerspiegeln zu können.                                                                                                                                                              | Nach Bedarf              |               |
| Bereitstellen von Gebäudedaten                                          | Stellen Sie aktualisierte Subnetzinformationen für den Qualitätschampion (oder relevante Projektbeteiligten) zur Verfügung, um sicherzustellen, dass die Gebäudedefinitionen [im CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem neuesten Stand gehalten werden. | Nach Bedarf              |               |
| Implementieren von Änderungen                                               | Implementieren Sie Änderungen im Netzwerk, um Änderungen an geschäftlichen Teams technischen Anforderungen zu unterstützen. Zu den Netzwerkelementen zählen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>     | Nach Bedarf              |               |
| Netzwerküberwachung und -berichterstellung                               | Überwachen Sie das Ende des Netzwerks auf Verfügbarkeit, Nutzung und Kapazitätstrends, indem Sie Ihre vorhandenen Netzwerkverwaltungstools und Berichtsfunktionen von Drittanbietern verwenden, die von Ihren Netzwerkanbietern zur Verfügung stehen. Verwenden Sie Trenddaten für die Planung der Netzwerkkapazität.                                                                                                            | Täglich, wöchentlich, monatlich |               |
| Kapazitätsplanung                                              | Arbeiten Sie mit den Teams, um änderungen geschäftliche und technische Anforderungen zu verstehen, die zusätzliche Kapazitätsänderungen zur Verfügung haben könnten.                                | Nach Bedarf              |               |
| Problembehandlung und Problembehebung im Netzwerk                        | Unterstützen Sie Teams Helpdesks, Dienstbesitzer und wichtige Projektbeteiligten bei der Problembehandlung und Behebung von Problemen im Zusammenhang mit Teams Konnektivität, Zuverlässigkeit oder Qualität. Zu den Netzwerkelementen zählen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul>    | Nach Bedarf              |               |
| Notfallwiederherstellung und Hochverfügbarkeitstests                | Führen Sie regelmäßige Tests zur Hochverfügbarkeit und Notfallwiederherstellung in der Netzwerkinfrastruktur durch, um sicherzustellen, dass sie die festgelegten Ziele zum Servicelevel (Service Level Objectives, SLOs) oder Vereinbarungen zum Servicelevel (Service Level Agreements, SLAs) für den Teams erfüllt.                                                                                                                                                  | Monatlich                |               |


### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Gebäudedatenschema](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und Sicherstellen der Qualität 

Alle Organisationen benötigen eine Gruppe oder Einzelperson, um auf Ihre Qualität zu würdigen. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Die Rolle "Qualitäts-Champion" wird einer Person oder Gruppe zugewiesen, die begeistert von der Benutzererfahrung ist.
Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität der Organisation kann es sich dabei um jede Person oder Gruppe mit der Leidenschaft zur Sicherstellung einer qualitativ hochwertigen Benutzererfahrung machen.

Der Qualitäts-Champion nutzt vorhandene Tools und dokumentierte Prozesse, z. B. das Anrufqualitätsdashboard (Call Quality Dashboard, CQD), um die Benutzerfreundlichkeit zu überwachen, Qualitätstrends zu erkennen und bei Bedarf eine Problembehebung zu ermöglichen.
Der Qualitäts-Champion sollte mit den jeweiligen Teams zusammenarbeiten, um Problembehebungsaktionen zu steuern und einem Lenkungsgremium Fortschritt und offene Probleme zu melden.

Lesen [Sie verbessern und überwachen](monitor-call-quality-qos.md)Sie die Anrufqualität für Teams . In diesem Artikel werden Aktivitäten beschrieben, die Aktivitäten bewerten und Anleitungen zur Problembehebung in wichtigen Bereichen bereitstellen, die den größten Einfluss auf die Verbesserung der Benutzerfreundlichkeit haben. Der Schwerpunkt der Anleitungen in diesem Artikel liegt auf der Verwendung des AQD als primäres Tool zum Melden und Untersuchen der einzelnen Bereich, mit dem Schwerpunkt auf Audio, um die Verbreitung und die Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Es wird dringend empfohlen, den Qualitäts-Champion frühzeitig zu benennen. Nachdem sie benannt wurden, sollten sie [](monitor-call-quality-qos.md) damit beginnen, sich mit dem Überwachen von Inhalten der Anrufqualität und zugehörigen Schulungsmaterialien vertraut zu machen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                               | Beschreibung                                                                                                                                                                                                                                                                                                 | Cadence                             | Team zugewiesen |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Verdingungs- und Zugqualitäts-Champion(n) | Sie können einen Qualitäts-Champion benannt und trainieren.                                                                                                                                                                                                                                                                   | Nach Bedarf                           |               |
| Durchführen von Qualitätsüberprüfungen (Quality of Experience Reviews, QERs)     | Führen Sie eine QER-Überprüfung durch, um Trends in Qualität und Zuverlässigkeit zu erkennen, gegenüber definierten Zielen zu überprüfen und den wichtigsten Projektbeteiligten in der Organisation Berichte zu erstellen.                                                                                                                            | Monatlich (wöchentlich während Bereitstellungen) |               |
| Laufwerkbereinigung                      | Koordinieren Sie die Wartungsmaßnahmen in der gesamten Organisation basierend auf den QER-Bewertungen und -Ergebnissen.                                                                                                                                                                                                           | Nach Bedarf                           |               |
| Aktualisieren von Gebäudedaten im AQD            | Aktualisieren oder fügen Sie neue Gebäudedefinitionen im CQD hinzu, wenn Änderungen am Netzwerk vorgenommen werden (siehe Hochladen [Gebäudeinformationen](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Nach Bedarf                           |               |
| Ausfüllen der Rolle "Qualitätschampion"      | End-to-End-Verantwortung für die Qualität in der Organisation. Dies umfasst:<ul><li>Stellen Sie sicher, dass die QER regelmäßig durchgeführt wird.</li><li>Berichten Sie den wichtigsten Projektbeteiligten über den Qualitätsstatus.</li><li>Stellen Sie sicher, dass die Definitionen der Gebäudedaten auf dem neuesten Stand sind.</li><li>Koordinieren Sie die Wartungsmaßnahmen in der gesamten Organisation, um sicherzustellen, dass die Benutzer über eine qualitativ hochwertige Erfahrung mit Teams.</li></ul>          | Täglich                               |               |



### <a name="references"></a>Referenzen 


[Hochladen mandanten- und gebäudedaten im AQD](CQD-upload-tenant-building-data.md)

[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft Teams Endpunkte können als alle PCs, Macs, Tablets oder mobilen Geräte definiert werden, auf Teams ausgeführt werden. Der Begriff *Endpunkt* umfasst nicht nur das Gerät selbst, sondern auch die Art und Weise, wie ein Benutzer eine Verbindung mit dem Gerät herstellt – z. B. mithilfe des integrierten Mikrofons oder Lautsprechers, der Ohrhörer oder eines optimierten Headsets. Nach der Bereitstellung dürfen Endpunkte nicht vergessen werden. Die Teams Endpunkte erfordern kontinuierliche Pflege und Wartung. In den folgenden Abschnitten werden bestimmte Bereiche beschrieben, auf die Sie sich konzentrieren können.

### <a name="endpoint-requirements"></a>Anforderungen an den Endpunkt

Einer der Wichtigsten von Teams besteht in der automatischen Veröffentlichung des Clients. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die Teams mobilen Apps werden in den jeweiligen App Stores auf dem aktuellen Stand gehalten.

Der Teams-Client hat Mindestanforderungen hinsichtlich der zugrunde liegenden Softwareplattform. Diese Anforderungen können sich im Laufe der Zeit ändern, daher ist es wichtig, dass Sie sie auf Änderungen überwachen. Der Client für Teams z. B. verfügt über eine iOS-Mindestversion. Wenn der Client einen Internetbrowser verwendet, muss der Browser ebenfalls auf dem aktuellen Stand gehalten werden. Eine Liste der unterstützten Plattformen finden Sie unter Clients für die [Microsoft Teams.](get-clients.md)

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können sich auf die Anrufqualität auswirken und sogar verhindern, dass ein Anruf eingerichtet wird. Nachdem die entsprechenden Ausschlüsse der Clientfirewall konfiguriert wurden, müssen sie basierend auf den Informationen in den Office 365 URLs und IP-Adressbereichen auf dem neuesten Stand [gehalten werden.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Ihr Drittanbieter hat spezifische Anleitungen zum Aktualisieren der Ausschlüsse.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Wi-Fi Treiber sind möglicherweise problematisch. Beispielsweise kann ein Treiber ein sehr aggressives Roamingverhalten zwischen Zugriffspunkten haben, das unnötige Zugriffspunktenwechsel auslösen kann, was zu einer schlechten Anrufqualität führt. Einen Treiber mit schlechter Wi-Fi kann eine Überprüfung der Qualität [](monitor-call-quality-qos.md) der Benutzererfahrung erkennen (weitere Informationen finden Sie unter Verbessern und Überwachen Teams Anrufqualität). Es ist von wesentlicher Bedeutung, einen qualitätsorientierten Prozess zu implementieren, der neue treiber Wi-Fi überwacht und sicherstellt, dass diese getestet werden, bevor sie für die allgemeine Benutzerbevölkerung bereitgestellt werden.

### <a name="endpoint-management"></a>Endpunktverwaltung

Ein Katalog unterstützter Endpunkte und Benutzeroberflächengeräte (z. B. Headsets) sollte verfügbar sein und verwaltet werden. Dieser Katalog enthält eine Liste der genehmigten Geräte, die ausgewählt und als Teil der Phase "Envision" und "Onboard" überprüft wurden. In der Regel werden bestimmte Geräte für jeden Personatyp in Ihrer Organisation ausgewählt, um die Anforderungen der Attribute dieser Persona zu erfüllen. Alle Endpunkte haben einen Lebenszyklus, und Sie müssen die Lieferantenverträge, Garantie-, Ersatz-, Verteilungs- und Reparaturrichtlinien verwalten, die diesen Geräten zugeordnet sind.

### <a name="endpoint-troubleshooting"></a>Problembehandlung für Endpunkte

Selbst wenn Sie die vorherigen Anweisungen befolgt haben, können benutzer in Ihrer Organisation weiterhin Probleme mit Teams. Obwohl das Problem möglicherweise nicht auf den Endpunkt selbst liegt, werden die Symptome des Problems in der Regel beim Benutzer über den Client angezeigt. Der folgende Leitfaden soll allgemeine Schritte bereitstellen, die Sie zum Beheben des Problems ausführen können. es ist nicht als umfassendes Handbuch zur Problembehandlung gedacht. Die Schritte werden in einer bestimmten Reihenfolge bereitgestellt, müssen aber nicht explizit befolgt werden und sind je nach Art des Problems möglicherweise nicht anwendbar.

1.  **Überprüfen des Dienstzustands:** Das Problem, das ein Benutzer möglicherweise hat, kann mit einem Ereignis in Zusammenhang stehen, das sich negativ auf den Teams Dienst oder seine abhängigen Dienste auswirkt. Als ersten Schritt sollten Sie bestätigen, dass keine Probleme mit dem aktiven Dienst auftreten. Weitere [Informationen finden Sie unter überprüfen Office 365 Dienstinte health](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Denken Sie daran, den Status abhängiger Dienste zu überprüfen (z. B. Exchange, SharePoint, OneDrive for Business). Die Überwachung des Dienstzustands wird im vorherigen Abschnitt Überwachen des [Dienstzustands ausführlicher erläutert.](#monitor-service-health)

2.  **Überprüfen der Clientkonnektivität:** Verbindungsprobleme verursachen Funktionalitäts- oder Anmeldeprobleme in Teams. Wir empfehlen (insbesondere für neue Websites oder Speicherorte), die Konnektivität mit dem Dienst zu überprüfen. Stellen Sie sicher, dass Office 365 Richtlinien zu URLs und [IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges) für jede Website befolgt werden. Sie können das [Microsoft-Netzwerkbewertungstool](https://www.microsoft.com/download/details.aspx?id=53885) verwenden, um einen Verbindungstest durchzuführen, um zu überprüfen, ob die Medienports ordnungsgemäß für Cloud-Sprachfunktionen geöffnet wurden. Detaillierte Schritte zum Ausführen der Konnektivitätstests finden Sie im Leitfaden zur [Netzwerkbereitschaft.](3-envision-evaluate-my-environment.md#network-readiness)

3.  **Überprüfen Sie die Liste der bekannten Probleme:** Wenden [Teams Problembehandlung](/MicrosoftTeams/troubleshoot/teams) an, um festzustellen, ob der Benutzer von einem dieser Probleme negativ betroffen ist. Folgen Sie der bereitgestellten Problemumgehung (sofern vorhanden), um das Problem zu beheben.

4.  **Besuchen Sie die Microsoft Teams Community:** Die [Microsoft Teams Community bietet](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) dedizierte Räume für Teams. Die Teams Community stellt eine Diskussionsliste, Blogbeiträge und Ankündigungen zur Teams. Sie können eine Frage posten oder frühere Diskussionen nach Lösungen für Ihr Problem durchsuchen.

5.  **Wenden Sie sich an den Microsoft-Support:** Sie können den Microsoft-Support kontaktieren, wenn Sie Probleme Teams online oder telefonisch haben. Weitere Informationen finden Sie unter [Kontaktieren des Support für Business-Produkte.](/microsoft-365/admin/contact-support-for-business-products)
    Für Premier-Kunden können Supportanfragen initiiert werden, indem Sie den Anweisungen unter Support kontaktieren für Microsoft Teams [(Premier-Kunden) folgen.](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                 | Beschreibung                                                                                                                                                                                                                                                                                                                                                                     | Cadence   | Team zugewiesen |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Anforderungen an den Endpunkt    | Stellen Sie sicher, dass Teams Endpunkt weiterhin alle Softwareanforderungen für die Teams, die unter Kunden für die [Microsoft Teams aufgeführt sind.](get-clients.md)                                                                                                                                                                                       | Monatlich   |               |
| Endpunktfirewalls       | Behalten Sie die entsprechenden Ausschlüsse der Endpunktfirewall auf der Grundlage der Informationen in den Office 365 [URLs und IP-Adressbereichen bei.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Ihr Drittanbieter hat spezifische Anleitungen für die Beibehaltung der Ausschlüsse. Abonnieren Sie den [RSS-Feed,](https://support.office.com/o365ip/rss) um automatisch über Änderungen benachrichtigt zu werden. | Nach Bedarf |               |
| WLAN-Treiber            | Testen und aktualisieren Wi-Fi Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe des AQD ( Verbessern und Überwachen der[Anrufqualität für Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Nach Bedarf |               |
| Endpunktverwaltung      | Verwalten Sie den Katalog der unterstützten Endpunkte und Schnittstellengeräte (z. B. Headsets). Verwalten Sie Lieferantenverträge, Garantie, Verteilung, Ersatz und Reparaturrichtlinien.                                                                                                                                                                                                        | Monatlich   |               |
| Problembehandlung für Endpunkte | Problembehandlungsaufgaben können das Überprüfen der Konnektivität, das Durchfragen der Liste bekannter Probleme, das Erfassen von Protokollen, die Analyse und die Eskalierung für den Microsoft-Support oder Drittanbieter umfassen.                                                                                                                                                                                               | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Clients für Microsoft Teams abrufen](get-clients.md)

[Microsoft Teams Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products)

[Premier-Support kontaktieren](https://support.microsoft.com/premier/contacts)

[Problembehandlung Teams Video](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Microsoft Teams Dienst bereitgestellt wurde, müssen Sie mehrere Aktivitäten im Zusammenhang mit seiner Verwaltung ausführen. Die Aktivitäten reichen von der Verwaltung des Diensts und einzelner Benutzer bis zur Kapazitätsplanung und Bereitstellung von Lizenzen und Telefonnummern. In den folgenden Abschnitten werden einige der allgemeinen Verwaltungsaufgaben beschrieben.

### <a name="service-administration"></a>Dienstverwaltung

Der Teams dienst verfügt über mehrere Einstellungen, die mandantenweit konfiguriert werden können.
Änderungen, die an den Mandanteneinstellungen vorgenommen werden, wirken sich auf alle Benutzer aus, die für die Mandanten Teams. Eine detaillierte Liste dieser Einstellungen finden Sie unter Verwalten [Microsoft Teams Einstellungen für Ihre Organisation.](enable-features-office-365.md)

### <a name="user-administration"></a>Benutzerverwaltung

Zur Unterstützung von Benutzern kann eine Organisation eine beliebige Anzahl zusammen bezogener Vorgänge erfordern – die jeweiligen Aufgaben variieren von einer Organisation zur nächsten. Diese Vorgänge müssen letztendlich von einem Supportteam verwaltet werden, dem diese betriebsbereiten Aufgaben zugewiesen wurden. Die folgenden Aufgaben sind häufig erforderlich, um Benutzer in der Teams.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Allgemeine Aufgaben für Telefonsystem

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

Wenn Ihre Organisation wächst oder Verträge einnimmt, ist es wichtig, dass Sie die Lizenzierung für aktuelle und zukünftige Anforderungen planen. Zusätzlich zur Lizenzierung Teams Cloud-Sprachfunktionen[(Telefonsystem](here-s-what-you-get-with-phone-system.md) [audio conferencing)](https://products.office.com/skype-for-business/audio-conferencing)gibt es eine Basislizenz für Audiokonferenzen.

Für Teams sind für Telefonsystem zugeordnete [Anrufplanlizenzen](calling-plan-landing-page.md) erforderlich. Mit der Anrufplanlizenzierung können Sie Inlands- und/oder Auslandsanrufe erstellen und empfangen. Diesen Plänen sind nutzungsbasierte Pläne mit zugeordneten Minutenpools. Durch die Bereitstellung [von Guthaben](what-are-communications-credits.md) für Kommunikationen wird sichergestellt, dass Ihnen der Dienst nie auslaufen wird.

Audiokonferenzen ermöglichen tolle Einwahlkonferenzen und nationale Einwahlkonferenzdienste. Gebührenfreie Einwahlkonferenz- oder nicht inlandsfreie Einwahlszenarien können zu zusätzlichen Gebühren führen, für die Guthaben für [Kommunikationen](what-are-communications-credits.md) erforderlich ist.

Guthaben für Kommunikationen kann sowohl die Lizenzen für Anrufplan- als auch Audiokonferenzen ergänzen. Sowohl Anrufplanlizenzen als auch Kommunikationsguthaben sind nutzungsbasierte Lizenzen und müssen daher entsprechend überwacht und bereitgestellt werden.

Mithilfe des [PSTN-Nutzungsberichts](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) können Sie die Nutzung von Anrufplanminuten und Guthaben für Kommunikationen überwachen. Basierend auf den Ergebnissen dieser Aktivität können Sie Ihre Lizenzierung entsprechend anpassen. In Kürze bieten wir einen Bericht zu [PSTN-Minutenpools](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) an, um diese Aufgabe effektiver zu unterstützen.

### <a name="telephone-number-management"></a>Verwaltung von Telefonnummern

Es gibt zwei Methoden zum Erwerben von Nummern in Teams: Sie können Telefonnummern von einem anderen Anbieter portieren oder die Nummern direkt aus dem Bestand der Microsoft-Telefonnummern bereitstellen. Beide Methoden werden unter [Abrufen von Telefonnummern für Ihre Benutzer beschrieben.](getting-phone-numbers-for-your-users.md)

Die Anzahl der Telefonnummern, die Sie aus dem Telefonnummernbestand von Microsoft bereitstellen können, ist begrenzt. Die Grenzwerte werden durch eine Reihe von Faktoren bestimmt, die unter Wie viele Telefonnummern können [Sie erhalten? detailliert festgelegt werden.](how-many-phone-numbers-can-you-get.md)
Die Grenzwerte hängen vom Typ der gebührenfreien Servicenummern, gebührenpflichtigen Leistungsnummern und Telefonnummern für Abonnenten (Benutzer) ab. Jede hat eigene Grenzwerte und muss unabhängig verwaltet werden. Wenn Sie sich dem Grenzwert nähern (oder das Limit erreicht haben), können Sie einen Inkrement bis zum Grenzwert anwenden. Dieser Vorgang wird in dem im vorherigen Absatz beschriebenen Artikel beschrieben.

Es kann sein, dass in einer Region, in der ein Dienst verfügbar ist, keine Nummer bereitgestellt werden kann. Informationen zum Verfahren zum Anfordern von Nummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

### <a name="team-creation-optional"></a>Teamerstellung (optional)

Standardmäßig besitzen alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Microsoft 365 Gruppen und daher eines Teams in Microsoft Teams. Wenn Sie die Erstellung neuer Teams [(und](assign-roles-permissions.md#permissions-to-create-teams) damit die Erstellung neuer Microsoft 365-Gruppen) enger steuern und einschränken möchten, können Sie Gruppenerstellungs- und -verwaltungsrechte an eine Gruppe von Administratoren delegieren. Wenn Ihre Organisation diese Option weiterververfolge möchten, lesen Sie den in diesem Artikel beschriebenen Prozess, um Benutzern das Übermitteln von Anforderungen zu ermöglichen, die von einem zugewiesenen Team verarbeitet werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität                    | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                             | Cadence   | Team zugewiesen |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Dienstverwaltung      | Verwaltung mandantenweite Teams Einstellungen.                                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Benutzerverwaltung         | Verwaltung von benutzerbasierten Einstellungen und Lizenzierung in Teams.                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Lizenzverwaltung          | Planen Sie die aktuellen und künftigen Anforderungen für benutzer- und verbrauchsbasierte Lizenzierung (Anrufpläne und Guthaben für Kommunikationen) unter Verwendung des PSTN-Nutzungsberichts und des [Berichts PSTN-Minutenpools.](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) [](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) | Wöchentlich    |               |
| Verwaltung von Telefonnummern | Verwalten Sie die Telefonnummern, die für zukünftiges Wachstum verfügbar sind, und passen Sie die Lagerbestände an Ihre Organisatorischen an.                                                                                                                                                                                                                                                                                                | Wöchentlich    |               |
| Teamerstellung (optional)    | Überprüfen und verarbeiten Sie Anforderungen für die Teamerstellung.                                                                                                                                                                                                                                                                                                                                                                          | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Verbessern und Überwachen der Anrufqualität

[Verbessern und Überwachen der Anrufqualität](monitor-call-quality-qos.md) für Teams umfasst eine Reihe von Aktivitäten, die Anleitungen zur Problembehebung in Schlüsselbereichen bewerten und bereitstellen, die den größten Einfluss auf die Verbesserung der Benutzerfreundlichkeit haben, wie unten dargestellt.

![Diagramm der Bereiche, die während einer Überprüfung der Qualität der Benutzererfahrung untersucht werden sollten](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während der Überprüfung der Qualität der Benutzerfreundlichkeit untersucht werden sollten: Audio, Zuverlässigkeit und Ergebnisse der Benutzerumfrage.")

Durch die kontinuierliche Bewertung und Behebung der im Leitfaden beschriebenen Bereiche können Sie ihr Potenzial verringern, die Benutzerfreundlichkeit zu beeinträchtigen. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration

-   Schlechte WLAN-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Verwendung nicht optimierter oder integrierter Audiogeräte

-   Problematische Subnetze oder Netzwerkgeräte

Der Schwerpunkt der Anleitungen unter Verbessern und Überwachen der Anrufqualität für [Teams](monitor-call-quality-qos.md) liegt auf der Verwendung des Anrufqualitätsdashboards (Anrufqualitätsdashboard) Online als primäres Tool zum Melden und Untersuchen der einzelnen beschriebenen Bereich, mit dem Schwerpunkt auf Audio, um die Verbreitung und die Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Es wird dringend empfohlen, den Qualitäts-Champion frühzeitig zu benennen. Nachdem sie benannt wurden, sollten sie sich mit den Inhalten unter Verbessern und Überwachen der Anrufqualität für Ihr [Teams.](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->