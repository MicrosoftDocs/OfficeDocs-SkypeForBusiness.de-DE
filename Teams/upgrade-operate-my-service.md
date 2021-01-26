---
title: Vorgänge für Microsoft Teams| Dienstverwaltung | Qualität
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Aufgaben und Aktivitäten, die für die Dienstverwaltung von Teams erforderlich sind, einschließlich Überwachung des Dienstzustands sowie Bewertung und Sicherstellung der Netzwerkqualität und -verwendung
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3180eabe2886faaade690f7a5bc0f3f97226589
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841496"
---
# <a name="operate-your-service"></a>Betreiben des Diensts

![Upgrade journey diagram, emphasizing the Operational Operational Excellence stage](media/upgrade-banner-op-excellence.png "Phasen des Upgradewegs, mit Betonung auf der Operational -2010-Phase")

Dieser Artikel ist Teil der Phase "Operational Excellence" Ihres Upgradewegs, die beginnt, sobald Sie das Upgrade von Skype for Business auf Teams abgeschlossen haben.

Dieser Artikel bietet eine Übersicht über die Anforderungen für den erfolgreichen Betrieb von Teams für Ihre Organisation nach dem Upgrade. Durch den ordnungsgemäßen Betrieb Ihrer Teams-Dienste können Sie sicher sein, dass Sie eine qualitativ hochwertige und zuverlässige Erfahrung für Ihre Organisation bereitstellen.

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Der Betriebsleitfaden bietet Ihnen einen Überblick über alle Aufgaben und Aktivitäten, die als Teil der Dienstverwaltungsfunktion für Microsoft Teams erforderlich sind.

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Dienst "Teams" umfasst Microsoft 365 oder Office 365 sowie die Infrastrukturkomponenten, die lokal bereitgestellt werden (z. B. Netzwerke).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Möglicherweise haben Sie bereits Prozesse und Aufgaben implementiert, die vorhandenen Diensten zugeordnet sind. Dies bedeutet, dass Sie Ihre aktuellen Prozesse wahrscheinlich erweitern können, wenn Sie die Dienstverwaltung heute für die zukünftige Unterstützung von Teams planen.

Die Dienstverwaltung umfasst alle Aktivitäten und Prozesse, die mit der Verwaltung von Teams von Ende bis Ende involviert sind. Wie bereits erwähnt, liegen einige Komponenten der Dienstverwaltung – die Infrastruktur, die der Microsoft 365- oder Office 365-Dienst selbst umfasst – in der Verantwortung von Microsoft, wohingegen Sie, der Kunde, Gegenüber Ihren Benutzern für die Verwaltung der verschiedenen Aspekte von Teams, des Netzwerks und der Endpunkte, die Sie bereitstellen, verantwortlich sind.

Die Aufgaben und Aktivitäten in diesem Leitfaden sind in acht Kategorien unterteilt, wie im folgenden Diagramm dargestellt. Jede dieser Kategorien wird in den folgenden Abschnitten erweitert.

