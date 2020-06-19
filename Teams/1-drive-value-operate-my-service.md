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
description: Aufgaben und Aktivitäten, die für die Verwaltung von Teams erforderlich sind, einschließlich der Überwachung des Dienststatus sowie der Beurteilung und Gewährleistung der Netzwerkqualität und-Nutzung.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e20023d1b79f4b5706301ef0cb1e670f35e8b5f
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761383"
---
# <a name="operate-my-service"></a>Verwenden des Diensts

In diesem Artikel finden Sie eine Übersicht über die Anforderungen für den erfolgreichen Betrieb von Cloud-VoIP-Diensten für Ihre Organisation. Durch die ordnungsgemäße Bedienung Ihrer Cloud-VoIP-Dienste können Sie sicherstellen, dass Sie eine qualitativ hochwertige und zuverlässige Benutzeroberfläche für Ihre Organisation bereitstellen.

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Im Betriebshandbuch erhalten Sie einen Überblick über alle Aufgaben und Aktivitäten, die im Rahmen der Dienstverwaltungsfunktion für Microsoft Teams erforderlich sind.

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Dienst "Teams" umfasst Microsoft 365 oder Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt werden (beispielsweise Netzwerke).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Möglicherweise haben Sie bereits Prozesse und Aufgaben implementiert, die vorhandenen Diensten zugeordnet sind. Allerdings können Sie Ihre derzeitigen Prozesse wahrscheinlich erweitern, wenn Sie planen, dass das Service-Management heute Teams in Zukunft unterstützt.

Das Dienstleistungsmanagement umfasst alle Aktivitäten und Prozesse, die in der End-to-End-Verwaltung von Teams beteiligt sind. Wie bereits erwähnt, sind einige Komponenten der Dienstverwaltung – die Infrastruktur, die der Microsoft 365-oder Office 365-Dienst selbst umfasst – für Microsoft verantwortlich, während Sie als Kunde für Ihre Benutzer verantwortlich sind, um die verschiedenen Aspekte von Teams, dem Netzwerk und den von Ihnen bereitgestellten Endpunkten zu verwalten.

Die Aufgaben und Aktivitäten in diesem Leitfaden sind in acht Kategorien unterteilt, wie in der folgenden Abbildung dargestellt. Jede dieser Kategorien wird in den folgenden Abschnitten erweitert.