![A diagram depicting a list of categories of tasks and activities](media/operate-my-service-image1.png "Ein Diagramm mit einer Liste von Kategorien von Aufgaben und Aktivitäten, die die Dienstverwaltung für Teams umfasst. Das Diagramm zeigt auch, dass die Dienstverwaltung größtenteils eine Kundenaufgabe ist.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie Vorgänge für Teams implementiert werden.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Sehen Sie sich das Betriebshandbuch vollständig an.</li><li>Implementieren Sie eine Betriebsstrategie, die sich an den Zielen Ihrer Organisation an der Bereitstellung der Qualität und Zuverlässigkeit von Teams-Workloads richtet.</li><li>Lesen Sie den Leitfaden zur Überprüfung der Qualität der Benutzererfahrung.</li><li> Implementieren Sie eine Betriebsstrategie, um regelmäßig Überprüfungen zur Qualität der Benutzererfahrung durchzuführen, um sicherzustellen, dass Ihre Teams-Bereitstellung auf Spitzenleistung ausgeführt wird.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die Planung der Vorgänge in der Zielphase ist von entscheidender Bedeutung, da die Betriebsaktivitäten beginnen, wenn die ersten Pilotbenutzer aktiviert sind. In diesem Leitfaden sind die Aktivitäten und Aufgaben aufgeführt, die täglich, wöchentlich, monatlich oder nach Bedarf ausgeführt werden müssen, um eine qualitativ hochwertige Bereitstellung von Teams zu pflegen. Dieses Handbuch enthält Wissen und Anleitungen zum Ausführen dieser kritischen Aktivitäten und Vorgänge.

Eine wichtige Komponente einer erfolgreichen Bereitstellung besteht in der Sicherstellung, dass die Planung, die Sie frühzeitig in der Zielphase planen, auch die Ermittlung umfasst, wer für die Durchführung bestimmter Aktivitäten zuständig sein soll. Nachdem Sie herauszufinden, welche Aufgaben und Aktivitäten für Ihre Bereitstellung gelten, müssen sie verstanden werden und von den Gruppen oder Personen gefolgt werden, die Sie ihnen zuweisen.

Jedes Team, das Sie bestimmen, muss die identifizierten Aufgaben und Zuständigkeiten überprüfen und zustimmen und mit der Vorbereitung beginnen. Dies kann Schulungen und Bereitschaft umfassen, Aktualisierungen des Personalplans bereitstellen oder sicherstellen, dass externe Anbieter bereit für die Bereitstellung sind.

Die in diesem Handbuch definierten Aktivitäten und Rollen sollten in den meisten Szenarien gültig sein, aber jede #A0 ist eindeutig. Daher können Sie dieses Handbuch als Ausgangspunkt verwenden, um die Aktivitäten und Standardrollen an Ihre Anforderungen anzupassen.

Stellen Sie sicher, dass jedes verständigte Team über gute Kenntnisse der Aktivitäten verfügt, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass jedes Team seine Verantwortlichkeit in Ihrer Organisation annimmt und abschreibt, bevor das erste Pilotprojekt beginnt.

Nachdem eine Vereinbarung in Betrieb ist, sollten die entsprechenden Teams mit der Operationalisierung ihrer Rollen beginnen.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument, um die Operational Role Mapping Übung zu vereinfachen.</li><li>Treffen Sie sich mit den jeweiligen Supportteams, um jedem Element in der Liste der erforderlichen Aktivitäten Namen zuzuordnen.</li><li>Gewinnen Sie Anerkennung oder Anerkennung für die zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams über die geeigneten Schulungen, Bereitschaft und Ressourcen verfügen, um die erforderlichen Aktivitäten zu unternehmen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dienstabhängigkeiten in Teams

Microsoft Teams bringt Technologien aus Microsoft 365 und Office 365 zusammen, um einen Hub für Teamarbeit zu bieten. Beispiele hierfür sind:

- Azure Active Directory (Azure AD) stellt Authentifizierungs- und Autorisierungsdienste für Teams bereit.

- Exchange Online bietet erweiterte Features wie gesetzliches Halten und E-Discovery.

- SharePoint Online bietet die Möglichkeit, Dateien in Kanälen zu teilen, und OneDrive for Business stellt einen Mechanismus zum Freigeben von Dateien in einem privaten Chat zur Verfügung.

Organisationen können auch vorhandene Investitionen in die lokale Infrastruktur nutzen. So können beispielsweise vorhandene lokale Active Directory-Konten für die Authentifizierung verwendet werden, indem Azure AD Connect genutzt wird. Bestimmte Versionen von Exchange Server können statt Exchange Online verwendet werden.

Diese Technologien sind eine umfassende, gemeinsame und intelligente Kommunikationssuite für Benutzer. Diese enge Integration ist ein wesentlicher Vorteil von Teams, macht aber auch eine Anforderung für die Dienstverwaltung über diese Technologien hinweg erforderlich.

In diesem Leitfaden werden die wichtigsten Schwerpunktbereiche für die Verwaltung des Teams-Diensts behandelt. Höchstwahrscheinlich verfügen Sie über Serviceverwaltungspläne für die unterstützenden Technologien, von der Teams abhängt. Andern falls nicht, müssen Sie auch für diese Technologiekomponenten (sowohl lokal als auch online) geeignete Dienstverwaltungspläne einrichten. Dies hilft Ihnen sicherzustellen, dass Ihre Benutzer eine qualitativ hochwertige und zuverlässige Erfahrung mit Teams genießen.

#### <a name="references"></a>Referenzen

[Übersicht über Microsoft Teams](teams-overview.md)

[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

[Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Aktivitäten im Betriebshandbuch

In den folgenden Abschnitten finden Sie eine Übersicht über die Aktivitäten, die erforderlich sind, um den Microsoft Teams-Dienst erfolgreich zu betreiben. Sie enthalten Verweise auf Tools, Kontextinformationen und zusätzliche Inhalte, die Ihnen helfen, die Aktivität zu verstehen und bei Bereitschaftsinitiativen zu unterstützen.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Überwachen des Dienstzustands

Es ist wichtig, dass Sie den Gesamtzustand des Microsoft Teams-Diensts verstehen, damit Sie andere Personen in Ihrer Organisation proaktiv über alle Ereignisse warnen können, die sich auf den Dienst auswirkt. Wie zuvor beschrieben, ist Teams von anderen Microsoft 365- und Office 365-Diensten wie Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business abhängig. Daher ist es ebenso wichtig, dass Sie die Integrität der abhängigen Dienste überwachen.

Integrieren Sie diese Aktivität in Ihren Vorfallverwaltungsprozess, um Benutzer, den Helpdesk und Ihre Betriebsteams proaktiv zu informieren, um sich auf die Handhabung von Benutzereskalation vorzubereiten.

In den folgenden Abschnitten werden die Tools beschrieben, die Sie zur Überwachung auf [Servicevorfälle](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) nutzen können, die sich auf den Teams-Dienst auswirken. In der folgenden Tabelle ist eine Zusammenfassung der Vorteile der einzelnen Tools enthalten, und wann Sie die einzelnen Tools verwenden sollten.

| Überwachungstool | Vorteile | Verwendung |
|---|---|---|
| Microsoft 365 Admin Center | Von jedem Gerät mit einem unterstützten Browser verfügbar. | Verwenden Sie diese Benachrichtigungen, wenn Sie keine Echtzeitbenachrichtigungen benötigen. |
| Microsoft 365-Administrator-App | Stellt Pushbenachrichtigungen für Ihr mobiles Gerät zur Anwendung. | Verwenden Sie diese Anwendung, wenn Sie unterwegs über Servicevorfälle benachrichtigt werden müssen. |
| Microsoft System Center | Integration in Microsoft System Center. | Verwenden Sie diese Funktion, wenn Sie erweiterte Überwachungsfunktionen und Benachrichtigungsunterstützung benötigen. |
| Microsoft 365-Dienstkommunikations-API | Programmgesteuerter Zugriff auf den Dienstzustand von Microsoft 365 oder Office 365. | Verwenden Sie diese Anwendung, wenn Sie die Integration mit einem Drittanbieterüberwachungstool benötigen oder eine eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, denen die Rolle des **globalen Administrators oder** **Dienstadministrators** zugewiesen ist, können den Dienstzustand anzeigen.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Überwachen mit dem Microsoft 365 Admin Center

Das [Microsoft 365 Admin Center](https://portal.office.com/) stellt ein Dashboard ["Dienstinte](https://portal.office.com/adminportal/home#/servicehealth) health" zur Verfügung, in dem Sie zusätzlich zu abhängigen Diensten den aktuellen Status des Teams-Diensts anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachen mit der mobilen App

Die Microsoft 365-Administrator-App ist für Apple iOS, Android und Windows (PC und Mobile) verfügbar. Die App stellt Dienstadministratoren Informationen zum Dienstzustand und zu bevorstehenden Änderungen zur Verfügung. Die App unterstützt Pushbenachrichtigungen, die Sie fast unmittelbar nach dem Posten einer Empfehlung warnen können. Auf diese Weise bleiben Sie über den Status, den Status und alle anstehenden Änderungen am Dienst auf dem Laufenden. Die Benachrichtigungsunterstützung macht sie zum empfohlenen Überwachungstool für Administratoren. Weitere Informationen finden Sie unter:

[Microsoft 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Herunterladen der mobilen Microsoft 365 Admin App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Überwachen mit Microsoft System Center

Microsoft System Center ist eine integrierte Verwaltungsplattform, die Ihnen hilft, Rechenzentren, Clientgeräte und hybride Cloud-IT-Umgebungen zu verwalten. Microsoft 365- oder Office 365-Administratoren, die System Center verwenden, haben jetzt die Möglichkeit, das Management Pack zu importieren, wodurch sie die gesamte Dienstkommunikation in Operations Manager in System Center anzeigen können. Mit diesem Tool erhalten Sie Zugriff auf den Status Ihrer abonnierten Dienste, aktive und gelöste Dienstvorfälle und Ihre Nachrichtencenterkommunikation (anstehende Änderungen). Weitere Informationen finden Sie im folgenden [Blogbeitrag.](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/)

Wenn Sie System Center zum Überwachen des Dienstzustands von Teams (und abhängiger Dienste) verwenden, können Sie das Management Pack weiter anpassen, um bestimmte Gruppen oder Personen, die identifiziert wurden, um auf Vorfälle zu reagieren, zu benachrichtigen oder zu benachrichtigen.
Diese Gruppen können Dienstbesitzer, Helpdesks, Supportgruppen der zweiten und dritten Ebene sowie Vorfallmanager in Ihrer Organisation umfassen.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachen erweiterter Szenarien

Sie können den Dienstzustand und anstehende Änderungen überwachen, indem Sie die Dienstkommunikations-API nutzen, um programmgesteuert auf den Dienstzustand und Änderungen zu zugreifen. Verwenden Sie diese API, um ein eigenes Überwachungstool zu erstellen oder Ihre vorhandenen Überwachungstools mit der Microsoft 365- oder Office 365-Dienstkommunikation zu verbinden, was möglicherweise die Überwachung Ihrer Umgebung vereinfacht. Weitere Informationen finden Sie unter [Microsoft 365 oder Office 365 für Enterprise-Entwickler.](https://docs.microsoft.com/office/developer-program/microsoft-365-developer-program-faq)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Überwachen des Dienstzustands | Überwachen Sie den Dienstzustand von Microsoft Teams (und abhängigen Diensten) proaktiv mithilfe der verfügbaren Tools. Abhängige Dienste sind: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Echtzeit | |
| Vorfallbenachrichtigung | Benachrichtigen Sie interne Beteiligte über Ereignisse, die auswirkungen auf den Teams-Dienst haben. Interne Beteiligte können Benutzer, Helpdesks und Vorfallmanager sein. | Nach Bedarf | |

### <a name="references"></a>Referenzen

[Überprüfen des Dienstzustands von Microsoft 365 oder Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Dienstinte health and continuity](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von Organisationsänderung

Microsoft Teams ist ein cloudbasierter Dienst. Dies bietet die Möglichkeit, neue Features und Funktionen in einem schnellen Tempo bereitzustellen. Die Bereitstellung fortlaufender Innovationen ist für Organisationen ein offensichtlicher Vorteil, aber diese Änderungen müssen in Ihrer Organisation entsprechend verwaltet werden, um Widerstände oder Einekalkalation für den Helpdesk zu vermeiden.

Updates für Teams werden automatisch für Ihre Benutzer veröffentlicht. Ihre Benutzer verfügen immer über die neuesten Clients und Features, die im Dienst "Teams" verfügbar sind. Es ist nicht möglich, den Rollout von Updates für Teams für Ihre Benutzer zu verwalten, daher ist es von entscheidender Bedeutung, den Wandel durch effektive Kommunikationsprogramme, Schulungen und Einführungsprogramme zu verwalten. Wenn Ihre Benutzer sich der Änderung bewusst sind, sich über die Vorteile freuen und die neuen Funktionen nutzen können, können sie sich schneller anpassen und die Änderung &mdash; begrüßen.

### <a name="monitoring-for-change"></a>Überwachen auf Änderungen

Der erste Schritt bei der Änderungsverwaltung besteht in der Überwachung der Änderungen, die für Teams geplant sind. Die beste Quelle für die Überwachung dieser Änderungen ist [die Microsoft 365 Roadmap,](https://www.microsoft.com/microsoft-365/roadmap)in der Features aufgeführt werden, die sich derzeit in der Entwicklung befinden, für Kunden eingeführt oder vollständig gestartet wurden. Sie können nach Teams-spezifischen Features suchen, indem Sie den bereitgestellten Filter verwenden, oder Sie können die Roadmap für eine weitere Analyse in eine Excel-Datei herunterladen. Für jedes Feature enthält die Roadmap eine kurze Beschreibung zusammen mit dem erwarteten Veröffentlichungsdatum.

Im [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)erhalten Sie Informationen zu bewährten Methoden, Trends und Neuigkeiten zu Microsoft Teams-Produktupdates. Erwarten Sie, dass hier wichtige Featureupdates für Teams angekündigt werden. Sie können den Blog auch über einen RSS-Feed abonnieren. Sie können dann den [RSS-Feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direkt zu einem Teamkanal hinzufügen, sodass alle wichtigen Nachrichten direkt in Teams übermittelt werden.

Alle veröffentlichten Features werden in den [Versionshinweisen für Microsoft Teams dokumentiert.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Hier finden Sie eine Liste der Features, die für Desktop, Web und mobile Geräte veröffentlicht wurden. Die gleiche Gruppe von Versionshinweisen finden Sie auch auf der Registerkarte **"Neues"** in der [Hilfe.](get-help-in-microsoft-teams.md)

Machen Sie sich mit den verfügbaren Ressourcen vertraut, und stellen Sie sicher, dass Sie die geeigneten Besitzer zuweisen, um Änderungen zu überwachen.

### <a name="planning-for-change"></a>Planen von Änderungen

Nachdem Sie nun über bevorstehende Änderungen am Dienst "Teams" wissen, besteht der nächste Schritt in der Vorbereitung und Planung. Bewerten Sie jede Änderung, um zu bestimmen, welche Änderungen die Kommunikation mit Benutzern, Informationskampagnen, Schulungen für Supportteams oder -benutzer oder Kampagnen zur Bewertung und Einführung von Features erfordern. Dies ist die primäre Rolle eines Change Management Teams in Ihrer Organisation. Im Folgenden finden Sie eine Sammlung von Beispieltabellen, die Ihnen bei der Planung von Änderungen helfen können.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloudaufzeichnung (Veröffentlichungsdatum: Januar 2018)

**Allgemeine Nachverfolgung**

| Änderungsbereitschaft | Status | Hinweise/nächste Schritte | Besitzer |
|---|---|---|---|
| Rechtliche Überprüfung | Abgeschlossen | Dieses Feature ist Voraussetzung für das Onboarding des Schulungsteams. | Projektteam |

**Verwaltung technischer Änderungen**

| Änderungsbereitschaft | Status | Hinweise/nächste Schritte | Besitzer |
|---|---|---|---|
| IT-Änderungen erforderlich | Ja | Der Administrator muss die Aufzeichnung nur für identifizierte Benutzer aktivieren. | Supportteam |
| Technische Bereitschaft abgeschlossen | Ja | | Supportteam |
| | | | |

**Benutzeränderungsverwaltung**

| Änderungsbereitschaft | Status | Hinweise/nächste Schritte | Besitzer |
|---|---|---|---|
| Auswirkungen des Benutzers | Niedrig | | |
| Benutzerbereitschaft erforderlich | Ja | | |
| Kommunikation bereit | Nein | Kommunikations-E-Mails wurden erstellt – ausstehende Überprüfung. | Kommunikationsteam |
| Schulung bereit | Ja | Die Schulung nutzt vorhandenes Microsoft-Video. | Schulungsteam |

**Statusspur**

| Änderungsbereitschaft | Status | Hinweise/nächste Schritte | Besitzer |
|---|---|---|---|
| Veröffentlichungsstatus | wird ausgeführt | Ausstehende Überprüfung durch den Executive Sponsor. | Change Management Team |
| Freigabe-Abmeldung | | | |
| Veröffentlichungsdatum | | | |

Weitere Informationen zur Planung des Change Managements mit Teams finden Sie unter ["Erstellen einer Änderungsverwaltungsstrategie für Microsoft Teams".](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität| Beschreibung| "Cadence"| Zugewiesenes Team |
|---|---|---|---|
| Überwachen auf Änderung| Überwachen Sie den Microsoft Teams-Dienst auf bevorstehende Änderungen.| Täglich||
| Planen von Änderungen| Bewerten und planen Sie neue Features und Funktionen, einschließlich Kommunikationsplänen, Informationskampagnen und Schulungen.| Nach Bedarf ||
| Benutzerbereitschaft| Führen Sie gezielte Kommunikation, Informationen oder Schulungskampagnen durch, um sicherzustellen, dass die Benutzer für die bevorstehende Änderung bereit sind.| Nach Bedarf ||
| Supportteambereitschaft | Führen Sie gezielte Kommunikation, Information oder Schulungskampagnen durch, um sicherzustellen, dass das Supportteam bereit ist. Supportteams können das "weiße" Team, Helpdesks, Support der Stufe 2 oder Stufe 3, externe Partner und so weiter umfassen. | Nach Bedarf ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten der Nutzung von Teams

Nachdem das erste Pilotprojekt begonnen hat, ist es wichtig, einen regelmäßigen Zeitfrequenz zum Messen der tatsächlichen Nutzung von Teams zu erstellen. Auf diese Weise kann Ihre Organisation Einblicke gewinnen, wie die tatsächliche Nutzung an der Nutzung ausgerichtet ist, die Sie in der Zielphase vorhergesagt haben. Obwohl sich der Schwerpunkt dieses Abschnitts auf der Nutzung von Microsoft Teams konzentriert, sollte dies Teil eines breiteren Rahmens sein, um die Nutzung von Microsoft 365 oder Office 365 insgesamt zu messen und zu bewerten.

Eine häufige Überprüfung der Nutzung zu einem frühen Bereitstellungsdatum bietet Ihnen die Möglichkeit:

- Überprüfen Sie, ob Benutzer Teams verwenden.

- Identifizieren Sie potenzielle Herausforderungen bei der Einführung, bevor sie zu kritischen Problemen in der gesamten Organisation führen.

- Verstehen Sie, ob es Abweichungen zwischen den Anforderungen der Zielphase und der tatsächlichen Nutzung gibt.

Wenn die Nutzung nicht Ihren Erwartungs wegen eines Bereitstellungsproblems oder einer nicht ordnungsgemäßen Ausführung des Einführungsplans oder eines anderen Problems führen kann. Abhängig vom tatsächlichen Grund für die geringe Nutzung muss der Dienstadministrator mit den zugehörigen Teams zusammenarbeiten, um Verwendungsbarrieren zu beseitigen.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Messen der Nutzung mit dem Microsoft 365 Admin Center

Nutzungsdaten von Teams sind im Berichterstellungsdashboard verfügbar. Daten zur Nutzung von Teams finden Sie in drei verschiedenen Berichten. Der erste Bericht bietet eine produktübergreifende Ansicht der Kommunikation und Zusammenarbeit der Benutzer mithilfe der verschiedenen Dienste in Microsoft 365 oder Office 365. Dieser Bericht finden Sie hier: [Microsoft 365-Berichte im Admin Center – Aktive Benutzer](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Die anderen beiden Berichte sind Teams-spezifisch und liefern aus Benutzer- und Geräteperspektive weitere Details zur Nutzung von Teams. Beide Berichte finden Sie hier:

[Microsoft Teams – Gerätenutzungsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams – Benutzeraktivitätsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Auf die Verwendungsberichte im Admin Center können Personen  zugreifen, denen eine globale Administratorrolle oder eine produktspezifische Administratorrolle zugewiesen wurde **(Exchange-Administrator,** **Skype for Business-Administrator,** **SharePoint-Administrator).**

Darüber hinaus steht **die** Rolle des Lesers für Berichte für Benutzer zur Verfügung, die Zugriff auf die Berichte benötigen, aber keine Aufgaben ausführen, die Berechtigungen auf Administratorebene erfordern. Sie weisen diese Rolle zu, um allen Beteiligten Nutzungsberichte zur Verfügung zu stellen, um die Akzeptanz zu überwachen und zu unterstützen. Weitere Informationen zu den verschiedenen verfügbaren Rollen finden Sie unter ["Informationen zu Administratorrollen von Microsoft 365".](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Bewerten der Nutzung

Nachdem Sie das Berichterstellungsdashboard zum Messen der Nutzung verwendet haben, ist es wichtig, die gemessene Nutzung mit allen Key Success Indicators (KSIs) zu vergleichen, die Sie während der Projekterstellungsphase definiert haben. Sie können ein KSI definieren, das möglicherweise als aktive Nutzung definiert ist, oder eine, die indirekt mit der aktiven Nutzung verknüpft ist.

Es ist wichtig, alle Abweichungen zwischen der tatsächlichen und der geplanten Nutzung zu ermitteln, bevor Sie das Rollout auf weitere Websites oder Benutzer fortsetzen. Wahrscheinlich identifizieren Sie im Rahmen dieser Aktivität organisationsorganisatorische Lernergebnisse, die Sie nutzen können, um sicherzustellen, dass für die nächste Gruppe von Websites oder Benutzern nicht dieselben Probleme auftreten.

Zuerst sollten Sie genau bestimmen, ob es sich um ein Verbreitungs- oder technisches Problem handelt. Beginnen Sie mit der Untersuchung der unten aufgeführten Elemente, um festzustellen, wo das Problem liegt.

1. Überprüfen Sie die Qualität, indem Sie eine [Überprüfung der Qualität der Benutzererfahrung durchführen.](upgrade-monitor-quality.md)

2. Arbeiten Sie mit dem Helpdeskteam zusammen, um zu überprüfen, ob es keine trendenden technischen Probleme gibt, die benutzer am Zugriff auf oder die Verwendung des Diensts verhindern. Wenn Problemtrends vorhanden sind, verwenden Sie den Abschnitt zur Problembehandlung am Endpunkt weiter später in diesem Artikel, um zu versuchen, das Problem zu beheben, bevor Sie Unterstützung engagieren. [](#endpoint-troubleshooting)

3. Arbeiten Sie mit dem Schulungs- und Einführungsteam zusammen, um direktes Feedback von Benutzern zu sammeln (siehe "Bewerten der Benutzerwahrnlichkeiten später in diesem Artikel"), und um die Effektivität des Bewusstseins und der Verbreitungsaktivitäten zu überprüfen. [](#assess-user-sentiment)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Nutzung messen (Aktivierungsphase) | Messen und bewerten Sie die Nutzung von Teams, da Websites während der Aktivierungsphase weiterhin onboardiert werden. Beheben Sie Verwendungsprobleme nach Bedarf. | Wöchentlich | |
| Messen der Nutzung | Messen und bewerten Sie die Nutzung von Teams in der Phase "Drive Value" (nach Abschluss der Bereitstellung). Beheben Sie Verwendungsprobleme nach Bedarf. | Zweiwochen | |
| (Drive Value Phase) | | | |
| Plan zur Aktualisierung der Einführung | Aktualisieren Sie Ihren Einführungsplan basierend darauf, wie sich die gemessene Nutzung mit Ihren Planungszielen vergleichen lassen. | Nach Bedarf | |

### <a name="references"></a>Referenzen

[Informationen zum Microsoft 365 Admin Center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Bewerten der Benutzerstimmung

Das Verständnis der Benutzerstimmung kann ein wichtiger Indikator für den Erfolg Ihrer Teams-Bereitstellung sein. Benutzerfeedback kann Änderungen in Ihrer Organisation unterstützen. dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise umfassen, wie Sie Ihren Benutzern Support anbieten.

Es ist wichtig, frühzeitig Feedback zu erhalten und mit der Bewertung der Benutzerstimmung während des gesamten Projektlebenszyklus und darüber hinaus fortzufahren. Verwenden Sie die folgenden Richtlinien, um das Intervall zu ermitteln, in dem Ihre Organisation Feedback eins sucht:

- **Anfang des Projekts:** Indem Sie die Benutzerstimmung zu Projektbeginn bewerten, erhalten Sie frühzeitig einen Einblick in das Gefühl, wie sich Ihre Benutzer von der Teamerfahrung fühlen.

- **Nach wichtigen Meilensteinen:** Indem Sie während des gesamten Projektlebenszyklus Feedback sammeln, können Sie die Benutzerstimmung fortlaufend messen und bei Bedarf Änderungen vornehmen. Dies ist besonders nach größeren Meilensteinen hilfreich.

- **Projektabschluss:** Wenn Sie die Einschätzung der Benutzer am Ende eines Projekts bewerten, können Sie sehen, wie gut Sie bereits vorgegangen sind und wo noch Arbeit zu erledigen ist. Außerdem können Sie die Ergebnisse mit der vorherigen Umfrage vergleichen.

- **Fortlaufend:** Messen Sie die Benutzerstimmung weiterhin auf unbestimmte Zeit. Änderungen der Benutzerstimmung können auf Änderungen in der Umgebung Ihrer Organisation oder auf Änderungen im Dienst "Teams" bzw. Indem Sie die Benutzerfreundlichkeit in regelmäßigen Zeitabständen überprüfen, können Sie verstehen, wie gut Ihre Dienstverwaltungsteams abarbeiten und wie Ihre Organisation auf Änderungen im Teamdienst reagiert.

Die Benutzerstimmung kann mit vielen unterschiedlichen Methoden bewertet werden. Dazu können E-Mail-Umfragen, Persönliches oder Vorstellungsgespräch im Telefonstil gehören oder einfach einen Feedbackkanal in Teams oder Yammer. Weitere Informationen finden Sie unter ["Bewährte Methoden für Benutzerfeedbackmethoden in Microsoft Teams".](best-practices-feedback.md)

Sie können auch einen branchenweiten Ansatz verwenden, um das Benutzerkonzept zu bewerten, das als Net Pro score (NPS) bezeichnet wird. Dies wird im folgenden Abschnitt beschrieben.

### <a name="nps"></a>NPS

Der Net Promoter Score (NPS) ist eine branchenweite Kundentreuemetrik und ein guter Ansatz zum Bewerten der Benutzerstimmung. NPS kann berechnet werden, indem zwei Fragen gestellt werden: "Wie wahrscheinlich ist es, dass Sie Teams einem Kollegen empfehlen?", gefolgt von der Freihandfrage "Warum?"

NPS ist ein Index im Bereich von -100 bis 100, der die Bereitschaft eines Kunden misst, das Produkt oder die Dienstleistung eines Unternehmens zu empfehlen. NPS basiert auf einer anonymen Umfrage, die benutzern per E-Mail oder auf andere elektronischem Weg zugestellt wird. NPS misst die Kundentreue zwischen einem Anbieter und einem Verbraucher. Sie besteht aus nur einer Frage, in der die Benutzer gefragt werden, ob sie ihre Erfahrung mit 1 bis 10 bewerten können, und sie können zusätzliche Kommentare bereitstellen. Die Benutzer werden dann basierend auf den folgenden Bewertungen klassifiziert:

- 9 oder 10 sind Organisatoren: Loyale Fans, die für Ihren Dienst werben und andere besennen.

- 7 oder 8 sind passive: Zufrieden, aber unenthustisch, anfällig für einen anderen Dienst oder ein anderes Angebot.

- Von 1 bis 6 sind Verdingungsschwörer: Unzufriedene Kunden, die Ihren Dienst beschädigen können und das Wachstum behindern können.

![Ein Diagramm zur Darstellung der NPS-Skala](media/operate-my-service-image2.png "Dieses Diagramm veranschaulicht die NPS-Skala. Es zeigt, dass Rangfolge von 0 bis 6 Verdingungen sind, 7 bis 8 passive und 9 bis 10 Organisatoren sind.")

Obwohl die Basis-NPS-Zahl nützlich ist, erhalten Sie den größten Nutzen aus der Analyse von Benutzerkommentaren. Sie helfen Ihnen zu verstehen, warum der Benutzer Teams anderen Benutzern empfehlen würde (oder nicht). Diese Kommentare können wertvolles Feedback liefern, damit die Projekt- oder Dienstverwaltungsteams die Anpassungen verstehen, die erforderlich sind, um einen qualitativ hochwertigen Dienst zu leisten.

Um NPS-Umfragen für Ihre Organisation zur Verfügung zu stellen, können Sie Ihr bevorzugtes Onlineumfragetool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/nach Bedarf ausgeführte Aufgaben

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Bewerten der Benutzerstimmung | Erfassen und bewerten Sie die Benutzerstimmungen mithilfe von Umfragen oder Vorstellungsgesprächen oder über einen Feedbackkanal in Teams oder Yammer. | Nach Bedarf | |
| Aktualisieren der Einführungspläne | Laufwerkänderung in Ihrer Organisation auf der Grundlage von Benutzerfeedback; dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise umfassen, wie Sie Ihren Benutzern Support anbieten. | Nach Bedarf | |

### <a name="references"></a>Referenzen

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden Yammer zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzerfeedback](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Viele wichtige Planungselemente werden in die Optimierung, die richtige Größenanpassung und die Behebung Ihrer Netzwerkinfrastruktur eingesetzt, um einen qualitativ hochwertigen und effizienten Pfad zum Microsoft Teams-Dienst sicherzustellen. Die Planungsaufgaben und Anforderungen werden in unserer Anleitung zur [Netzwerkbereitschaft](prepare-network.md) behandelt. Netzwerke entwickeln sich im Laufe der Zeit häufig aufgrund von Upgrades, Erweiterung oder anderen geschäftlichen Anforderungen. Es ist wichtig, dass Sie ihre Anforderungen an Teams in Ihren Netzwerkplanungsaktivitäten berücksichtigen.

Obwohl die Netzwerkplanung ein kritischer Aspekt einer Teams-Bereitstellung ist, ist es ebenso wichtig, dass das Netzwerk fehlerfrei bleibt und auf der Grundlage sich änderner geschäftlicher oder technischer Anforderungen auf dem Laufenden bleibt.

Um die Integrität Ihres Netzwerks sicherzustellen, müssen eine Reihe von Vorgängen in regelmäßigen Intervallen ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Überwachen von Microsoft 365- oder Office 365-IPs und -URLs | Überwachen Sie alle Änderungen an [office 365-URLs](https://aka.ms/o365ips) und -IP-Adressbereichen mithilfe des bereitgestellten [RSS-Feeds,](https://go.microsoft.com/fwlink/p/?linkid=236301) und initiieren Sie eine Änderungsanforderung an die entsprechenden Netzwerkgruppen. | Täglich | |
| Aktualisieren des Netzwerks basierend auf Änderungen an Microsoft 365- oder Office 365-IPs und URLs | Aktualisieren Sie die entsprechenden Netzwerkkomponenten (Firewalls, Proxyserver, VPNs, clientseitige Firewalls und so weiter), um Änderungen an den UrLs und IP-Adressbereichen von [Office 365](https://aka.ms/o365ips)widergespiegeln zu können. | Nach Bedarf | |
| Bereitstellen von Gebäudedaten | Stellen Sie aktualisierte Subnetzinformationen für den Qualitätschampion (oder die relevanten Projektbeteiligten) zur Verfügung, um sicherzustellen, dass die Gebäudedefinitionen [im AQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem neuesten Stand gehalten werden. | Nach Bedarf | |
| Implementieren von Änderungen | Implementieren Sie Änderungen im Netzwerk, um das Ändern geschäftlicher und technischer Anforderungen von Teams zu unterstützen. Zu den Netzwerkelementen zählen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul> | Nach Bedarf | |
| Netzwerküberwachung und -berichterstellung | Überwachen Sie das Ende-bis-Ende des Netzwerks auf Verfügbarkeit, Nutzung und Kapazitätstrends, indem Sie Ihre vorhandenen Netzwerkverwaltungstools und Berichterstellungsfunktionen von Drittanbietern verwenden, die von Ihren Netzwerkanbietern zur Verfügung stehen. Verwenden Sie Trenddaten für die Planung der Netzwerkkapazität. | Täglich, wöchentlich, monatlich | |
| Kapazitätsplanung | Arbeiten Sie mit den Dienstbesitzern von Teams zusammen, um zu verstehen, dass sich geschäftliche und technische Anforderungen ändern, die zusätzliche Kapazitätsänderungen zur Sichten haben könnten.  | Nach Bedarf | |
| Problembehandlung und Problembehebung im Netzwerk | Unterstützen Sie die Helpdesks, Dienstbesitzer und wichtigsten Projektbeteiligten bei der Problembehandlung und Problembehebung im Zusammenhang mit der Konnektivität, Zuverlässigkeit oder Qualität von Teams. Zu den Netzwerkelementen zählen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelte und Wi-Fi Netzwerke</li><li>Internetverbindung und ExpressRoute</li><li>DNS</li></ul> | Nach Bedarf | |
| Notfallwiederherstellung und Hochverfügbarkeitstests | Führen Sie regelmäßige Tests für hohe Verfügbarkeit und Notfallwiederherstellung in der Netzwerkinfrastruktur durch, um sicherzustellen, dass sie die festgelegten Ziele zum Servicelevel (SLOs) oder Vereinbarungen zum Servicelevel (Service Level Agreements, SLAs) für den Teams-Dienst erfüllt. | Monatlich | |

### <a name="references"></a>Referenzen

[URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365ips)

[Gebäudedatenschema](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und Sicherstellen der Qualität

Alle Organisationen benötigen eine Gruppe oder Einzelperson, um für die Qualität der Daten auf dem Konto zu sein. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Die Rolle "Quality Champion" wird einer Person oder Gruppe zugewiesen, die sich leidenschaftlich für die Benutzererfahrung ihrer Benutzer begeistert.
Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität der Organisation kann dies jede Person oder Gruppe sein, die mit Begeisterung für eine qualitativ hochwertige Benutzererfahrung sorgt.

Der Qualitätschampion nutzt vorhandene Tools und dokumentierte Prozesse, z. B. das Anrufqualitätsdashboard (CQD), und verbessert und überwacht die Anrufqualität für [Teams,](monitor-call-quality-qos.md)um die Benutzererfahrung zu überwachen, Qualitätstrends zu identifizieren und die Wartung bei Bedarf vordrangen.
Der Qualitätschampion sollte mit den jeweiligen Teams zusammenarbeiten, um Problembehebungsaktionen vordrangen und einem Lenkungsgremium informationen über den Fortschritt und alle offenen Probleme zu melden.

[Die Anrufqualität für Teams zu](monitor-call-quality-qos.md) verbessern und zu überwachen umfasst Aktivitäten, die Anleitungen zur Problembehebung in wichtigen Bereichen bewerten und bereitstellen, die den größten Einfluss auf die Verbesserung der Benutzerfreundlichkeit haben. Der Schwerpunkt der Anleitungen im Handbuch zur Qualitätsüberprüfung liegt auf der Verwendung von WebQualitätsqualitäts-Online als primäres Tool zum Melden und Untersuchen der einzelnen Bereich. Dabei liegt der Schwerpunkt auf der Audiowiedergabe, um die Verbreitung und die Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Es wird dringend empfohlen, den Qualitätschampion frühzeitig zu benennen. Nachdem sie benannt wurden, sollten sie damit beginnen, sich mit den Inhalten in "Verbessern" vertraut zu machen und die Anrufqualität für [Teams](monitor-call-quality-qos.md) und zugehörige Schulungsmaterialien zu überwachen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Team zugewiesen |
|---|---|---|---|
| Verdingungs- und Zugqualitäts-Champion(n) | Sie können einen Qualitätschampion benannt und trainieren. | Nach Bedarf | |
| Durchführen von Qualitätsüberprüfungen (Quality of Experience Reviews, QERs) | Führen Sie eine QER aus, um Qualitäts- und Zuverlässigkeitstrends zu erkennen, die definierten Ziele zu überprüfen und wichtige Projektbeteiligten in der Organisation zu melden. | Monatlich (wöchentlich während Bereitstellungen) | |
| Wartung von Laufwerken | Koordinieren Sie die Wartungsmaßnahmen in der gesamten Organisation basierend auf den Bewertungen und Ergebnissen der QER. | Nach Bedarf | |
| Aktualisieren von Gebäudedaten im AQD | Aktualisieren oder hinzufügen Sie neue Gebäudedefinitionen im CQD, wenn Änderungen am Netzwerk vorgenommen werden (siehe [Informationen zum Hochladen von Gebäude).](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | Nach Bedarf | |
| Ausfüllen der Rolle "Qualitätschampion" | End-to-End-Verantwortung für die Qualität in der Organisation. Dies umfasst:<ul><li>Stellen Sie sicher, dass die QER regelmäßig durchgeführt wird.</li><li>Berichten Sie den wichtigsten Projektbeteiligten über den Qualitätsstatus.</li><li>Stellen Sie sicher, dass die Definitionen der Gebäudedaten auf dem neuesten Stand sind.</li><li>Koordinieren Sie die Wartungsmaßnahmen in der gesamten Organisation, um sicherzustellen, dass die Benutzer über eine qualitativ hochwertige Erfahrung mit Teams verfügen.</li></ul> | Täglich | |

### <a name="references"></a>Referenzen

[Hochladen von Gebäudeinformationen](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft Teams-Endpunkte können als alle PCs, Macs, Tablets oder mobilen Geräte (oder mobilen Geräte) definiert werden, auf der der Teamclient ausgeführt wird. Der  Ausdrucksendpunkt umfasst nicht nur das Gerät selbst, sondern auch die Art und Weise, wie ein Benutzer eine Verbindung mit dem Gerät herstellt – z. B. mithilfe des integrierten Mikrofons oder Lautsprechers, der Ohrhörer oder eines optimierten Headsets. Nach der Bereitstellung dürfen Endpunkte nicht vergessen werden. Die Endpunkte von Teams erfordern fortlaufende Pflege und Wartung. In den folgenden Abschnitten werden bestimmte Bereiche beschrieben, auf die Sie sich konzentrieren können.

### <a name="endpoint-requirements"></a>Endpunktanforderungen

Einer der wichtigsten Vorteile von Teams ist, dass der Kunde automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die mobilen Apps von Teams werden über die jeweiligen App Stores auf dem aktuellen Stand gehalten.

Für den Teams-Client gelten Mindestanforderungen hinsichtlich der zugrunde liegenden Softwareplattform. Diese Anforderungen können sich im Laufe der Zeit ändern, daher ist es wichtig, dass Sie sie auf Änderungen überwachen. So verfügt der Teamclient beispielsweise über eine iOS-Mindestversion. Wenn der Client einen Internetbrowser verwendet, muss der Browser ebenfalls auf dem aktuellen Stand gehalten werden. Eine Liste der unterstützten Plattformen finden Sie unter ["Kunden für Microsoft Teams erhalten".](get-clients.md)

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können die Anrufqualität beeinträchtigen und sogar verhindern, dass ein Anruf eingerichtet wird. Nachdem die entsprechenden Ausschlüsse für die Clientfirewall konfiguriert wurden, müssen sie basierend auf den Informationen in [Office 365-URLs](https://aka.ms/o365ips)und -IP-Adressbereichen auf dem neuesten Stand gehalten werden. Ihr Drittanbieter hat spezifische Anleitungen zum Aktualisieren der Ausschlüsse.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Wi-Fi Treiber sind möglicherweise problematisch. Ein Treiber kann z. B. ein sehr aggressives Roamingverhalten zwischen Zugriffspunkten haben, das unnötigen Zugriffspunktwechsel auslösen kann, was zu einer schlechten Anrufqualität führt. Ein Treiber mit schlechter Wi-Fi kann durch eine Überprüfung der Qualität der Benutzererfahrung ermittelt werden (ausführlichere Informationen finden Sie unter "Verbessern und Überwachen der Anrufqualität für [Teams").](monitor-call-quality-qos.md) Es ist wichtig, einen qualitätsgesteuerten Prozess zu implementieren, der neue Treiber Wi-Fi überwacht und sicherstellt, dass sie getestet werden, bevor sie für die allgemeine Benutzergesamtheit bereitgestellt werden.

### <a name="endpoint-management"></a>Endpunktverwaltung

Ein Katalog unterstützter Endpunkte und Benutzeroberflächengeräte (z. B. Headsets) sollte verfügbar und gewartet werden. Dieser Katalog enthält eine Liste der genehmigten Geräte, die im Rahmen der Phase "Envision" und "Onboard" ausgewählt und überprüft wurden. In der Regel werden bestimmte Geräte für jeden Personentyp in Ihrer Organisation ausgewählt, um die Anforderungen der Attribute dieser Persona zu erfüllen. Alle Endpunkte haben einen Lebenszyklus, und Sie müssen die Lieferantenverträge, die Garantie, den Austausch, die Verteilung und die Reparaturrichtlinien verwalten, die diesen Geräten zugeordnet sind.

### <a name="endpoint-troubleshooting"></a>Problembehandlung am Endpunkt

Selbst wenn Sie die vorherigen Anleitungen befolgt haben, können benutzer in Ihrer Organisation weiterhin Probleme mit Teams haben. Obwohl das Problem möglicherweise nicht mit dem Endpunkt selbst besteht, werden die Symptome des Problems in der Regel dem Benutzer über den Client angezeigt. Die folgenden Anleitungen sollen allgemeine Schritte bereitstellen, die Sie zum Beheben des Problems ausführen können. es ist nicht als umfassendes Handbuch zur Problembehandlung gedacht. Die Schritte werden in einer bestimmten Reihenfolge bereitgestellt, müssen aber je nach Art des Problems nicht explizit befolgt werden und sind ggf. nicht anwendbar.

1. **Überprüfen des Dienstzustands:** Das Problem, das ein Benutzer möglicherweise hat, kann mit einem Ereignis verknüpft sein, das sich negativ auf den Dienst von Teams oder seine abhängigen Dienste auswirkt. Als ersten Schritt sollten Sie bestätigen, dass keine aktiven Dienstprobleme auftreten. Informationen [zum Überprüfen des Dienstzustands von Microsoft 365.](https://docs.microsoft.com/office365/enterprise/view-service-health) Denken Sie daran, den Status abhängiger Dienste (z. B. Exchange, SharePoint, OneDrive for Business) zu überprüfen. Die Überwachung des Dienstzustands wird im vorherigen Abschnitt, "Überwachen des Dienstzustands", [ausführlicher erläutert.](#monitor-service-health)

2. **Überprüfen der Clientkonnektivität:** Verbindungsprobleme verursachen Funktionalitäts- oder Anmeldeprobleme in Teams. Wir empfehlen (insbesondere bei neuen Websites oder Speicherorten), die Verbindung mit dem Dienst zu überprüfen. Stellen Sie sicher, dass die folgenden Richtlinien zu [Office 365-URLs](https://aka.ms/o365ips) und -IP-Adressbereichen für jede Website befolgt werden. Sie können das [Microsoft Netzwerkbewertungstool](https://www.microsoft.com/download/details.aspx?id=53885) verwenden, um einen Verbindungstest durchzuführen, um zu überprüfen, ob die Medienports für die Funktionen von Teams ordnungsgemäß geöffnet wurden. Detaillierte Schritte zum Ausführen der Konnektivitätstests finden Sie im Leitfaden zur [Netzwerkbereitschaft.](prepare-network.md)

3. **Überprüfen Sie die Liste der bekannten Probleme:** Sehen [Sie sich die Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) in Teams an, um festzustellen, ob der Benutzer von einem dieser Probleme negativ betroffen ist. Folgen Sie der bereitgestellten Problemumgehung (sofern vorhanden), um das Problem zu beheben.

4. **Besuchen Sie die Microsoft Teams-Community:** Die [Microsoft Teams Community bietet](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) dedizierte Bereiche für Teams. Die Teams-Community bietet eine Diskussionsliste, Blogbeiträge und Ankündigungen, die auf Teams zentriert sind. Sie können eine Frage posten oder frühere Diskussionen nach Lösungen für Ihr Problem durchsuchen.

5. **Wenden Sie sich an den Microsoft-Support:** Sie können sich bei Problemen mit Teams online oder telefonisch an den Microsoft Support wenden. Weitere Informationen finden Sie unter ["Support für Geschäftsprodukte kontaktieren – Hilfe für Administratoren".](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) Für Premiumkunden können Supportanfragen initiiert werden, indem sie den Anweisungen unter "Support kontaktieren" für [Microsoft Teams (Premier-Kunden) folgen.](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Endpunktanforderungen | Stellen Sie sicher, dass der Endpunkt von Microsoft Teams weiterhin alle Softwareanforderungen für Teams erfüllt, die unter ["Kunden für Microsoft Teams erhalten" aufgeführt sind.](get-clients.md) | Monatlich | |
| Endpunktfirewalls | Behalten Sie die geeigneten Ausschlüsse für die Endpunktfirewall auf der Grundlage der Informationen in [Office 365-URLs und -IP-Adressbereichen bei.](https://aka.ms/o365ips) Ihr Drittanbieter hat spezifische Anleitungen für die Beibehaltung der Ausschlüsse. Abonnieren Sie den [RSS-Feed,](https://support.office.com/o365ip/rss) um automatisch über Änderungen benachrichtigt zu werden. | Nach Bedarf | |
| WLAN-Treiber | Testen und aktualisieren Wi-Fi Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe des AQD (Verbessern und Überwachen der[Anrufqualität für Teams).](monitor-call-quality-qos.md) | Nach Bedarf | |
| Endpunktverwaltung | Verwalten Sie den Katalog der unterstützten Endpunkte und Schnittstellengeräte (z. B. Headsets). Verwalten Sie Lieferantenverträge, Garantie-, Verteilungs-, Ersatz- und Reparaturrichtlinien. | Monatlich | |
| Problembehandlung am Endpunkt | Problembehandlungsaufgaben können das Überprüfen der Konnektivität, das Befragen der Liste bekannter Probleme, das Erfassen von Protokollen, die Analyse und die Eskalierung für den Microsoft Support oder Drittanbieter umfassen. | Nach Bedarf | |

### <a name="references"></a>Referenzen

[URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365ips)

[Clients für Microsoft Teams abrufen](get-clients.md)

[Microsoft Teams Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Kontaktieren des Premier-Support](https://support.microsoft.com/premier/contacts)

[Video zur Problembehandlung in Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Microsoft Teams-Dienst bereitgestellt wurde, müssen Sie mehrere Aktivitäten im Zusammenhang mit seiner Verwaltung ausführen. Die Aktivitäten reichen von der Verwaltung des Diensts und einzelner Benutzer bis zur Kapazitätsplanung und Bereitstellung von Lizenzen und Telefonnummern. In den folgenden Abschnitten werden einige dieser allgemeinen Verwaltungsaufgaben beschrieben.

### <a name="service-administration"></a>Dienstverwaltung

Der Dienst "Teams" verfügt über mehrere Einstellungen, die mandantenweit konfiguriert werden können.
Änderungen an den Mandanteneinstellungen wirken sich auf alle Benutzer aus, die für Teams aktiviert wurden. Eine detaillierte Liste dieser Einstellungen finden Sie unter "Verwalten von [Microsoft Teams-Einstellungen für Ihre Organisation".](enable-features-office-365.md)

### <a name="user-administration"></a>Benutzerverwaltung

Zur Unterstützung von Benutzern erfordert eine Organisation möglicherweise eine beliebige Anzahl verwandter Aufgaben – die jeweiligen Aufgaben variieren von Organisation zu Organisation. Diese Aufgaben müssen letztendlich von einem Supportteam verwaltet werden, dem diese betrieblichen Aufgaben zugewiesen wurden. Die folgenden Aufgaben sind häufig erforderlich, um Benutzer in Teams zu unterstützen.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Teamerstellung (optional)

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über Berechtigungen zum Erstellen von Microsoft 365-Gruppen und somit eines Teams in Microsoft Teams. Wenn Sie eine engere Kontrolle haben und die Erstellung neuer Teams [(und](assign-roles-permissions.md#permissions-to-create-teams) damit die Erstellung neuer Microsoft 365-Gruppen) einschränken möchten, können Sie Gruppenerstellungs- und -verwaltungsrechte an eine Gruppe von Administratoren delegieren. Wenn Ihre Organisation diese Option weiterververfolge, lesen Sie den in diesem Artikel beschriebenen Prozess, um Benutzern das Übermitteln von Anforderungen zu ermöglichen, die von einem zugewiesenen Team verarbeitet werden.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/nach Bedarf

| Aktivität | Beschreibung | "Cadence" | Zugewiesenes Team |
|---|---|---|---|
| Dienstverwaltung | Verwaltung von mandantenweiten Teams-Einstellungen. | Nach Bedarf | |
| Benutzerverwaltung | Verwaltung von benutzerbasierten Einstellungen und Lizenzierung in Teams. | Nach Bedarf | |
| Lizenzverwaltung | Planen Sie die aktuellen und künftigen Anforderungen an die Benutzer- und nutzungsbasierte Lizenzierung (Anrufpläne und Guthaben für Kommunikationen), indem Sie den Bericht ["PSTN-Nutzung"](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) und den Bericht ["PSTN-Minutenpools"](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) nutzen. | Wöchentlich | |
| Verwaltung von Telefonnummern | Verwalten Sie die Telefonnummern, die für zukünftiges Wachstum verfügbar sind, und passen Sie die Lagerbestände an Ihre Organisationsanforderungen an. | Wöchentlich | |
| Teamerstellung (optional) | Überprüfen und verarbeiten Sie Anforderungen für die Teamerstellung. | Nach Bedarf | |

<!--ENDOFSECTION-->