![Ein Diagramm, das eine Liste der Kategorien von Aufgaben und Aktivitäten darstellt](media/operate-my-service-image1.png "Ein Diagramm, das eine Liste der Kategorien von Aufgaben und Aktivitäten darstellt, die von Service Management für Teams umfasst werden. Das Diagramm zeigt auch, dass die Dienstverwaltung größtenteils eine Kundenaufgabe ist.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie Vorgänge für Teams implementiert werden.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Überprüfen Sie den Betriebsleitfaden vollständig.</li><li>Implementieren Sie eine Betriebsstrategie, die mit den Zielen Ihrer Organisation übereinstimmt, um die Qualität und Zuverlässigkeit von Cloud-sprach Auslastungen zu gewährleisten.</li><li>Lesen Sie den Leitfaden zur Überprüfung der Qualität der Benutzerfreundlichkeit.</li><li> Implementieren Sie eine Betriebsstrategie, um regelmäßig Bewertungen der Qualität von Erfahrungen durchzuführen, um sicherzustellen, dass Ihre Cloud-VoIP-Bereitstellung mit ihren Spitzenfunktionen funktioniert.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die Planung, die Sie für Vorgänge während der enVision-Phase durchgeführt haben, ist wichtig, da die Vorgangs Aktivitäten beginnen, wenn die ersten Pilotbenutzer aktiviert sind. In diesem Leitfaden sind die Aktivitäten und Aufgaben aufgelistet, die täglich, wöchentlich, monatlich oder bedarfsorientiert ausgeführt werden müssen, um eine hochwertige Teams-Bereitstellung zu gewährleisten. Dieser Leitfaden enthält Kenntnisse und Anleitungen für die Durchführung dieser wichtigen Aktivitäten und Aufgaben.

Eine wichtige Komponente einer erfolgreichen Bereitstellung besteht darin, sicherzustellen, dass die Planung, die Sie zu einem frühen Zeitpunkt in der enVision-Phase durchführen, die Entscheidung umfasst, wer für die Ausführung bestimmter Aktivitäten verantwortlich ist. Nachdem Sie herausgefunden haben, welche Aufgaben und Aktivitäten für Ihre Bereitstellung gelten, müssen Sie von den Gruppen oder Personen, die Sie Ihnen zuweisen, verstanden und befolgt werden.

Jedes Team, das Sie identifizieren, muss die angegebenen Aufgaben und Zuständigkeiten überprüfen und sich damit einverstanden erklären und mit der Vorbereitung beginnen. Dazu gehören Schulung und Bereitschaft, die Bereitstellung von Updates für den Personalplan oder die Bereitstellung externer Anbieter.

Die in diesem Leitfaden definierten Aktivitäten und Rollen sollten in den meisten Szenarien gültig sein, aber jede Bereitstellung von Teams ist eindeutig. aus diesem Grund können Sie diesen Leitfaden als Ausgangspunkt verwenden, um die Aktivitäten und Standardrollen Ihren Anforderungen entsprechend anzupassen.

Stellen Sie sicher, dass jedes verantwortliche Team ein gutes Verständnis der Aktivitäten hat, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass die einzelnen Teams ihre Verantwortlichkeit in Ihrer Organisation akzeptieren und sich vor Beginn des ersten Pilotprojekts abmelden.

Nachdem eine Vereinbarung abgeschlossen ist, sollten die entsprechenden Teams beginnen, ihre Rollen zu übersetzen.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument, um die Übung zur operativen Rollenzuordnung zu vereinfachen.</li><li>Treffen Sie sich mit den jeweiligen Support Teams, um jedem Element in der Liste der erforderlichen Aktivitäten Namen zuzuweisen.</li><li>Erhalten Sie Akzeptanz oder Abmelden für die zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams über die entsprechenden Schulungs-, Bereitschafts-und Ressourcen verfügen, um die erforderlichen Aktivitäten abzuschließen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams-Dienstabhängigkeiten

Microsoft Teams vereint Technologien in Microsoft 365 oder Office 365, um einen Hub für Teamarbeit bereitzustellen. Beispiele sind:

-   Azure Active Directory (Azure AD) bietet Authentifizierungs-und Autorisierungsdienste für Teams.

-   Exchange Online bietet erweiterte Funktionen wie rechtliche Aufbewahrung und e-Discovery.

-   SharePoint Online bietet die Möglichkeit zum Freigeben von Dateien in Kanälen, und OneDrive for Business bietet einen Mechanismus zum Freigeben von Dateien in einem privaten Chat.

Organisationen können auch vorhandene Investitionen in die lokale Infrastruktur nutzen. Beispielsweise können vorhandene lokale Active Directory-Konten zur Authentifizierung verwendet werden, indem Sie Azure AD Connect nutzen. Bestimmte Versionen von Exchange Server können anstelle von Exchange Online verwendet werden.

Diese Technologien sind zusammen gekommen, um eine umfassende, kollaborative und intelligente Kommunikations Suite für Benutzer bereitzustellen. Diese enge Integration ist ein wichtiger Vorteil von Teams, aber auch eine Voraussetzung für das Service Management in diesen Technologien.

In diesem Leitfaden werden die wichtigsten Schwerpunkte für die Verwaltung des Teams-Diensts behandelt. Höchstwahrscheinlich verfügen Sie über Dienst Verwaltungspläne für die unterstützenden Technologien, von denen Teams abhängig sind. Wenn dies nicht der Fall ist, müssen Sie geeignete Service Management-Pläne für diese Technologiekomponenten (sowohl lokal als auch online) einrichten. So können Sie sicherstellen, dass Ihre Benutzer eine qualitativ hochwertige und zuverlässige Erfahrung mit Teams erhalten.

#### <a name="references"></a>Referenzen 

[Übersicht über Microsoft Teams](teams-overview.md)

[Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Aktivitäten des Arbeits Ratgebers

Die folgenden Abschnitte geben einen Überblick über die Aktivitäten, die für den erfolgreichen Betrieb des Microsoft Teams-Diensts erforderlich sind. Dazu gehören Verweise auf Tools, kontextbezogene Informationen und zusätzliche Inhalte, die Ihnen helfen, die Aktivitäten zu verstehen und in Bereitschafts Initiativen zu unterstützen.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Überwachen des Dienststatus

Es ist wichtig, dass Sie den allgemeinen Status des Microsoft Teams-Diensts verstehen, damit Sie andere Personen in Ihrer Organisation proaktiv über alle Ereignisse informieren können, die sich auf den Dienst auswirken. Wie zuvor beschrieben, sind Teams von anderen Microsoft 365-oder Office 365-Diensten wie Azure Active Directory, Exchange Online, SharePoint Online und OneDrive for Business abhängig. Aus diesem Grund ist es genauso wichtig, dass Sie die Integrität der abhängigen Dienste überwachen.

Nehmen Sie diese Aktivität in den Vorfall Verwaltungsprozess auf, um die Benutzer, den Helpdesk und ihre Betriebsteams proaktiv zu informieren, um sich auf die Behandlung von Benutzer Eskalationen vorzubereiten.

In den folgenden Abschnitten werden die Tools beschrieben, die Sie nutzen können, um [Dienst Vorfälle](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) zu überwachen, die sich auf den Team Dienst auswirken. In der folgenden Tabelle finden Sie eine Zusammenfassung der Vorteile der einzelnen Tools und deren Verwendung.

| Überwachungs Tool                       | Vorteile                                            | Verwendungszweck                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 Admin Center                     | Verfügbar auf jedem Gerät mit einem unterstützten Browser. | Verwenden Sie diese, wenn Sie keine Echtzeitbenachrichtigungen benötigen.                                          |
| Microsoft 365-oder Office 365-Administrator-App                  | Bietet Push-Benachrichtigungen für Ihr mobiles Gerät.  | Verwenden Sie diese Funktion, wenn Sie über Service-Vorfälle benachrichtigt werden möchten, während Sie unterwegs sind.                  |
| Microsoft System Center               | Integration in Microsoft System Center.           | Verwenden Sie diese Funktion, wenn Sie erweiterte Überwachungsfunktionen und Benachrichtigungsunterstützung benötigen.                       |
| Microsoft 365 oder Office 365 Service Communications-API | Programmgesteuerten Zugriff auf Microsoft 365 oder Office 365-Dienststatus.   | Verwenden Sie diese Option, wenn Sie die Integration mit einem Überwachungstool eines Drittanbieters benötigen oder eine eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, denen die Rolle **globaler Administrator** oder **Dienstadministrator** zugewiesen ist, können den Dienststatus anzeigen.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Überwachung mit dem Microsoft 365 Admin Center

Das [Microsoft 365 Admin Center](https://portal.office.com/) bietet ein [Dienststatus-Dashboard](https://portal.office.com/adminportal/home#/servicehealth) , in dem Sie zusätzlich zu den abhängigen Diensten den aktuellen Status des Teams-Diensts anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachen mit der mobilen App

Die Microsoft 365-oder Office 365-Administrator-App steht unter Apple IOS, Android und Windows zur Verfügung (PC und Mobile). Die APP bietet Dienstadministratoren Informationen zu Dienststatus und bevorstehenden Änderungen. Die App unterstützt Push-Benachrichtigungen, mit denen Sie fast unmittelbar nach der Veröffentlichung einer Empfehlung benachrichtigt werden können. Auf diese Weise können Sie den Status, die Integrität und alle bevorstehenden Änderungen des Diensts auf dem neuesten Stand halten. Die Benachrichtigungsunterstützung macht es zum empfohlenen Überwachungstool für Administratoren. Weitere Informationen finden Sie unter:

[Office 365 admin Mobile-App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Herunterladen der mobilen Office 365 admin-App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Überwachung mit Microsoft System Center

Microsoft System Center ist eine integrierte Verwaltungsplattform, die Ihnen bei der Verwaltung von Rechenzentren, Clientgeräten und Hybrid-Cloud-IT-Umgebungen hilft. Office 365-Administratoren, die System Center verwenden, haben jetzt die Möglichkeit, das Office 365-Management Pack zu importieren, das es Ihnen ermöglicht, alle Dienst Kommunikationen in Operations Manager in System Center anzuzeigen. Mit diesem Tool können Sie auf den Status Ihrer abonnierten Dienste, aktive und aufgelöste Service Vorfälle und Ihre Nachrichten Center Kommunikation (bevorstehende Änderungen) zugreifen. Weitere Informationen finden Sie im folgenden [Blogbeitrag](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Wenn Sie System Center zum Überwachen des Teams-Dienststatus (und abhängiger Dienste) nutzen, können Sie das Management Pack weiter anpassen, um bestimmte Gruppen oder Personen, die identifiziert wurden, um auf Vorfälle zu reagieren, zu informieren oder zu benachrichtigen.
Diese Gruppen können Dienstbesitzer, Helpdesks, Supportgruppen der zweiten Ebene und Dritter Ebene sowie Vorfall Manager in Ihrer Organisation umfassen.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachen für erweiterte Szenarien

Sie können den Dienststatus und bevorstehende Änderungen überwachen, indem Sie die Office 365 Service Communications-API für den Zugriff auf den Office 365-Dienststatus und die programmgesteuerte Änderung nutzen. Verwenden Sie diese API, um ein eigenes Überwachungstool zu erstellen oder Ihre vorhandenen Überwachungstools mit der Office 365-Dienst Kommunikation zu verbinden, wodurch die Überwachung Ihrer Umgebung potenziell vereinfacht wird. Weitere Informationen finden Sie unter [Office 365 für Enterprise-Entwickler](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                               | Häufigkeit   | Team zugewiesen |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen des Dienststatus | Proaktives Überwachen des Microsoft Teams-Dienststatus (und abhängiger Dienste) mithilfe der verfügbaren Tools Zu den abhängigen Diensten gehören: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Echt Zeit |               |
| Vorfall Benachrichtigung  | Informieren Sie interne Stakeholder über Ereignisse, die sich auf den Team-Service auswirken. Interne Stakeholder können Benutzer, Helpdesks und Incident Manager umfassen.                                                                          | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Überprüfen von Office 365-Dienststatus](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Dienststatus und Kontinuität](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von organisatorischen Änderungen

Microsoft Teams ist ein Cloud-basierter Dienst. Damit ist es möglich, neue Features und Funktionen in rasantem Tempo bereitzustellen. Die Bereitstellung kontinuierlicher Innovationen bietet Organisationen einen offensichtlichen Vorteil, doch müssen diese Änderungen in Ihrer Organisation angemessen verwaltet werden, um Benutzer Resistenzen oder Eskalationen an Helpdesks zu vermeiden.

Updates für Teams werden automatisch für Ihre Benutzer bereit gesetzt. Ihre Benutzer verfügen immer über die neuesten Clients und Features, die im Team-Service zur Verfügung stehen. Es ist nicht möglich, den Rollout von Teams-Updates für Ihre Benutzer zu verwalten, daher ist es wichtig, Änderungen durch effektive Kommunikations-, Schulungs-und Adoptionsprogramme zu verwalten. Wenn Ihre Benutzer über die Änderung Bescheid wissen, sich über die Vorteile gebildeten und befugt sind, die neuen Funktionen zu nutzen, &mdash; können Sie sich schneller anpassen und die Änderung begrüßen.

### <a name="monitoring-for-change"></a>Überwachen auf Änderung

Der erste Schritt bei der Änderungsverwaltung ist das Überwachen der für Teams geplanten Änderungen. Die beste Quelle für die Überwachung dieser Änderungen ist die [Office 365-Roadmap](https://products.office.com/business/office-365-roadmap), in der Features aufgelistet sind, die derzeit in der Entwicklung sind, für Kunden bereit stehen oder vollständig gestartet wurden. Sie können mithilfe des bereitgestellten Filters nach Teams-spezifischen Features suchen, oder Sie können die Roadmap für eine weitere Analyse in eine Excel-Datei herunterladen. Für jedes Feature gibt die Roadmap eine kurze Beschreibung zusammen mit dem voraussichtlichen Veröffentlichungsdatum an.

Im [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)finden Sie Informationen zu bewährten Methoden, Trends und Neuigkeiten zu Produktupdates für Teams. Erwarten Sie, dass Sie wichtige Funktionsupdates für Teams finden, die hier angekündigt werden. Sie können den Blog auch über einen RSS-Feed abonnieren. Sie können [den RSS-Feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) dann direkt in einen Teams-Kanal einfügen, damit alle wichtigen Nachrichten direkt innerhalb von Teams bereitgestellt werden.

Alle freigegebenen Features sind in den Versionshinweisen [für Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)dokumentiert.
Hier finden Sie eine Liste der Funktionen, die für Desktop-, Web-und mobile Geräte freigegeben wurden. Die gleichen Anmerkungen zu dieser Version finden Sie auch auf der Registerkarte **Neuerungen** in der [Hilfe](get-help-in-microsoft-teams.md).

Machen Sie sich mit den verfügbaren Ressourcen vertraut, und stellen Sie sicher, dass Sie entsprechende Besitzer zuweisen, um Änderungen zu überwachen.

### <a name="planning-for-change"></a>Planen von Änderungen

Nachdem Sie sich nun mit den bevorstehenden Änderungen des Teams-Diensts vertraut machen, besteht der nächste Schritt darin, entsprechend vorzubereiten und zu planen. Bewerten Sie die einzelnen Änderungen, um festzustellen, welche Änderungen die Kommunikation mit Benutzern, Sensibilisierungskampagnen, Schulungen für Support Teams oder Benutzer sowie Kampagnen zur Evaluierung und Annahme von Funktionen erfordern. Dies ist die primäre Rolle eines Change Management-Teams in Ihrer Organisation. Nachfolgend finden Sie eine Sammlung von Beispieltabellen, die Ihnen bei der Planung von Änderungen behilflich sein können.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloud-Aufzeichnung (Veröffentlichungsdatum: Januar 2018)

**Allgemeiner Titel**

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Rechtliche Überprüfung   | Abgeschlossen     | Dieses Feature ist eine Voraussetzung für das Onboarding des Schulungsteams. | Projektteam  |

**Technisches Änderungsmanagement**

|       Ändern der Bereitschaft       | Status |                      Notizen/nächste Schritte                      |    Besitzer     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Änderungen erforderlich      |  Ja   | Der Administrator muss die Aufzeichnung nur für erkannte Benutzer aktivieren. | Support-Team |
| Technische Bereitschaft abgeschlossen |  Ja   |                                                            | Support-Team |
|                              |        |                                                            |              |

**Benutzer Änderungsverwaltung** 

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Auswirkungen des Benutzers                  | Niedrig                  |                                                                 |                        |
| Benutzer Bereitschaft erforderlich      | Ja                  |                                                                 |                        |
| Kommunikation bereit         | Nein                   | E-Mail-Kommunikation wurde verfasst – ausstehend Überprüfung.            | Kommunikations Team    |
| Schulung bereit               | Ja                  | Die Schulung nutzt vorhandene Microsoft-Video.                | Schulungs Team          |

**Status Spur**

| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Freigabestatus               | in Bearbeitung          | Ausstehende Überprüfung durch den Executive-Sponsor.               | Change Management-Team |
| Freigabe Abmeldung             |                      |                                                                 |                        |
| Veröffentlichungsdatum                 |                      |                                                                 |                        |

Weitere Informationen zum Planen der Änderungsverwaltung für Teams finden Sie unter [Erstellen einer Änderungs Verwaltungsstrategie für Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                                | Häufigkeit   | Team zugewiesen |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Überwachen auf Änderung     | Überwachen Sie die bevorstehenden Änderungen am Microsoft Teams-Dienst.                                                                                                                                                                   | Täglich     |               |
| Planen von Änderungen    | Evaluieren und planen Sie neue Features und Funktionen, einschließlich Kommunikationspläne, Sensibilisierungskampagnen und Schulung.                                                                                                     | Nach Bedarf |               |
| Benutzer Bereitschaft             | Führen Sie gezielte Kommunikations-, Sensibilisierungs-oder Schulungskampagnen durch, um sicherzustellen, dass Benutzer bereit für die bevorstehende Änderung sind.                                                                                                        | Nach Bedarf |               |
| Bereitschaft des Support Teams | Führen Sie gezielte Kommunikations-, Sensibilisierungs-oder Schulungskampagnen durch, um sicherzustellen, dass das Support Team bereit ist. Zu den Support Teams gehören das Team "weißer Handschuh", Helpdesks, Support für Stufe 2 oder Tier 3, externe Partner usw. | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten der Verwendung von Teams

Nach Beginn des ersten Pilotprojekts ist es wichtig, eine reguläre Kadenz für die Messung der tatsächlichen Team Auslastung festzulegen. Auf diese Weise kann Ihre Organisation Einblicke in die Übereinstimmung der tatsächlichen Nutzung mit der in der Envisions Phase prognostizierten Verwendung gewinnen. Dieser Abschnitt konzentriert sich zwar auf die Verwendung von Teams, sollte aber Teil einer breiteren Bemühung sein, die Verwendung von Office 365 insgesamt zu messen und zu bewerten.

Die häufige Überprüfung der Verwendung zu Beginn der Bereitstellung bietet Ihnen folgende Möglichkeiten:

-   Überprüfen Sie, ob Benutzer Teams verwenden.

-   Ermitteln Sie potenzielle Akzeptanz Herausforderungen, bevor Sie kritische Probleme in der gesamten Organisation verursachen.

-   Ermitteln Sie, ob Diskrepanzen zwischen den Anforderungen der Envisions Phase und der tatsächlichen Verwendung bestehen.

Wenn die Verwendung nicht das ist, was Sie erwarten, kann dies auf ein Bereitstellungsproblem zurückzuführen sein, oder der Adoptions Plan wird nicht ordnungsgemäß oder ein anderes Problem ausgeführt. Je nach dem tatsächlichen Grund für die niedrige Auslastung muss der Dienstadministrator mit den zugehörigen Teams zusammenarbeiten, um die Nutzung von Hindernissen zu entfernen.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Messen der Verwendung mit dem Microsoft 365 Admin Center

Verwendungsdaten aus Teams sind im Dashboard für die Berichterstellung verfügbar. Die Nutzungsdaten für Teams sind in drei verschiedenen Berichten zu finden. Der erste Bericht bietet eine produktübergreifende Ansicht, wie Benutzer mit den verschiedenen Diensten in Office 365 kommunizieren und zusammenarbeiten. Diesen Bericht finden Sie hier: [Office 365-Bericht "aktive Benutzer](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D) "

Die anderen beiden Berichte sind Teams-spezifisch, und Sie bieten weitere Details zur Verwendung von Teams aus Benutzer-und Geräte Perspektive. Beide Berichte finden Sie hier:

[Microsoft Teams – Gerätenutzungsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams – Benutzeraktivitätsbericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Auf die Verwendungsberichte im Admin Center kann von Personen zugegriffen werden, denen eine **globale Administrator** Rolle zugewiesen wurde, oder auf eine produktspezifische Administratorrolle (**Exchange-Administrator**, **Skype for Business-Administrator**, **SharePoint-Administrator**).

Darüber hinaus steht die Rolle " **berichtsleser** " für Benutzer zur Verfügung, die Zugriff auf die Berichte benötigen, jedoch keine Aufgaben ausführen, für die Berechtigungen auf Administratorebene erforderlich sind. Sie weisen diese Rolle zu, um jedem, der ein Stakeholder ist, Verwendungsberichte zur Verfügung zu stellen, um die Einführung zu überwachen und zu steuern. Weitere Informationen zu den verschiedenen verfügbaren Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Bewerten der Verwendung

Nachdem Sie die Verwendung des Berichterstattungs-Dashboards verwendet haben, ist es wichtig, die gemessene Verwendung mit allen wichtigen Erfolgsindikatoren (KSIs) zu vergleichen, die Sie während der Envisions Phase des Projekts definiert haben. Sie können eine ksi definieren, die möglicherweise als aktive Verwendung definiert ist, oder eine, die indirekt mit aktiver Verwendung verknüpft ist.

Es ist wichtig, etwaige Abweichungen zwischen der tatsächlichen und der geplanten Verwendung zu erkennen, bevor der Rollout auf zusätzliche Websites oder Benutzer fortgesetzt wird. Wahrscheinlich identifizieren Sie organisatorisches Lernen als Teil dieser Aktivität, die Sie nutzen können, um sicherzustellen, dass der nächste Batch von Websites oder Benutzern nicht dieselben Probleme aufweist.

Ermitteln Sie zunächst, ob es sich um ein Adoptions-oder technisches Problem handelt. Untersuchen Sie zunächst die folgenden Elemente, um festzustellen, wo das Problem liegt.

1.  Überprüfen Sie die Qualität, indem Sie eine [Bewertung der Qualität der Erfahrung](#quality-of-experience-review-guide)durchführen.

2.  Arbeiten Sie mit dem Helpdesk-Team zusammen, um zu überprüfen, ob es keine Trend technischen Probleme gibt, die verhindern, dass Benutzer auf den Dienst zugreifen oder ihn verwenden. Wenn Problem Trends vorhanden sind, verwenden Sie den Abschnitt [Endpunkt Problembehandlung](#endpoint-troubleshooting) weiter unten in diesem Artikel, um das Problem zu beheben, bevor Sie den Support ansprechen.

3.  Arbeiten Sie mit dem Schulungs-und Adoptions Team zusammen, um direktes Feedback von Benutzern zu sammeln (Weitere Informationen finden Sie unter [bewerten der Benutzer Sentiment](#assess-user-sentiment) weiter unten in diesem Artikel), und überprüfen Sie die Effektivität von Sensibilisierungs-und Adoptions Aktivitäten.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität                         | Beschreibung                                                                                                                      | Häufigkeit   | Team zugewiesen |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Messen der Verwendung (Aktivierungsphase) | Messen und bewerten Sie die Verwendung von Teams, während die Websites während der Aktivierungsphase weiterhin an Bord sind. Behebung von Nutzungsproblemen nach Bedarf. | Wöchentlich    |               |
| Messen der Verwendung                    | Messen und bewerten Sie die Verwendung von Teams in der Antriebs Wert Phase (nach Abschluss der Bereitstellung). Behebung von Nutzungsproblemen nach Bedarf. | Biweekly  |               |
| (Antriebs Wert Phase)              |                                                                                                                                  |           |               |
| Update Annahme Plan             | Aktualisieren Sie Ihren Adoptions Plan basierend darauf, wie die gemessene Nutzung mit ihren Planungszielen verglichen wird.                                         | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Informationen zum Microsoft 365 Admin Center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Beurteilen der Benutzer Stimmung

Das Verständnis der Benutzer Empfindung kann als ein wichtiger Indikator für den Erfolg Ihrer Teams-Bereitstellung fungieren. Benutzer Feedback kann Änderungen in Ihrer Organisation vorantreiben. Dies kann Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder der Art und Weise beinhalten, wie Sie Ihre Benutzer unterstützen.

Es ist wichtig, dass Sie frühzeitig Feedback erhalten und die Einschätzung der Benutzer Gefühle während des gesamten Lebenszyklus des Projekts und darüber hinaus fortsetzen. Verwenden Sie die folgenden Anleitungen, um das Intervall zu ermitteln, in dem Ihre Organisation Feedback sucht:

-   **Anfang des Projekts**: Wenn Sie die Einschätzung des Nutzers zu Beginn des Projekts bewerten, können Sie sich einen frühen Überblick darüber verschaffen, wie sich Ihre Benutzer über die Erfahrungen ihrer Teams fühlen.

-   **Nach wichtigen Meilensteinen**: durch das Sammeln von Feedback während des gesamten Projektlebenszyklus können Sie die Benutzer Stimmung kontinuierlich beurteilen und Änderungen nach Bedarf vornehmen. Dies ist besonders nach wichtigen Meilensteinen nützlich.

-   **Projektfazit**: Wenn Sie die Einschätzung des Benutzers am Ende eines Projekts bewerten, erfahren Sie, wie gut Sie gearbeitet haben und wo noch Arbeit zu erledigen ist, und Sie können die Ergebnisse mit der vorherigen Umfrage vergleichen.

-   Fort **laufend**: Messen Sie die Benutzer Stimmung weiterhin auf unbestimmte Zeit. Änderungen in der Benutzer Einschätzung können auf Änderungen in der Umgebung Ihrer Organisation oder auf Änderungen des Teams-Diensts zurückzuführen sein. Indem Sie die Benutzer Stimmung in regelmäßigen Abständen beurteilen, können Sie verstehen, wie gut Ihre Dienst Verwaltungsteams funktionieren und wie Ihre Organisation auf Änderungen im Team Dienst reagiert.

Benutzer Gefühle können über viele verschiedene Methoden bewertet werden. Diese können e-Mail-Umfragen, persönliche oder telefonische Interviews oder einfach nur einen Feedback Kanal in Teams oder "jammern" umfassen. Weitere Informationen finden Sie unter [bewährte Methoden für Benutzer Feedback Methoden in Microsoft Teams](best-practices-feedback.md).

Sie können auch einen industrieweite-Ansatz verwenden, um die Benutzer Sentiment mit dem Namen net Promotor Score (NPS) zu bewerten, der im folgenden Abschnitt beschrieben wird.

### <a name="nps"></a>NPS 

Net Promoter Score (NPS) ist eine industrieweite-Kunden Bindungs Metrik und ein guter Ansatz zur Beurteilung der Benutzer Empfindung. NPS kann berechnet werden, indem zwei Fragen gestellt werden: "wie wahrscheinlich ist es, dass Sie einem Kollegen Teams empfehlen?", gefolgt von der frei Hand Frage "Warum?"

Bei NPS handelt es sich um einen Index, der von-100 bis 100 reicht und die Bereitschaft eines Kunden zur Empfehlung eines Produkts oder einer Dienstleistung des Unternehmens misst. NPS basiert auf einer anonymen Umfrage, die Benutzern per e-Mail oder auf anderen elektronischen wegen zugestellt wird. NPS misst die Loyalität zwischen einem Anbieter und einem Verbraucher. Es besteht aus nur einer Frage, die die Nutzer auffordert, ihre Erfahrungen von 1 bis 10 zu veranschlagen, mit der Möglichkeit, zusätzliche Kommentare anzubieten. Benutzer werden dann basierend auf den folgenden Bewertungen klassifiziert:

-   9 oder 10 sind Promoter: Treue Enthusiasten, die Ihren Service fördern und andere anheizen werden.

-   7 oder 8 sind passiv: zufrieden, aber unenthusiastisch, anfällig für einen anderen Dienst oder ein Angebot.

-   Von 1 bis 6 sind Kritiker: unzufriedene Kunden, die Ihren Service beschädigen und das Wachstum behindern können.

![Ein Diagramm, das die NPS-Skalierung veranschaulicht](media/operate-my-service-image2.png "Dieses Diagramm veranschaulicht die NPS-Skalierung. Es zeigt, dass die Rankings von 0 bis 6 Kritiker sind, 7 bis 8 sind passiv, und 9 bis 10 sind Promoter.")

Obwohl die NPS-Basisnummer hilfreich ist, erhalten Sie den größten Nutzen aus der Analyse von Benutzerkommentaren. Sie werden Ihnen helfen zu verstehen, warum der Benutzer Teams anderen Personen empfehlen würde (oder nicht). Diese Kommentare können wertvolle Rückmeldungen liefern, damit die Projekt-oder Service Management Teams die Anpassungen verstehen, die erforderlich sind, um einen Qualitätsdienst bereitzustellen.

Wenn Sie Ihrer Organisation NPS-Umfragen zur Verfügung stellen möchten, können Sie Ihr bevorzugtes Online Umfrage Tool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/Bedarfs Aufgaben

| Aktivität              | Beschreibung                                                                                                                                                                         | Häufigkeit   | Team zugewiesen |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Beurteilen der Benutzer Stimmung | Erfassen und bewerten Sie die Benutzer Stimmung mithilfe von Umfragen oder Interviews oder über einen Feedback Kanal in Teams oder "jammern".                                                                 | Nach Bedarf |               |
| Aktualisieren von Adoptions Plänen | Laufwerksänderungen in Ihrer Organisation auf der Grundlage von Benutzer Feedback Dazu gehören Änderungen an Ihren Kommunikationsplänen, Schulungsprogrammen oder die Art und Weise, wie Sie Ihre Benutzer unterstützen können. | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[Netto-Promoter-Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden von "jammern" zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzer Feedback](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Viele grundlegende Planungselemente gehen in die Optimierung, die richtige Größenanpassung und die Remediation Ihrer Netzwerkinfrastruktur ein, um einen qualitativ hochwertigen, effizienten Pfad zum Microsoft Teams-Dienst zu gewährleisten. Die Planungsaufgaben und-Anforderungen werden in unserer [Netzwerk Readiness](3-envision-evaluate-my-environment.md#network-readiness) -Anleitung behandelt. Netzwerke entwickeln sich im Laufe der Zeit aufgrund von Upgrades, Erweiterungen oder anderen geschäftlichen Anforderungen oft weiter. Es ist wichtig, dass Sie Ihre Anforderungen für Teams in Ihren Netzwerk Planungsaktivitäten berücksichtigen.

Obwohl die Netzwerkplanung ein kritischer Aspekt einer Teams-Bereitstellung ist, ist es gleichermaßen wichtig, sicherzustellen, dass das Netzwerk weiterhin fehlerfrei bleibt und auf der Grundlage geänderter geschäftlicher oder technischer Anforderungen aktuell bleibt.

Um die Integrität Ihres Netzwerks zu gewährleisten, müssen in regelmäßigen Abständen eine Reihe von Vorgangs Aktivitäten ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität                                                       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                 | Häufigkeit                | Team zugewiesen |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Überwachen von Office 365 IPS und URLs                                | Überwachen Sie alle Änderungen an den [Office 365-URLs und IP-Adressbereichen](https://aka.ms/o365ips) mit dem bereitgestellten [RSS-Feed](https://go.microsoft.com/fwlink/p/?linkid=236301) , und initiieren Sie eine Änderungsanforderung für entsprechende Netzwerkgruppen.                                                                                                                                | Täglich                  |               |
| Aktualisieren des Netzwerks auf Grundlage von Änderungen an Office 365 IPS und URLs | Aktualisieren Sie die anwendbaren Netzwerkkomponenten (Firewalls, Proxy Server, VPNs, clientseitige Firewalls usw.), um Änderungen an den [Office 365-URLs und IP-Adressbereichen](https://aka.ms/o365ips)wiederzugeben.                                                                                                                                                              | Nach Bedarf              |               |
| Bereitstellen von Gebäudedaten                                          | Bereitstellen von aktualisierten Subnetz-Informationen für den Quality Champion (oder relevante Stakeholder), um sicherzustellen, dass die [Gebäude Definitionen in CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem neuesten Stand gehalten werden. | Nach Bedarf              |               |
| Implementieren von Änderungen                                               | Implementieren Sie Änderungen im Netzwerk, um die geschäftlichen und technischen Anforderungen des Teams zu ändern. Zu den Netzwerkelementen gehören:<ul><li>Firewalls</li><li>VPNs</li><li>Kabelgebundene und WLAN-Netzwerke</li><li>Internet Konnektivität und Express Route</li><li>DNS</li></ul>     | Nach Bedarf              |               |
| Netzwerküberwachung und-Berichterstellung                               | Überwachen Sie das Ende des Netzwerks auf Verfügbarkeit, Auslastung und Kapazitäts Trends, indem Sie die vorhandenen Netzwerkverwaltungstools und Berichtsfunktionen von Drittanbietern verwenden, die von ihren Netzwerkanbietern zur Verfügung stehen. Verwenden Sie Trenddaten für die Netzwerkkapazitätsplanung.                                                                                                            | Täglich, wöchentlich, monatlich |               |
| Kapazitätsplanung                                              | Arbeiten Sie mit den Team Dienstanbietern zusammen, um sich verändernde geschäftliche und technische Anforderungen zu verstehen, die zusätzliche Kapazitätsänderungen antreiben könnten.                                | Nach Bedarf              |               |
| Netzwerkproblembehandlung und-Behebung                        | Unterstützen Sie die Teams-Helpdesks, Dienstbesitzer und wichtigen Teilnehmer bei der Problembehandlung und Beheben von Problemen im Zusammenhang mit der Konnektivität, Zuverlässigkeit oder Qualität von Teams. Zu den Netzwerkelementen gehören:<ul><li>Firewalls</li><li>VPNs</li><li>Kabelgebundene und WLAN-Netzwerke</li><li>Internet Konnektivität und Express Route</li><li>DNS</li></ul>    | Nach Bedarf              |               |
| Testen von Disaster Recovery und Höchstverfügbarkeit                | Führen Sie regelmäßige hoch Verfügbarkeits-und Disaster Recovery-Tests für die Netzwerkinfrastruktur durch, um sicherzustellen, dass Sie die angegebenen Service Level Objectives (SLOs) oder Service Level Agreements (SLAs) für den Teams-Service erfüllt.                                                                                                                                                  | Monatlich                |               |


### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365ips)

[Erstellen eines Datenschemas](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und sicherstellen von Qualität 

Alle Organisationen benötigen eine Gruppe oder eine Person, um für Qualität verantwortlich zu sein. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Die Rolle "Qualitäts Champion" wird einer Person oder Gruppe zugewiesen, die leidenschaftlich über die Benutzererfahrung verfügt.
Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität des Unternehmens kann es sich um eine Person oder Gruppe mit einer Leidenschaft für die Gewährleistung einer qualitativ hochwertigen Benutzererfahrung handeln.

Der Quality Champion nutzt die vorhandenen Tools und dokumentierten Prozesse, wie beispielsweise das Anruf Qualitäts-Dashboard (CQD) und den Leitfaden zur Überprüfung der Qualität von Erfahrungen, um die Benutzererfahrung zu überwachen, qualitätstrends zu erkennen und bei Bedarf eine Problembehebung durchführen zu können.
Der Quality Champion sollte mit den jeweiligen Teams zusammenarbeiten, um die Behebungsaktionen voranzutreiben, und einem Lenkungsausschuss über den Fortschritt und alle offenen Probleme Bericht erstatten.

Der [Leitfaden zur Überprüfung der Qualität](https://aka.ms/qerguide) der Benutzerfreundlichkeit umfasst Aktivitäten, die in wichtigen Bereichen, die die Verbesserungen der Benutzeroberfläche am stärksten beeinflussen, die Behebungs Anleitung bewerten und bereitstellen. Die im Leitfaden zur Überprüfung der Qualität der Überprüfung bereitgestellten Anleitungen konzentrieren sich auf die Verwendung von CQD Online als primäres Tool für die Berichterstellung und Untersuchung der einzelnen Bereiche, wobei der Schwerpunkt auf Audio liegt, um die Akzeptanz und Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Wir empfehlen Ihnen dringend, den Qualitätschampion frühzeitig zu benennen. Nachdem Sie nominiert wurden, sollten Sie sich mit dem Inhalt des Überprüfungs Leitfadens für die Qualität der Erfahrung und zugehörigen Schulungsmaterialien vertraut machen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität                               | Beschreibung                                                                                                                                                                                                                                                                                                 | Häufigkeit                             | Team zugewiesen |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominierung und Schulung von Quality Champion (s) | Einen Qualitätschampion benennen und Schulen.                                                                                                                                                                                                                                                                   | Nach Bedarf                           |               |
| Durchführen von Bewertungen der Quality of Experience (QERs)     | Führen Sie eine QER durch, um Trends in Bezug auf Qualität und Zuverlässigkeit zu erkennen, anhand definierter Ziele zu überprüfen und den wichtigsten Stakeholdern in der Organisation zu melden.                                                                                                                            | Monatlich (wöchentlich während der Bereitstellung) |               |
| Behebung von Laufwerken                      | Koordinieren Sie die Behebungs Bemühungen in der gesamten Organisation auf der Grundlage der QER-Bewertungen und-Ergebnisse.                                                                                                                                                                                                           | Nach Bedarf                           |               |
| Aktualisieren von Gebäudedaten in CQD            | Aktualisieren oder Hinzufügen neuer Gebäude Definitionen in CQD, wenn Änderungen am Netzwerk vorgenommen werden (siehe [Hochladen von Gebäudeinformationen](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Nach Bedarf                           |               |
| Füllen der Rolle "Qualitäts Champion"      | End-to-End-Verantwortung für die Qualität in der Organisation Dazu gehören:<ul><li>Stellen Sie sicher, dass die QER regelmäßig durchgeführt wird.</li><li>Melden Sie sich an wichtige Stakeholder zum Qualitätsstatus.</li><li>Stellen Sie sicher, dass die Definitionen für Gebäudedaten auf dem neuesten Stand sind.</li><li>Koordinieren Sie die Behebungs Bemühungen in der gesamten Organisation, um sicherzustellen, dass die Benutzer eine qualitativ hochwertige Erfahrung mit Teams haben.</li></ul>          | Täglich                               |               |



### <a name="references"></a>Referenzen 

[Hochladen von Mandantendaten Informationen](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)

[Handbuch für die Überprüfung der QoE (Quality of Experience)](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft Teams-Endpunkte können als alle PC-, Mac-, Tablet-oder mobilen Geräte (oder ein anderes Gerät) definiert werden, auf denen der Client für Teams ausgeführt wird. Der Term- *Endpunkt* umfasst nicht nur das Gerät selbst, sondern wie ein Benutzer eine Verbindung mit dem Gerät herstellt, beispielsweise mithilfe des integrierten Mikrofons oder Lautsprechers des Geräts, Ohrstöpsel oder eines optimierten Headsets. Nach der Bereitstellung dürfen Endpunkte nicht vergessen werden. Die Endpunkte der Teams erfordern ständige Wartung und Wartung. In den folgenden Abschnitten werden bestimmte Bereiche beschrieben, auf die Sie sich konzentrieren sollten.

### <a name="endpoint-requirements"></a>Endpunkt Anforderungen

Einer der Hauptvorteile von Teams besteht darin, dass der Client automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die mobilen Teams-apps werden über ihre jeweiligen App-Stores aktuell gehalten.

Der Client für Teams hat Mindestanforderungen hinsichtlich der zugrunde liegenden Softwareplattform. Diese Anforderungen können sich im Laufe der Zeit ändern, und daher ist es wichtig, dass Sie Sie auf Änderungen überwachen. Der Client für Teams verfügt beispielsweise über eine minimale IOS-Version. Wenn der Client einen Internet Browser verwendet, muss der Browser ebenfalls aktuell gehalten werden. Eine Liste der unterstützten Plattformen finden [Sie unter Abrufen von Clients für Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Client seitige Firewalls können die Anrufqualität beeinträchtigen und sogar verhindern, dass ein Anruf eingerichtet wird. Nachdem die entsprechenden Ausschlüsse für die Client Firewall konfiguriert wurden, müssen Sie basierend auf den Informationen in [Office 365-URLs und IP-Adressbereichen](https://aka.ms/o365ips)auf dem neuesten Stand gehalten werden. Ihr Drittanbieter erhält spezifische Anleitungen für die Aktualisierung der Ausschlüsse.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

WLAN-Treiber sind möglicherweise problematisch. Ein Beispiel: ein Treiber kann sehr aggressive Roaming-Verhaltensweisen zwischen Zugriffspunkten aufweisen, die unnötige Zugriffspunktwechsel auslösen können, was zu schlechter Anrufqualität führt. Ein schlechter leistungsfähiger WLAN-Treiber wird möglicherweise durch eine Überprüfung der Qualität der Erfahrung ermittelt (Weitere Einzelheiten finden Sie im [Leitfaden zur Überprüfung der Qualität](https://aka.ms/qerguide) ). Es ist wichtig, einen qualitätsorientierten Prozess zu implementieren, der neue Wi-Fi-Treiber überwacht und sicherstellt, dass Sie getestet werden, bevor Sie für die allgemeine Benutzer Bevölkerung bereitgestellt werden.

### <a name="endpoint-management"></a>Endpunkt Verwaltung

Ein Katalog mit unterstützten Endpunkten und Schnittstellengeräten (wie Headsets) sollte verfügbar und gewartet werden. Dieser Katalog enthält eine Liste der genehmigten Geräte, die als Teil der Phase enVision und Onboard ausgewählt und überprüft wurden. In der Regel werden bestimmte Geräte für jeden Persona-Typ in Ihrer Organisation ausgewählt, um die Anforderungen der Attribute dieser Person zu erfüllen. Alle Endpunkte verfügen über einen Lebenszyklus, und Sie müssen die Vertragspartner Verträge, Gewährleistungs-, Ersatz-, Verteilungs-und Reparatur Richtlinien verwalten, die diesen Geräten zugeordnet sind.

### <a name="endpoint-troubleshooting"></a>Problembehandlung für Endpunkt

Auch wenn Sie die vorherigen Anleitungen befolgt haben, können die Benutzer in Ihrer Organisation weiterhin Probleme mit Teams eingehen. Obwohl das Problem möglicherweise nicht mit dem Endpunkt selbst verbunden ist, werden die Symptome des Problems in der Regel über den Client für den Benutzer angezeigt. Die folgenden Anleitungen sollen allgemeine Schritte zur Behebung des Problems bereitstellen. Es handelt sich nicht um eine umfassende Anleitung zur Fehlerbehebung. Die Schritte werden in einer bestimmten Reihenfolge bereitgestellt, müssen aber nicht explizit befolgt werden und sind je nach Art des Problems möglicherweise nicht anwendbar.

1.  Über **prüfen des Dienststatus:** Das von einem Benutzer auftretende Problem kann sich auf ein Ereignis beziehen, das sich negativ auf den Teams-Dienst oder dessen abhängige Dienste auswirkt. Als ersten Schritt empfehlen wir, dass Sie bestätigen, dass es keine aktiven Dienst Probleme gibt. Informieren [Sie sich, wie Sie den Office 365-Dienststatus überprüfen können](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Denken Sie daran, den Status abhängiger Dienste zu überprüfen (beispielsweise Exchange, SharePoint, OneDrive for Business). Die Überwachung des Dienststatus wird im vorherigen Abschnitt, [Überwachen des Dienststatus](#monitor-service-health), ausführlicher erläutert.

2.  Über **Prüfen der Clientkonnektivität:** Verbindungsprobleme führen zu Funktions-oder Anmeldeproblemen in Teams. Wir empfehlen (insbesondere für neue Websites oder Standorte), dass Sie die Verbindung mit dem Dienst überprüfen. Stellen Sie sicher, dass die folgenden [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) für jede Website befolgt werden. Sie können das Tool für die [Microsoft-Netzwerkbewertung](https://www.microsoft.com/download/details.aspx?id=53885) nutzen, um einen Verbindungstest durchzuführen, um zu überprüfen, ob die Medienanschlüsse für Cloud-Sprachfunktionen ordnungsgemäß geöffnet wurden. Detaillierte Anweisungen zum Ausführen der Verbindungstests finden Sie im [Netzwerk Readiness](3-envision-evaluate-my-environment.md#network-readiness) -Leitfaden.

3.  **Überprüfen Sie die Liste bekannte Probleme:** Konsultieren Sie die [Problembehandlung für Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) , um festzustellen, ob der Benutzer von einem dieser Probleme negativ betroffen ist. Befolgen Sie die Problemumgehung (sofern vorhanden), um das Problem zu beheben.

4.  **Besuchen Sie die Microsoft Teams-Community:** Die [Microsoft Teams-Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) bietet dedizierte Räume für Teams. Die Teams-Community bietet eine Diskussionsliste, Blogbeiträge und Ankündigungen, die sich auf Teams konzentrieren. Sie können eine Frage Posten oder frühere Diskussionen nach Lösungen für Ihr Problem durchsuchen.

5.  **Wenden Sie sich an den Microsoft-Support:** Sie können sich an den Microsoft-Support wenden, um Probleme mit Teams Online oder telefonisch zu beheben. Informationen finden Sie unter [kontaktieren des Supports für Business-Produkte](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
    Für Premier-Kunden können Supportanfragen initiiert werden, indem Sie die Anleitungen unter [Kontakt Support für Microsoft Teams (Premier-Kunden)](https://support.microsoft.com/premier/contacts)befolgen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität                 | Beschreibung                                                                                                                                                                                                                                                                                                                                                                     | Häufigkeit   | Team zugewiesen |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Endpunkt Anforderungen    | Stellen Sie sicher, dass der Endpunkt des Teams weiterhin alle Softwareanforderungen für Teams erfüllt, die unter [Abrufen von Clients für Microsoft Teams](get-clients.md)aufgeführt sind.                                                                                                                                                                                       | Monatlich   |               |
| Endpunktfirewalls       | Verwalten Sie die entsprechenden Ausnahmen für die Endpunkt Firewall basierend auf den Informationen in [Office 365-URLs und IP-Adressbereichen](https://aka.ms/o365ips). Ihr Drittanbieter erhält spezifische Anleitungen für die Beibehaltung der Ausschlüsse. Abonnieren Sie den [RSS-Feed](https://support.office.com/o365ip/rss) , um automatisch über Änderungen benachrichtigt zu werden. | Nach Bedarf |               |
| WLAN-Treiber            | Testen und aktualisieren Sie die WLAN-Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe von CQD ([Quality of Experience Review Guide](https://aka.ms/qerguide)).                                                                                                                                                                                                                                                                   | Nach Bedarf |               |
| Endpunkt Verwaltung      | Verwalten Sie den Katalog unterstützter Endpunkte und Schnittstellengeräte (wie Headsets). Verwalten von Lieferantenverträgen, Gewährleistungs-, Verteilungs-, Ersatz-und Reparatur Richtlinien.                                                                                                                                                                                                        | Monatlich   |               |
| Problembehandlung für Endpunkt | Die Problembehandlung kann die Überprüfung der Konnektivität, das Konsultieren der Liste der bekannten Probleme, die Erfassung von Protokollen, die Analyse und die Eskalation des Microsoft-Supports oder von Drittanbietern umfassen.                                                                                                                                                                                               | Nach Bedarf |               |

### <a name="references"></a>Referenzen 

[URLs und IP-Adressbereiche für Office 365](https://aka.ms/o365ips)

[Clients für Microsoft Teams abrufen](get-clients.md)

[Microsoft Teams-Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Überprüfen der Dienstintegrität für Microsoft Teams](service-health.md)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Kontaktieren des Premier-Supports](https://support.microsoft.com/premier/contacts)

[Problembehandlung für Teams – Video](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Microsoft Teams-Dienst bereitgestellt wurde, müssen Sie mehrere Aktivitäten im Zusammenhang mit der Verwaltung durchführen. Die Aktivitäten sind von der Verwaltung des Diensts und einzelnen Benutzern bis hin zur Kapazitätsplanung und Bereitstellung von Lizenzen und Telefonnummern. In den folgenden Abschnitten werden einige dieser allgemeinen Verwaltungsaufgaben behandelt.

### <a name="service-administration"></a>Dienstverwaltung

Der Team Dienst verfügt über mehrere Einstellungen, die mandantenübergreifend konfiguriert werden können.
Änderungen an den Mandanten Einstellungen wirken sich auf alle Benutzer aus, die für Teams aktiviert wurden. Eine detaillierte Liste dieser Einstellungen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md).

### <a name="user-administration"></a>Benutzerverwaltung

Zur Unterstützung von Benutzern erfordert eine Organisation möglicherweise eine beliebige Anzahl verwandter Aufgaben – die spezifischen Aufgaben variieren von einer Organisation zur nächsten. Letztendlich müssen diese Aufgaben von einem Support Team verwaltet werden, dem diese operativen Aufgaben zugewiesen wurden. Die folgenden Aufgaben sind häufig erforderlich, um Benutzer in Teams zu unterstützen.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Allgemeine Aufgaben für das Telefon System

[[Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user).](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)

[Zuweisen oder Ändern einer Notfalladresse für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Allgemeine Aufgaben für Audiokonferenzen

[Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Lizenzverwaltung

Wenn Ihre Organisation wächst oder Verträge aufnimmt, ist es wichtig, dass Sie die Lizenzierung für aktuelle und zukünftige Anforderungen planen. Neben der Lizenzierung für Cloud-Sprachfunktionen ([Telefon System](here-s-what-you-get-with-phone-system.md) und [Audiokonferenz](https://products.office.com/skype-for-business/audio-conferencing)) gibt es eine Basis Teams-Lizenz.

Für Teams benötigen Lizenzen für Telefonsysteme zugeordnete [Anrufpläne](calling-plan-landing-page.md) . Mit der Anruf Plan Lizenzierung können Sie inländische und/oder internationale Telefonanrufe tätigen und empfangen. Diese Pläne sind Verwendungs basiert und mit Minuten Pools verbunden. Durch die Bereitstellung von [Kommunikationsguthaben](what-are-communications-credits.md) wird sichergestellt, dass Sie nie außer Dienst stehen.

Audiokonferenzen ermöglichen gebührenpflichtige Einwahlkonferenzen und Dienste für inländische Einwahlkonferenzen. Gebührenfreie Einwahlkonferenzen oder nicht-inländische Wähl Szenarien können dazu führen, dass zusätzliche Gebühren anfallen, für die [Kommunikationsguthaben](what-are-communications-credits.md) erforderlich sind.

Kommunikations Kredite können sowohl Anrufplan-als auch Audiokonferenz-Lizenzen ergänzen. Sowohl Lizenzen für den Anrufplan als auch Kommunikations Kredite sind Nutzungs basiert und müssen daher entsprechend überwacht und bereitgestellt werden.

Sie können den [Bericht zur PSTN-Nutzung](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) nutzen, um die Nutzung von Gesprächsminuten und Kommunikationsguthaben zu überwachen. Basierend auf den Ergebnissen dieser Aktivität können Sie Ihre Lizenzierung entsprechend anpassen. In Kürze werden wir einen PSTN- [Minuten Pool](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) Bericht anbieten, um diese Aufgabe effektiver zu unterstützen.

### <a name="telephone-number-management"></a>Verwaltung von Telefonnummern

Es gibt zwei Methoden zum Abrufen von Zahlen in Teams: Sie können Telefonnummern von einem anderen Anbieter portieren, oder Sie können die Nummern direkt aus dem Microsoft-Nummern Inventar bereitstellen. Beide Methoden werden unter [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md)beschrieben.

Die Anzahl der Telefonnummern, die Sie aus dem Microsoft-Nummern Inventar bereitstellen können, ist begrenzt. Die Grenzwertewerden durch eine Reihe von Faktoren bestimmt, die detailliert sind, [wie viele Telefonnummern Sie erhalten können?](how-many-phone-numbers-can-you-get.md)
Die Grenzwerte hängen von der Art der Nummern ab – gebührenfreie Servicenummern, gebührenpflichtige Dienstnummern und Abonnenten Nummern (Nutzer). Jede hat ihre eigenen Grenzwerte und muss unabhängig verwaltet werden. Wenn Sie sich dem Grenzwert nähern (oder Sie die Grenze erreicht haben), können Sie eine Erhöhung des Limits beantragen. Dieser Vorgang wird in dem Artikel im vorherigen Abschnitt beschrieben.

Es kann vorkommen, dass eine Rufnummer in einem Bereich, in dem der Dienst zur Verfügung steht, nicht bereitgestellt wird. Informationen zum Verfahren zum Anfordern von Nummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Team Erstellung (optional)

Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigungen zum Erstellen von Microsoft 365-Gruppen und damit zu einem Team in Microsoft Teams. Wenn Sie eine stärkere Kontrolle haben und [die Erstellung neuer Teams](assign-roles-permissions.md#permissions-to-create-teams) (und damit die Erstellung neuer Microsoft 365-Gruppen) einschränken möchten, können Sie Gruppen Erstellungs-und Verwaltungsrechte an eine Reihe von Administratoren delegieren. Wenn Ihre Organisation diese Option weiter verfolgen möchte, lesen Sie den in diesem Artikel beschriebenen Verfahren, um Benutzern das Senden von Anforderungen zu ermöglichen, die von einem zugewiesenen Team verarbeitet werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tägliche/wöchentliche/monatliche/bedarfsbezogene Aufgaben

| Aktivität                    | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                             | Häufigkeit   | Team zugewiesen |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Dienstverwaltung      | Verwaltung von Mandanten weiten Einstellungen für Teams.                                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Benutzerverwaltung         | Verwaltung benutzerbasierter Einstellungen und Lizenzierung in Teams.                                                                                                                                                                                                                                                                                                                                                           | Nach Bedarf |               |
| Lizenzverwaltung          | Planen Sie den aktuellen und zukünftigen Bedarf sowohl für die Benutzer-als auch für die verbrauchsbasierte Lizenzierung (Anrufpläne und Kommunikationsguthaben), indem Sie den Bericht " [PSTN-Nutzungsbericht](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) " und " [PSTN-Minuten Pools](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) " nutzen. | Wöchentlich    |               |
| Verwaltung von Telefonnummern | Verwalten Sie die verfügbaren Telefonnummern für zukünftiges Wachstum, und passen Sie die Lagerbestände an Ihre organisatorischen Anforderungen an.                                                                                                                                                                                                                                                                                                | Wöchentlich    |               |
| Team Erstellung (optional)    | Überprüfen und Verarbeiten von Anforderungen für die Teamerstellung                                                                                                                                                                                                                                                                                                                                                                          | Nach Bedarf |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>Leitfaden zur Überprüfung der Erlebnisqualität

Der [Leitfaden zur Überprüfung der Qualität](https://aka.ms/qerguide) der Benutzerfreundlichkeit umfasst eine Reihe von Aktivitäten, die in wichtigen Bereichen, die am stärksten zur Verbesserung der Benutzerfreundlichkeit führen, die Behebungs Anleitung bewerten und bereitstellen, wie unten dargestellt.

![Diagramm der zu untersuchenden Bereiche während einer Überprüfung der Qualität der Erfahrung](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während einer Prüfung der Qualität der Erfahrung zu untersuchen sind: Audio-, Zuverlässigkeits-und Nutzerumfrage Ergebnisse.")

Indem Sie die im Leitfaden beschriebenen Bereiche kontinuierlich bewerten und korrigieren, können Sie deren Potenzial verringern, die Benutzererfahrung negativ zu beeinflussen. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

-   Unvollständige Firewall- oder Proxykonfiguration

-   Schlechte WLAN-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Verwendung nicht optimierter oder integrierter Audiogeräte

-   Problematische Subnetze oder Netzwerkgeräte

Die Anleitungen im Leitfaden zur Überprüfung der Qualität der Benutzerfreundlichkeit konzentrieren sich auf die Verwendung von Call Quality Dashboard (CQD) online als primäres Tool zur Berichterstellung und Untersuchung jedes beschriebenen Bereichs, wobei der Schwerpunkt auf Audio liegt, um Akzeptanz und Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Wir empfehlen Ihnen dringend, den Qualitätschampion frühzeitig zu benennen. Nachdem Sie nominiert wurden, sollten Sie sich mit den Inhalten im [Leitfaden zur Überprüfung der Qualität von Erfahrungen](https://aka.ms/qerguide)vertraut machen.

<!--ENDOFSECTION-->
