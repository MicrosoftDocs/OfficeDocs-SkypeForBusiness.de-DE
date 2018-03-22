---
title: Betriebshandbuch für Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 'Aufgaben und Aktivitäten für Teams Servicemanagement, einschließlich Dienststatus: Überwachung, bewerten und sicherstellen, dass Netzwerkqualität und Verwendungsanalyse erforderlich.'
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f8abb573203bcb3f0292604c3b439f5903aa221
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="operate-my-service"></a>Meine Dienst betreiben

## <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

Im Betriebshandbuch enthält eine Übersicht aller Aufgaben und Aktivitäten, die als Teil der Service-Management-Funktion für Microsoft-Teams, erforderlich.

Service-Management ist ein weites, der täglichen Vorgänge des Diensts Microsoft-Teams abdeckt, nachdem es bereitgestellt und für Benutzer aktiviert wurde. Der Teams Service umfasst Microsoft Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt haben (beispielsweise Netzwerk).

Das Konzept der Service-Management ist wahrscheinlich nicht für die meisten Organisationen ein neues Konzept. Sie möglicherweise bereits implementiert haben, Prozesse und Aufgaben, bei die vorhandene Dienste zugeordnet sind. Dies bedeutet, dass Sie Ihre aktuellen Prozesse beim Service-Management heute planen zur Unterstützung von Teams in Zukunft wahrscheinlich erweitern können.

Service-Management umfasst alle Aktivitäten und Prozessen beteiligt Teams Ende zum Verwalten. Wie bereits erwähnt einige Komponenten von Service-Management – die Infrastruktur, die der Office 365-Dienst selbst umfasst – Microsofts Verantwortung sind, während Sie mit dem Kunden verantwortlich für die Benutzer zum Verwalten der verschiedenen Aspekte der Teams, die im Netzwerk sind , und Endpunkte, die Sie bereitstellen.

Die Aufgaben und Aktivitäten in diesem Handbuch sind in acht Kategorien unterteilt, wie in der folgenden Abbildung dargestellt. Jede dieser Kategorien werden in den folgenden Abschnitten erweitert werden.

![Ein Diagramm, in dem eine Liste der Kategorien von Aufgaben und Aktivitäten, die Service-Management für Teams umfassen. Die Abbildung zeigt auch, dass Service-Management zum großen Teil eines Vorgangs Kunden ist.] (media/operate-my-service-image1.png "Ein Diagramm, in dem eine Liste der Kategorien von Aufgaben und Aktivitäten, die Service-Management für Teams umfassen. Die Abbildung zeigt auch, dass Service-Management zum großen Teil eines Vorgangs Kunden ist.")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, wie die Vorgänge für Teams implementiert werden.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Überprüfen Sie im Betriebshandbuch vollständig.</li><li>Implementieren Sie eine Strategie für die Vorgänge, die mit Ihrer Organisation Ziele der Qualität und Zuverlässigkeit der Cloud VoIP Arbeitslasten übermitteln abschließt.</li><li>Überprüfen Sie im Handbuch für die Qualität Erfahrung überprüfen.</li><li> Implementieren Sie eine Strategie Vorgänge für die Qualität Erfahrung Bewertungen, um sicherzustellen, dass Ihre Cloud-VoIP-Bereitstellung auf Spitzenzeiten Funktionen betrieben wird regelmäßig ausführen.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Betriebliche Rolle Zuordnung

Die Planung, den, die Sie für Vorgänge während der Phase der Ermitteln übergeordneter Faktoren hat, ist entscheidend, da Operations Aktivitäten beginnen, wenn die erste Pilotbenutzer aktiviert sind. In diesem Handbuch werden die Aktivitäten und Aufgaben, die für einzelne täglich, wöchentlich, monatlich oder bei Bedarf Verwaltung eine qualitativ hochwertige Teams Bereitstellung ausgeführt werden müssen. Dieses Handbuch enthält Knowledge und Richtlinien zum diese wichtige Aktivitäten und Aufgaben ausführen.

Eine wichtige Komponente einer erfolgreichen Bereitstellung wird sichergestellt, dass die Planung frühzeitig in der Phase Ermitteln übergeordneter Faktoren haben Sie auch das ermitteln, die zum Ausführen bestimmter Aktivitäten zuständig sind. Nachdem Sie die welche Aufgaben und Aktivitäten für Ihre Bereitstellung gelten herausgefunden haben, müssen sie verstehen und dahinter die Gruppen oder Personen, die Sie ihnen zuweisen.

Jedes identifizierte Team muss überprüfen und stimmen auf Aufgaben und Zuständigkeiten identifiziert und starten zur Vorbereitung. Dies kann enthalten, Schulung und Bereitschaft und Bereitstellen von Updates für das Personal, oder sicherstellen möchten, den externen Anbieter übermitteln bereit sind.

Die Aktivitäten und Rollen, die in diesem Handbuch definierten sollte in den meisten Szenarien gültig sein, sondern jeder Bereitstellung von Teams ist eindeutig; Daher können Sie dieses Handbuch als Ausgangspunkt verwenden, Aktivitäten und Standardrollen für Ihre Bedürfnisse anpassen.

Stellen Sie sicher, dass jedes verantwortliche Team einen umfassenden Überblick über die Aktivitäten verfügt, die zum Ausführen des Diensts erforderlich sind. Es ist wichtig, dass jedes Team akzeptiert und ihre Accountability in Ihrer Organisation unterzeichnet vor Beginn des ersten Pilotprojekts.

Nachdem eine Vereinbarung erstellt wurde, sollte die entsprechende Teams zu ihrer Rollen durchsetzen beginnen.

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td>
<td><ul><li>Verwenden Sie dieses Dokument in der betrieblichen Rolle Zuordnung Übung zu vereinfachen.</li><li>Besprechen Sie mit der jeweiligen Supportteams, um jedes Element in der Liste der erforderlichen Aktivitäten Namen zuzuweisen.</li><li>Erlangen Sie Annahme oder Abnahme der zugewiesenen Rollen.</li><li>Stellen Sie sicher, dass die entsprechenden Teams entsprechenden Schulungen, Bereitschaft und Ressourcen für die Durchführung ihrer erforderlichen Aktivitäten verfügen.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams-dienstabhängigkeiten

Microsoft-Teams vereint Technologien über Office 365, um einen Hub für die Zusammenarbeit bereitzustellen. Einige Beispiele enthalten.

-   Azure Active Directory bietet Authentifizierung und Autorisierung Dienste für Teams.

-   Exchange Online bietet erweiterte Funktionen wie rechtliche Aufbewahrungspflicht und elektronische Ermittlung.

-   SharePoint Online bietet die Möglichkeit zum Freigeben von Dateien in Kanälen und OneDrive für Unternehmen bietet einen Mechanismus zum Freigeben von Dateien in einem privaten Chat.

Organisationen können auch vorhandene Investitionen in die lokale Infrastruktur nutzen. Beispielsweise können vorhandene lokalen Active Directory-Konten für die Authentifizierung verwendet werden, durch die Nutzung von Azure Active Directory verbinden. Anstelle von Exchange Online können bestimmte Versionen von Exchange Server verwendet werden.

Diese Technologien zusammengefügt, eine umfassende, Zusammenarbeit und intelligente Communications Suite für Benutzer bereitzustellen. Diese enge Integration ist einer der wichtigsten Vorteile von Teams, aber es auch eine Voraussetzung für Service-Management über diese Technologien Laufwerke.

In diesem Handbuch wird die wichtige Bereiche der Fokus zum Verwalten des Diensts Teams behandelt. In den meisten Fällen verfügen Sie Management Servicepläne für die unterstützenden Technologien, von denen Teams abhängt. Wenn nicht, Sie ordnungsgemäße Management Servicepläne für diese Technologiekomponenten einrichten müssen (lokal und online) als auch. Dies hilft sicherzustellen, dass Ihre Benutzer eine hohe Qualität und zuverlässige Erfahrung mit Teams nutzen zu können.

#### <a name="references"></a>Verweise 

[Übersicht über Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

[Interaktion von Exchange und Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact)

[Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact)

[Microsoft-Teams und Skype für die Business-Interoperabilität](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Operations Guide Aktivitäten

Die folgenden Abschnitte enthalten eine Übersicht über die Aktivitäten, die erforderlich sind, um den Microsoft-Teams, Dienst erfolgreich ausgeführt werden. Dazu gehören Verweis zu Tools und kontextbezogene Informationen zu zusätzliche Inhalte, um die Aktivität Verständnis und Bereitschaft Initiativen rechten zu unterstützen.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitor Dienststatus

Es ist wichtig, dass die allgemeine Integrität des Diensts Microsoft-Teams, verstehen, sodass Sie proaktiv andere in Ihrer Organisation jedes Ereignisses darüber informiert werden können, die den Dienst wirkt sich auf. Wie bereits erwähnt, ist die Teams andere Office 365-Diensten wie etwa Azure Active Directory, Exchange Online, SharePoint Online und OneDrive für Unternehmen abhängig. Aus diesem Grund ist es gleichermaßen wichtig, dass Sie die Integrität der die abhängigen Dienste überwachen.

Integrieren Sie diese Aktivität in Ihrer Incident Management-Prozess proaktiv über die Benutzer, der Helpdesk und Ihren Teams bei der Vorgänge zum Vorbereiten der Benutzer Eskalationen behandeln.

Die folgenden Abschnitte beschreiben die Tools, die Sie zum Überwachen von [Service Vorfälle] nutzen können (https://technet.microsoft.com/library/office-365-service-health.aspx?f=255&MSPPError=-2147217396#Service Vorfälle), die den Dienst Teams beeinflussen. In der folgenden Tabelle ist eine Zusammenfassung der Vorteile der einzelnen Tools, und wenn Sie verwenden sollten, jeweils enthalten.

| Tools für die Überwachung                       | Vorteile                                            | Wann verwendet werden                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Office 365-Portal                     | Von jedem Gerät mit einem unterstützten Browser verfügbar. | Wird verwendet, wenn Sie in Echtzeit Benachrichtigungen nicht erforderlich ist.                                          |
| Office 365-Admin-app                  | Pushbenachrichtigungen an Ihr mobiles Gerät enthält.  | Wenn müssen Sie Notification Service Vorfälle, während Sie unterwegs sind.                  |
| Microsoft System Center               | Integration in Microsoft System Center.           | Erweiterte Überwachungsfunktionen und Benachrichtigung Unterstützung benötigt.                       |
| Office 365-Dienst Communications API | Den programmgesteuerten Zugriff auf Office 365-Dienststatus.   | Sie erfordert die Integration mit einer 3. Partei monitoring Tool oder Ihre eigene Lösung erstellen möchten. |

> [!NOTE]
> Nur Personen, die die Rolle **globaler Administrator** oder **Dienstadministrator** zugewiesen sind, können Dienststatus anzeigen.

### <a name="monitoring-with-the-office-365-portal"></a>Überwachung mit Office 365-portal

Die [Office 365-Portal](https://portal.office.com/) bietet ein [Dienststatus Dashboard](https://portal.office.com/adminportal/home#/servicehealth) , in dem Sie den aktuellen Zustand des Diensts Teams zusätzlich zu abhängigen Dienste anzeigen können.

### <a name="monitoring-with-the-mobile-app"></a>Überwachen mit der mobilen app

Die Office 365-Admin-app ist verfügbar unter Apple iOS, Android und Windows (PC und Mobile). Die app enthält Dienstadministratoren Informationen zu Dienststatus und anstehende Änderungen. Die app unterstützt Pushbenachrichtigungen, die Sie fast sofort warnen können nachdem eine Empfehlung bereitgestellt wurde. Dadurch können Sie den Status, Integrität und anstehenden Änderungen an den Dienst auf dem laufenden. Die Benachrichtigung Unterstützung erleichtert das empfohlene Tool für die Überwachung für Administratoren. Weitere Informationen finden Sie unter:

[Office 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Laden Sie die Office 365-Admin-Mobile-App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Mit Microsoft System Center Monitoring

Microsoft System Center ist eine integrierte Management-Plattform, dass Sie Datacenter, Clientgeräten und hybride verwalten können IT-Umgebungen cloud. Office 365-Administratoren, die System Center jetzt verwenden, haben die Option zum Importieren der Office 365-Management Pack, wodurch sie alle Dienstkommunikation in Operations Manager in System Center anzeigen können. Mit diesem Tool ermöglicht den Zugriff auf den Status Ihrer abonnierten Dienste, aktiven und behobenen Dienstereignisse und Ihre Kommunikation Nachrichtencenter (anstehende Änderungen). Weitere Informationen finden Sie in der folgenden [Blogbeitrag](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Wenn Sie System Center zum Überwachen von Teams Service Health (und abhängigen Dienste) nutzen, können Sie weiter anpassen das Management Pack für Warnung oder benachrichtigen Sie bestimmte Gruppen oder Personen, die auf Vorfälle reagieren identifiziert wurden.
Diese Gruppen können Service Besitzer, Helpdesks, Unterstützung auf zweiter und dritter Ebene Gruppen und Vorfall-Manager in Ihrer Organisation enthalten.

### <a name="monitoring-for-advanced-scenarios"></a>Überwachung für erweiterte Szenarien

Sie können Dienststatus und anstehende Änderungen überwachen, durch die Nutzung von Office 365-Dienststatus und ändert den programmgesteuerten Zugriff auf die Office 365-Communications-API. Verwenden Sie diese API zum Erstellen eigener monitoring Tools oder Verbinden Sie Ihrer vorhandenen Überwachungstools mit Office 365-Dienst Communications, potenziell vereinfachen, wie Sie Ihre Umgebung überwachen. Weitere Informationen finden Sie unter [Office 365 für Enterprise-Entwickler](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                               | Trittfrequenz   | Team zugewiesen |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitor Dienststatus | Proaktive Überwachung Dienststatus Microsoft-Teams (und abhängigen Dienste) mithilfe der Tools verfügbar. Einschließen von abhängigen Dienste: Exchange Online, SharePoint Online, OneDrive für Unternehmen, Azure Active Directory. | In Echtzeit |               |
| Vorfall Benachrichtigung  | Benachrichtigen Sie interne beteiligten von Ereignissen, die den Dienst Teams betreffen. Interne Beteiligten können Benutzer, Helpdesks und Vorfall-Manager enthalten.                                                                          | Bei Bedarf |               |

### <a name="references"></a>Verweise 

[Gewusst wie: Überprüfen von Office 365-Dienststatus](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Überprüfen der Integrität der Dienst für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/service-health)

[Dienststatus und Continuity](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Verwalten von Organisationseinheiten ändern

Microsoft-Teams, ist ein Cloud-basierten Dienst. Aber auch die Möglichkeit, neue Features und Funktionen in eine schnelle Tempo bereitzustellen. Laufende Innovation bietet Organisationen einen offensichtlichen Vorteil, aber diese Änderungen müssen innerhalb Ihrer Organisation zur Vermeidung von Widerstand oder an den Helpdesk entsprechend verwaltet werden.

Updates für Teams werden automatisch an Ihre Benutzer eingeführt. Die Benutzer müssen immer die neuesten Client und Features, die im Dienst Teams verfügbar. Es ist nicht möglich, die Einführung von Teams-Updates für die Benutzer zu verwalten, es ist daher extrem wichtig Änderung über effektiven Kommunikation, Schulung und Akzeptanz Programme verwalten. Wenn Ihre Benutzer die Änderung kennen, zu den Vorteilen geschult und in der Lage, die neuen Funktionen nutzen&mdash;werden schneller Wartungszeiten und Willkommen bei den ändern können.

### <a name="monitoring-for-change"></a>Überwachung für Änderung

Der erste Schritt beim Änderungsmanagement überwacht die Änderungen, die für Teams geplant werden. Die beste Quelle für die Überwachung diese Änderungen ist [Wegweiser für Office 365](https://products.office.com/business/office-365-roadmap), die Features aufgeführt, die derzeit in der Entwicklung an Ihre Kunden eingeführt werden oder komplett gestartet haben. Sie können mithilfe des Filters für Teams-spezifischen Features suchen oder können Sie der Übersicht über die auf einer Excel-Datei zur weiteren Analyse herunterladen. Für jedes Feature bietet der Übersicht über die eine kurze Beschreibung, zusammen mit der erwarteten Veröffentlichungsdatum.

Im [Blog des Microsoft-Teams,](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)erhalten Sie Informationen zu bewährten Methoden, Trends und Neuigkeiten zu Teams Produktupdates. Erwarten Sie wichtiges Feature Updates für Teams hier vorgestellt. Sie können auch den Blog über einen RSS-feed abonnieren. Anschließend können Sie [den RSS-feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) direkt in einem Kanal Teams hinzufügen, damit alle wichtigen News direkt in Teams gesendet wird.

[Versionshinweise für Microsoft-Teams,](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)sind alle Features, die veröffentlicht werden dokumentiert.
Hier finden Sie eine Liste der Features, die freigegeben wurden für Desktop, Web und mobile Geräte. Der gleiche Satz von Anmerkungen zu dieser Version sind auch auf der Registerkarte Notizen freigeben in der [Microsoft-Teams T-Bot](https://docs.microsoft.com/microsoftteams/t-bot)verfügbar.

Machen Sie sich vertraut mit den verfügbaren Ressourcen, und stellen Sie sicher, dass Sie zutreffend Besitzer zum Überwachen von Änderung zuweisen.

### <a name="planning-for-change"></a>Planen der Änderung

Nun, da Sie anstehende Änderungen an den Dienst Teams bekannt sind, besteht der nächste Schritt zum Vorbereiten und entsprechend planen. Bewerten Sie die einzelnen ändern, um zu bestimmen, welche Änderungen Kommunikation mit Benutzern, Kampagnen zur Förderung des Bekanntheitsgrads, Schulung für Support-Teams oder Benutzern oder Feature Test- und Annahme Kampagnen erfordern. Dies ist die primäre Rolle von einer Änderung Managementteam in Ihrer Organisation. Es folgt eine Auflistung von Beispiel-Tabellen, die Ihnen helfen zu planen.

[//]: # (Die Spaltenbreite und Zeilenhöhe in dieser Tabelle sind schöne, jedoch nicht unterstützte in Abzugsverteilung(en), mindestens die rowspans ist. Dies ist so ähnlich wie ich erhalten können. Vielleicht benötigt das ganze auch umdrehen Neuentwurf.)

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Feature: Cloud-Aufzeichnung (Datum der Veröffentlichung: Januar 2018)

**Allgemeine nachverfolgen**
| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Rechtliche Prüfung   | Abgeschlossen     | Dieses Feature ist eine Voraussetzung für die Schulung des Teams Onboarding. | Das Projektteam  |

**Technische Änderungsmanagement**
| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| IT-Änderungen erforderlich          | Ja                  | Admin muss Aufzeichnung identifizierten nur für Benutzer zu aktivieren.      | Supportteam           |
| Vollständige technische Bereitschaft | Ja                  |                                                                 | Supportteam  
         |
**Die Verwaltung von ändern** 
| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Beeinträchtigung für die Benutzer                  | Niedrig                  |                                                                 |                        |
| Benutzerbereitschaft erforderlich      | Ja                  |                                                                 |                        |
| Kommunikation bereit         | Nein                   | Kommunikation e-Mail wurde entworfen wurde – Überprüfung aussteht.            | Communications-Teams    |
| Schulung bereit               | Ja                  | Schulung werden vorhandene Microsoft Video nutzen.                | Schulung-Teams          |

**Nachverfolgen des Status**
| Ändern der Bereitschaft | Status   | Notizen/nächste Schritte | Besitzer |
|----|----|----|-----|
| Veröffentlichungsstatus               | in Bearbeitung          | Ausstehende Überprüfung durch executive Sponsor.               | Ändern von Management-Team |
| Version deaktiviert             |                      |                                                                 |                        |
| Datum der Veröffentlichung                 |                      |                                                                 |                        |

Weitere Informationen zur Planung für das Änderungsmanagement mit den Teams finden Sie unter [Erstellen einer Strategie für Microsoft-Teams ändern](https://docs.microsoft.com/microsoftteams/change-management-strategy).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität               | Beschreibung                                                                                                                                                                                                                | Trittfrequenz   | Team zugewiesen |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitor für Änderung     | Prüfen auf anstehende Änderungen an den Dienst Microsoft-Teams.                                                                                                                                                                   | Täglich     |               |
| Planen der Änderung    | Bewerten und Planen der neuen Features und Funktionen, einschließlich Kommunikationsplänen, zur Förderung des Bekanntheitsgrads Kampagnen und Schulung.                                                                                                     | Bei Bedarf |               |
| Benutzerbereitschaft             | Führen Sie gezielte Kommunikation, zur Förderung des Bekanntheitsgrads oder Schulung Kampagnen, um sicherzustellen, dass Benutzer für die bevorstehende Änderung bereit sind.                                                                                                        | Bei Bedarf |               |
| Support Team Bereitschaft | Führen Sie gezielte Kommunikation, zur Förderung des Bekanntheitsgrads oder Schulung Kampagnen, um sicherzustellen, dass das Supportteam bereit ist. Supportteams zählen "weißen Handschuh" Team, Helpdesks, Stufe 2 oder Stufe 3-Unterstützung, externe Partner und So weiter. | Bei Bedarf |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Bewerten der Verwendung von Teams

Nachdem der Pilotphase begonnen hat, ist es wichtig, einen regulären Trittfrequenz zur Messung der tatsächlichen Teams Verbrauch einrichten. In Ihrer Organisation erhalten Sie Einblicke in wie die tatsächliche Verwendung ausgerichtet die Nutzung, die Sie während der Phase der Ermitteln übergeordneter Faktoren vorhergesagt können. Obwohl in diesem Abschnitt zur Verwendung von Teams behandelt, sollte dies Bestandteil einer größeren Aufwand zu messen und Bewerten der Office 365-Auslastung insgesamt sein.

Überprüfen häufig zu einem frühen Zeitpunkt Verwendung in der Bereitstellung haben Sie die Möglichkeit:

-   Überprüfen Sie, ob Benutzer Teams verwenden.

-   Möglichen Annahme Probleme zu erkennen, bevor sie kritische Probleme in der gesamten Organisation erstellen.

-   Verstehen Sie, ob zwischen dem Ermitteln übergeordneter Faktoren Phase Anforderungen und dem tatsächlichen Verbrauch Diskrepanzen.

Wenn Verwendung nicht, was Sie erwartet, möglicherweise aufgrund eines Problems Bereitstellung oder der Anpassungsplan ist nicht ordnungsgemäß ausgeführt werden, oder ein anderer Problem wird. Je nach den tatsächlichen Grund hinter der geringen Verwendung muss mit den zugehörigen Teams, die bei der Verwendung Hindernisse unterstützen Dienstadministrator zusammenarbeiten.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Messen der Verwendung mit Office 365 Administrationscenter

Verwendungsdaten von Teams ist im Dashboard Reporting verfügbar. Verwendungsdaten Teams können in drei verschiedene Berichte gefunden werden. Der erste Bericht bietet eine Ansicht produktübergreifende wie Benutzer kommunizieren und zusammenarbeiten, indem Sie die verschiedenen Dienste in Office 365 verwenden. In diesem Bericht kann, finden Sie hier: [Office 365 aktive Benutzer Bericht](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Die anderen beiden Berichte sind Teams-spezifisch und bieten weitere Details zur Nutzung des Teams von einem Benutzer und Gerät Perspektive. Beide Berichte finden Sie hier:

[Bericht zur Verwendung der Microsoft-Teams Gerät](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Bericht über Benutzeraktivität Microsoft-Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Erforderliche Berechtigungen

Die Verwendungsberichte in der Verwaltungskonsole können Benutzer darauf zugreifen, die einer Rolle **globaler Administrator** oder eine produktspezifische Administratorrolle (**Exchange-Administrator**, **Skype für Business-Administrator**, **SharePoint zugewiesen wurden Administrator**).

Darüber hinaus ist die Rolle **Leser von Berichten** verfügbar für Benutzer, die Zugriff auf die Berichte benötigen, aber keine Aufgaben ausführen, die auf Administratorebene Berechtigungen erforderlich sind. Sie weisen Sie diese Rolle schafft für jeden Verwendungsberichte, Beteiligten, überwachen und Laufwerk Einführung ist. Weitere Informationen zu den verschiedenen Rollen verfügbar finden Sie unter [Informationen zu Office 365-Administratorrollen](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Bewerten der Verwendung

Nachdem Sie das Dashboard Reporting Auslastung Messen verwendet haben, ist es wichtig, die gemessene Nutzung gegen alle Indikatoren für den Erfolg (KSIs) verglichen werden soll, die Sie während des Projekts Ermitteln übergeordneter Faktoren Phase definiert. Sie können eine KSI, die als active Verwendung definiert werden kann oder eine, die mit aktiven indirekt verknüpft wie folgt definieren.

Es ist wichtig, um alle Unterschiede zwischen der aktuellen und der geplanten Verwendung vor die Einführung auf zusätzliche Standorte oder Benutzer fortsetzen zu identifizieren. Sie benötigen wahrscheinlich Organisationseinheit Befunde identifizieren, im Rahmen dieser Aktivität, den Sie verwenden können, um sicherzustellen, dass der nächste Batch von Websites oder Benutzer die gleichen Probleme auftreten, nicht.

Ermitteln Sie zunächst, ob dies eine Annahme und/oder technischen Problem ist. Beginnen Sie mit dem Untersuchen von Elemente unten in der Reihenfolge, um zu bestimmen, wo das Problem liegt.

1.  Überprüfen der Qualität Datenquellenanbieters [Qualität Erfahrung überprüfen](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#quality-of-experience-review-guide).

2.  Arbeiten Sie mit dem Helpdeskteam zu überprüfen, ob es sind keine Trend technische Probleme, die verhindern, dass Benutzer den Zugriff auf oder die Verwendung des Diensts. Problemtrends vorhanden sind, verwenden Sie im Abschnitt [Endpunkt Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#endpoint-troubleshooting) weiter unten in diesem Artikel um zu versuchen, das Problem zu lösen, bevor ansprechender Support.

3.  Arbeiten Sie mit dem Team Schulung und Anpassung von Benutzern direktes Feedback sammeln (finden Sie weiter unten in diesem Artikel unter [Assess Benutzer Stimmung](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#assess-user-sentiment) ) und die Effektivität des Aktivitäten zur Förderung des Bekanntheitsgrads und Annahme zu überprüfen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität                         | Beschreibung                                                                                                                      | Trittfrequenz   | Team zugewiesen |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Measure Usage (Aktivierung Phase) | Messen Sie und bewerten Sie Teams Verwendung während der Phase der Aktivierung, wie Websites weiterhin Onboarded sein. Beheben Sie Probleme bei der Verwendung nach Bedarf. | Wöchentlich    |               |
| Measure Verwendung                    | Messen und Bewerten von Teams Verwendung in der Phase Laufwerk Wert (nach der Bereitstellung abgeschlossen ist). Beheben Sie Probleme bei der Verwendung nach Bedarf. | Alle zwei Wochen  |               |
| (Laufwerk Wert Phase)              |                                                                                                                                  |           |               |
| Aktualisieren von Anpassungsplan             | Aktualisieren Sie Ihre Anpassungsplan basierend auf wie gemessene Usage vergleicht auf Ihre Planung Ziele.                                         | Bei Bedarf |               |

### <a name="references"></a>Verweise 

[Informationen zum Office 365 Administrationscenter](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Bewerten der Benutzer Stimmung

Grundlegendes zu Stimmung der Benutzer kann als ein Schlüsselindikator für den Erfolg Ihrer Bereitstellung Teams Bewertung fungieren. Feedback der Benutzer kann die Änderungen in Ihrer Organisation Laufwerk; Dies kann Änderungen an Ihrer Kommunikationsplänen, Schulungsprogramme oder die Möglichkeit, dass Sie Unterstützung für Ihren Benutzern anbieten enthalten.

Es ist wichtig, früh Feedback erhalten möchten, und fahren Sie mit Benutzer Stimmung im gesamten Lebenszyklus des Projekts und darüber hinaus bewerten. Verwenden Sie die folgende Hinweise, um das Intervall zu bestimmen, in dem Ihre Organisation das Feedback seek wird:

-   **Beginn des Projekts**: mit der Bewertung der Benutzer Stimmung am Anfang des Projekts, erhalten Sie eine frühe Ansicht in wie Ihre Benutzer ihre Teams Erfahrung haben.

-   **Nach der wichtigsten Meilensteine**: durch das Sammeln von Feedback im gesamten Projektlebenszyklus, können Sie Benutzer Stimmung permanenten einzuschätzen und Änderungen vorzunehmen, je nach Bedarf. Dies ist insbesondere dann hilfreich, nach der wichtigsten Meilensteine.

-   **Project-Zusammenfassung**: Benutzer Stimmung am Ende eines Projekts bewerten informiert Sie darüber, wie gut Sie durchgeführt haben und, in denen Arbeit noch muss ausgeführt werden und können Sie Ergebnisse anhand der vorherigen Umfrage zu vergleichen.

-   **Laufend Besprechung**: weiterhin Benutzer Stimmung auf unbestimmte Zeit gemessen. Änderungen in Stimmung Benutzer möglicherweise aufgrund von Änderungen in der Umgebung Ihrer Organisation oder Änderungen im Dienst Teams. Bewertung Benutzer Stimmung in regelmäßigen Abständen, können Sie verstehen, gut Ihre Service-Management-Teams und wie Ihre Organisation auf Änderungen in der Teams Dienst reagiert.

Stimmung der Benutzer kann über viele verschiedene Methoden überprüft werden. Dazu zählen e-Mail Umfragen, persönlicher oder Telefon-Schreibweise Interviews oder erstellen einen Kanal Feedback einfach in Teams oder Yammer. Weitere Informationen finden Sie unter [bewährte Methoden für die Benutzer Feedback Methoden in Microsoft-Teams](https://docs.microsoft.com/microsoftteams/best-practices-feedback).

Sie können auch einen Ansatz Branche bewerten können Benutzer Stimmung aufgerufen net Promotor Punktzahl (NPS), die im folgenden Abschnitt beschrieben wird.

### <a name="nps"></a>NPS 

NET Promoter Score (NPS) ist ein industrywide Kunden können Metrik und stellen eine gute Methode zum Benutzer Stimmung bewerten.

NPS kann berechnet werden, indem Sie zwei Fragen: "wie wahrscheinlich Sie Teams an einen Kollegen empfehlen werden?", gefolgt von der Frage formfreies "Warum?"

NPS ist ein Index, im Bereich von – 100 bis 100, der einem Kunden Bereitschaft zur Produkt oder den Dienst des Unternehmens empfiehlt sich misst. NPS basiert auf einer anonymen Umfrage, die an Benutzer über e-Mail oder anderweitig elektronische übermittelt werden. NPS misst die Bindung zwischen einem Anbieter und Consumer. Es besteht nur eine Frage, die der Benutzer zum Bewerten ihrer Erfahrung von 1 bis 10, mit der Option zur Verfügung zu stellen zusätzliche Kommentare aufgefordert. Benutzer werden dann klassifiziert basierend auf den folgenden Filter:

-   9 oder 10 sind Projektträger: treu Anhänger, die Ihren Dienst herauf- und geschäftliches andere werden.

-   7 oder 8 sind passiv: zufrieden jedoch unenthusiastic, einem anderen Dienst oder besser anfällig.

-   Von 1 bis 6 werden geben: unzufriedenen Kunden, die Ihren Dienst beschädigen und Wachstum beeinträchtigen können.

![Dieses Diagramm veranschaulicht die Skala NPS. Es zeigt, dass 0-6-Rangordnungen sind geben, 7 und 8 sind passive und 9 bis 10 Projektträger.] (media/operate-my-service-image2.png "Dieses Diagramm veranschaulicht die Skala NPS. Es zeigt, dass 0-6-Rangordnungen sind geben, 7 und 8 sind passive und 9 bis 10 Projektträger.")

Obwohl die Zahl zur base NPS nützlich ist, erhalten Sie den größten Nutzen, durch das Analysieren von Benutzerkommentare. Sie helfen Ihnen zu verstehen, warum der Benutzer Teams an andere Personen empfehlen würden (oder würde nicht). Geben Sie diese Kommentare können wertvolles Feedback, um die Project-Hilfe oder Service-Management-Teams verstehen, die Anpassungen erforderlich, um einen Dienst für die Qualität.

Um NPS Umfragen für Ihre Organisation zu ermöglichen, können Sie Ihre bevorzugten Onlineumfrage Tool nutzen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/als erforderlichen Aufgaben

| Aktivität              | Beschreibung                                                                                                                                                                         | Trittfrequenz   | Team zugewiesen |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Bewerten der Benutzer Stimmung | Erfassen Sie und bewerten Sie der Benutzer Stimmung mithilfe von Umfragen oder Interviews oder über einen Kanal Feedback in Teams oder Yammer.                                                                 | Bei Bedarf |               |
| Aktualisieren der Annahme Pläne | Laufwerk Änderung in Ihrer Organisation basierend auf Feedback der Benutzer; Hierzu gehören Änderungen an Ihrer Kommunikationsplänen, Schulungsprogramme oder die Möglichkeit, dass Sie Unterstützung für Ihren Benutzern anbieten. | Bei Bedarf |               |

### <a name="references"></a>Verweise 

[NET Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Verwenden von Yammer zum Sammeln von Feedback](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Bewährte Methoden für Benutzerfeedback](https://docs.microsoft.com/microsoftteams/best-practices-feedback)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Verwalten der Netzwerkqualität

Rufen Sie viele Planung Kernelemente optimieren, rechts Sizing und Korrigieren von Ihrer Netzwerkinfrastruktur, um sicherzustellen, dass einen hohe Qualität und effizienten Pfad für den Dienst Microsoft-Teams. In vorherigen [Bereitschaft des Netzwerks](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) der Anleitung werden die Aufgaben und Anforderungen behandelt. Netzwerke weiterentwickelt werden häufig mit der Zeit aufgrund von Upgrades, Erweiterung oder anderen geschäftlichen Anforderungen. Es ist wichtig, dass Sie Ihren Anforderungen für Teams in Ihrem Netzwerk Planungsaktivitäten berücksichtigt.

Obwohl Netzwerk Planen einer Bereitstellung Teams ein wichtiger Aspekt ist, ist es gleichermaßen wichtig, um sicherzustellen, dass das Netzwerk fehlerfrei bleibt und bleibt aktuell, basierend auf geschäftlichen oder technischen Anforderungen ändern.

Um die Integrität des Netzwerks sicherzustellen, müssen eine Reihe von Operationen Aktivitäten in geplanten Intervallen ausgeführt werden.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität                                                       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                 | Trittfrequenz                | Team zugewiesen |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Überwachen von Office 365 IP-Adressen und URLs                                | Überwachen von Änderungen an den [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) mithilfe von den bereitgestellten [RSS-feed](https://go.microsoft.com/fwlink/p/?linkid=236301) , und starten Sie eine Anforderung einer entsprechenden Netzwerke Gruppen.                                                                                                                                | Täglich                  |               |
| Aktualisieren des Netzwerks aufgrund von Änderungen in Office 365 IP-Adressen und URLs | Nehmen Sie die entsprechenden Netzwerkkomponenten (Firewalls, Proxyservern, VPNs, mithilfe der clientseitigen Firewalls und usw.) entsprechend den Änderungen an den [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips)überarbeitet Updates.                                                                                                                                                              | Bei Bedarf              |               |
| Geben Sie zum Erstellen von Daten                                          | Stellen Sie aktualisierte Subnetz für die Qualität Champion (oder beteiligten), um sicherzustellen, dass die [Erstellung von Definitionen im CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) auf dem aktuellen Stand gehalten werden. | Bei Bedarf              |               |
| Implementieren der Änderung                                               | Implementieren Sie Änderungen im Netzwerk zu Support veränderbaren Teams geschäftliche und technische Anforderungen. Netzwerkelementen können Folgendes umfassen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelt und Wi-Fi-Netzwerke</li><li>Internet-Konnektivität und ExpressRoute</li><li>DNS</li></ul>     | Bei Bedarf              |               |
| Netzwerk-Überwachung und berichterstellung                               | Überwachen des Netzwerks durchgehende für Verfügbarkeit, Kapazität Trends und Auslastung mit Ihrer vorhandenen Drittanbieter-Netzwerk-Verwaltungstools und reporting-Funktionen, die von Ihrem Netzwerkanbieter zur Verfügung. Verwenden Sie Trend Daten für die Netzwerk-kapazitätsplanung.                                                                                                            | Täglich, wöchentlich, monatlich |               |
| Kapazitätsplanung                                              | Zusammenarbeit mit den Teams Service Besitzern zu verstehen, geschäftliche und technische Anforderungen, die zusätzliche Kapazität Änderungen Laufwerk möglicherweise ändern. Nutzen Sie die Ergebnisse aus dem [Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) zu gewährleisten, dass genügend Bandbreite für Microsoft-Teams zur Verfügung steht.                               | Bei Bedarf              |               |
| Behandlung von Netzwerkproblemen und-Wartung                        | Unterstützen der Teams Helpdesks, Dienstbesitzer und der verantwortlichen beheben und Beheben von Problemen, um im Zusammenhang mit der Konnektivität Teams, Zuverlässigkeit oder Qualität. Netzwerkelementen können Folgendes umfassen:<ul><li>Firewalls</li><li>VPNs</li><li>Verkabelt und Wi-Fi-Netzwerke</li><li>Internet-Konnektivität und ExpressRoute</li><li>DNS</li></ul>    | Bei Bedarf              |               |
| Disaster Recovery und Testen der hohen Verfügbarkeit                | Führen Sie regelmäßige hohe Verfügbarkeit und Disaster Recovery-Tests für die Netzwerkinfrastruktur, um sicherzustellen, dass es sich um den angegebenen Dienst-Level-Ziele (SLOs) oder Service Level Agreements (SLAs) für den Dienst Teams erfüllt.                                                                                                                                                  | Monatlich                |               |


### <a name="references"></a>Verweise 

[Netzwerk-Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips)

[Erstellen von Daten-Schema](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Bewerten und Sicherstellen der Qualität 

Alle Organisationen benötigen, eine Gruppe oder eine Person für die Qualität verantwortlich sein. Dies ist die wichtigste Funktion im Service-Management. Die Rolle für die Qualität Champion wird an eine Person oder Gruppe, die über ihre Benutzer wünschen engagierten ist zugewiesen.
Diese Rolle erfordert die Fähigkeiten Trends in der Umgebung und der Unterstützung durch die anderen Teams Remediation Laufwerk entwickelt erkennen. Der beste Kandidat für einen Qualitätspionier ist normalerweise der Leiter des Kundendiensts. Je nach Größe und Komplexität der Organisation kann dies eine Person oder Gruppe mit dem Schwerpunkt auf sicherstellen, dass ein hoher Qualität Benutzererlebnis sein.

Die Qualität Champion nutzt vorhandenen Tools und dokumentierte Prozessen, wie etwa aufrufen Quality Dashboard (CQD) und eine Anleitung Qualität erleben Sie die Überprüfung zum Überwachen der Benutzer wünschen, identifizieren Qualität Trends und-Wartung Laufwerk bei Bedarf.
Die Qualität Champion sollten mit den jeweiligen Teams auf Laufwerk Remediation Aktionen und Bericht zu einem Lenkungsausschuss zu des Fortschritts und der Probleme open arbeiten.

[Erleben Sie die Überprüfung Handbuch für Quality of](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) enthält Aktivitäten, die bewerten und-Wartung Anleitungen in wichtige Bereiche, die am stärksten zur Verbesserung der benutzerfreundlichkeit auswirken. Der Anleitungen in im Handbuch für die Überprüfung von Quality Erfahrung behandelt CQD Online als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die Maximieren Verwendung. Versucht, das Netzwerk zur Verbesserung der Audioqualität Optimierungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen. Nach dem benannt wird, sollten sie beginnen mit dem Inhalt im Handbuch für die Qualität Experience-Überprüfung und zugehörige Schulungsmaterial vertraut machen.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität                               | Beschreibung                                                                                                                                                                                                                                                                                                 | Trittfrequenz                             | Team zugewiesen |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Benennen Sie und Schulen Sie Qualität champion(s) | Benennen und eine Qualität Champion(s) Schulen.                                                                                                                                                                                                                                                                   | Bei Bedarf                           |               |
| Führen Sie die Qualität Erfahrung Reviews (engl.)     | Führen Sie Wiederholung Erfahrung Qualität (QER) Trends bei der Qualität und Zuverlässigkeit zu identifizieren, Überprüfung anhand definierter Ziele und melden sich an der Verantwortlichen in der Organisation.                                                                                                                            | Monatlich (wöchentlich während Bereitstellungen) |               |
| Laufwerk-Wartung                      | Koordinieren von Remediation-Maßnahmen in der Organisation basierend auf der QER Bewertung und die Ergebnisse.                                                                                                                                                                                                           | Bei Bedarf                           |               |
| Erstellen von Daten in CQD aktualisieren            | Aktualisieren oder neue Definitionen für Gebäude in CQD hinzufügen, wenn mit dem Netzwerk geändert wird (siehe [Erstellen Hochladen von Informationen](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Bei Bedarf                           |               |
| Füllen Sie die Qualität Champion(s)-Rolle      | End-to-End-Verantwortung für die Qualität in der Organisation. Dazu gehören:<ul><li>Stellen Sie sicher, dass die QER regelmäßig durchgeführt wird.</li><li>Skalieren der verantwortlichen Mitarbeiterstatus Qualität melden.</li><li>Vergewissern Sie sich zum Erstellen von Daten, die Definitionen Stand sind.</li><li>Koordinieren von Remediation-Maßnahmen in der Organisation, um sicherzustellen, dass Benutzer eine hohe Qualität Erfahrung mit Teams verfügen.</li></ul>          | Täglich                               |               |



### <a name="references"></a>Verweise 

[Hier erfahren Sie, CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Informationen zum Erstellen von hochladen](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Quality of Experience überprüfen Guide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Verwalten von Endpunkten

Microsoft-Teams, Endpunkte können als jeder PC, Mac, Tablet oder Mobiltelefonnummer (oder eines anderen) Gerät, die auf dem Client Teams definiert werden. Der Begriff *Endpunkt* umfasst nicht nur dem Gerät selbst, aber wie ein Benutzer auf das Gerät verbindet – beispielsweise mithilfe des Geräts integrierten Mikrofon oder Lautsprecher, Ohrstöpsel oder eine optimierte Kopfhörer. Nachdem sie bereitgestellt haben, müssen Endpunkte nicht vergessen. Die Teams Endpunkte erfordern laufenden Wartung und Pflege. Den folgenden Abschnitten werden bestimmte Bereiche konzentrieren.

### <a name="endpoint-requirements"></a>Anforderungen für Endpunkt

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem aktuellen Stand ist. Die Clients auf dem PC und Mac werden aktualisiert, mit einem Hintergrund, die für neue Builds überprüft und den neuen Client heruntergeladen, wenn die app im Leerlauf befindet. Die mobilen apps Teams sind über ihre jeweiligen app Speicher aktualisiert.

Der Client Teams über Mindestanforderungen im Hinblick auf die zugrunde liegenden Softwareplattform verfügt. Diese Anforderungen möglicherweise über einen Zeitraum ändern, und daher ist es wichtig, dass Sie diese Änderungen überwachen. Der Client Teams verfügt beispielsweise über eine minimale iOS-Version. Wenn der Client einen Internetbrowser verwendet, muss der Browser ebenfalls aktualisiert werden. Eine Liste der unterstützten Plattformen finden Sie in [Get-Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Endpunkt firewalls

Mithilfe der clientseitigen Firewalls können eine erhebliche Auswirkungen Benutzerinteraktion haben.
Mithilfe der clientseitigen Firewalls können sogar anzurufen aufgebaut wird und die Anrufqualität beeinflussen. Nachdem die entsprechenden Ausnahmen auf dem Clientfirewall konfiguriert wurden, müssen sie auf dem aktuellen Stand werden anhand der Informationen in [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips). Ihre Drittanbieter müssen spezifische Leitfäden dafür, wie die Ausnahmen zu aktualisieren.

### <a name="wi-fi-drivers"></a>Wi-Fi-Treiber

Wi-Fi-Treiber können problematisch sein. Als Beispiel möglicherweise ein Treiber sehr aggressive roaming-Verhaltens zwischen Zugriffspunkten, die nicht benötigte-Zugriffspunkt wechseln, dem führenden Anruf schlechter Qualität auslösen kann. Ein leistungsschwachen Wi-Fi-Treiber möglicherweise durch eine Prüfung der Qualität Erfahrung festgestellt werden (siehe [Erfahrung überprüfen Handbuch für Quality of](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/CloudVoice-working/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) für mehr Details). Es ist wichtig, einen Qualität datengesteuerten Prozess implementieren, der neue Wi-Fi-Treiber überwacht und stellt sicher, dass sie vor dem allgemeinen Benutzersegmente bereitgestellt wird getestet werden.

### <a name="endpoint-management"></a>Endpunkt-Verwaltung

Ein Katalog mit unterstützten Endpunkten und Geräte (wie Headsets) Schnittstelle sollte verfügbar und verwaltet werden. In diesem Katalog wird eine Liste der zugelassenen Geräte enthalten, die ausgewählt und als Teil der Phasen envisioning und Onboarding überprüft wurden. In der Regel bestimmte Geräte sind für die einzelnen Rollen in Ihrer Organisation ausgewählt und erfüllt die Anforderungen der Attribute, die diese Rolle. Alle Endpunkte haben einen Lebenszyklus, und es wird benötigt zum Verwalten der Anbieter Verträge, Garantie, Ersatz, Verteilung und Reparieren Richtlinien, die diese Geräte zugeordnet.

### <a name="endpoint-troubleshooting"></a>Endpunkt-Problembehandlung

Auch wenn Sie die vorherige Anleitung durchgeführt haben, können Benutzer in Ihrer Organisation weiterhin bei Teams Probleme auftreten ausgeführt. Obwohl möglicherweise das Problem nicht mit dem Endpunkt selbst, sind die Symptome des Problems in der Regel durch den Client für den Benutzer verfügbar gemacht. Die folgende Anleitung soll allgemeine Schritte zu übermitteln, die Sie ergreifen können, um dieses Problem zu beheben. Es ist nicht als ein umfassender Leitfaden zur Problembehandlung. Die Schritte in einer bestimmten Reihenfolge bereitgestellt werden, aber sie müssen nicht explizit ausgeführt werden und möglicherweise nicht zutreffend, abhängig von der Art des Problems.

1.  **Überprüfen Dienststatus:** Das Problem aus, das ein Benutzer unter Umständen auftreten kann möglicherweise auf ein Ereignis verknüpft werden, die sich negativ auf den Dienst Teams oder abhängigen Dienste betrifft. Als ersten Schritt wird empfohlen, dass Sie bestätigen, dass keine aktiven Dienstprobleme aufgetreten sind. Wenden Sie sich an [Office 365-Dienststatus zu überprüfen](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Denken Sie daran, prüfen, ob der Status der abhängigen Dienste (Beispiele; Exchange, SharePoint, OneDrive für Unternehmen). Überwachung für Dienststatus im Abschnitt ausführlich erläutert wird **Dienststatus Monitoring.**

2.  **-Clientkonnektivität überprüfen:** Verbindungsprobleme verursachen Funktionalität oder Registrierungsprobleme in Teams. (Besonders für neue Websites oder Standorte) wird empfohlen, dass Sie die Verbindung mit dem Dienst überprüfen. Stellen Sie sicher, dass die folgende Anleitung für [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) für jeden Standort des Telefonfestnetzes verwendet wird. Sie können das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) Informationen zum Ausführen eines Verbindungstest, um zu überprüfen, dass die medienports ordnungsgemäß für die Cloud-Sprachfunktionen geöffnet wurden nutzen. Ausführliche Schritte zum Ausführen der Verbindungstests werden in der Anleitung [Bereitschaft des Netzwerks](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) bereitgestellt.

3.  **Überprüfen Sie die Liste der bekannten Probleme:** Finden Sie in der [Liste bekannter Probleme für Teams](https://docs.microsoft.com/MicrosoftTeams/known-issues) , um festzustellen, ob der Benutzer sich negativ auf durch eines der folgenden Probleme betroffen ist. Führen Sie die problemumgehung zur Verfügung gestellt (sofern vorhanden), um das Problem zu beheben.

4.  **Besuchen Sie die Microsoft Tech Community:** Der [Microsoft-Teams Tech-Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) bietet dedizierte Leerzeichen für Teams. Der Community Teams bietet eine Diskussionsliste, Blogbeiträge und Teams zentraler Ankündigungen. Sie können eine Frage oder vorherige Diskussionen für Lösungen auf Ihr Problem suchen.

5.  **Support von Microsoft:** Microsoft-Support erhalten Sie bei Problemen mit Teams online oder per Telefon. Informationen finden Sie unter [Unterstützung für Microsoft-Teams, Kontakt](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    Für Premier Kunden Support-Anforderungen durch Befolgen der Anleitung unter [Kontakt Support für Microsoft-Teams (Premier-Kunden)](https://support.microsoft.com/premier/contacts)initiiert werden können.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität                 | Beschreibung                                                                                                                                                                                                                                                                                                                                                                     | Trittfrequenz   | Team zugewiesen |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Anforderungen für Endpunkt    | Stellen Sie sicher, dass der Teams Endpunkt weiterhin alle erforderliche Software für Teams [erhalten die Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients)erfüllen.                                                                                                                                                                                       | Monatlich   |               |
| Endpunkt firewalls       | Verwalten Sie die entsprechenden Ausnahmen auf dem Endpunkt Firewall anhand der Informationen im Artikel [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) . Ihre Drittanbieter müssen bestimmte Richtlinien zum Verwalten der Ausschlüsse. Abonnieren Sie den [RSS-feed](https://support.office.com/en-us/o365ip/rss) Änderungen automatisch benachrichtigt werden sollen. | Bei Bedarf |               |
| Wi-Fi-Treiber            | Testen Sie und aktualisieren Sie die Wi-Fi-Treiber auf dem PC. Überprüfen Sie die Ergebnisse mithilfe von CQD ([Qualität überprüfen Handbuch für of Experience](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/CloudVoice-working/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)).                                                                                                                                                                                                                                                                   | Bei Bedarf |               |
| Endpunkt-Verwaltung      | Verwalten des Katalogs der unterstützten Endpunkten und Geräte (wie Headsets) Schnittstelle. Hersteller Verträge, Garantie, Verteilung, Replacement verwalten und Richtlinien zu reparieren.                                                                                                                                                                                                        | Monatlich   |               |
| Endpunkt-Problembehandlung | Problembehandlung bei Aufgaben kann einschließen. Überprüfen der Konnektivität, konsultieren die Liste der bekannten Probleme, Log sammeln, Analyse und Weiterleitung zu Support von Microsoft oder von Drittanbietern.                                                                                                                                                                                               | Bei Bedarf |               |

### <a name="references"></a>Verweise 

[URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips)

[Beziehen von Clients für Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients)

[Microsoft Teams in der Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Bekannte Probleme beim Microsoft-Teams](https://docs.microsoft.com/MicrosoftTeams/known-issues)

[Überprüfen der Integrität der Dienst für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/service-health)

[Kontaktieren des Office 365 Business-Supports - Administratorhilfe](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&rs=en-US&ad=US)

[Kontakt Premier](https://support.microsoft.com/premier/contacts)

[Videos des Teams für die Problembehandlung](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Verwalten von Teams

Nachdem der Dienst Microsoft-Teams bereitgestellt wurde, müssen Sie mehrere Aktivitäten zur Verwaltung ausführen. Der Bereich der Aktivitäten von der Verwaltung von Dienst und Einzelbenutzern für kapazitätsplanung und Bereitstellung Lizenzierung und Telefonnummern. In den folgenden Abschnitten werden einige der folgenden allgemeinen Verwaltungsaufgaben behandelt.

### <a name="service-administration"></a>Verwalten des Diensts

Der Dienst Teams hat mehrere Einstellungen, die gesamte Mandanten konfiguriert werden können.
Änderungen an den Einstellungen für Mandanten betreffen alle Benutzer, die für Teams aktiviert wurden. Eine ausführliche Übersicht über diese Einstellungen finden Sie unter [Microsoft-Teams Features in Office 365-Organisation zu aktivieren](https://docs.microsoft.com/microsoftteams/enable-features-office-365).

### <a name="user-administration"></a>Verwalten des

Zur Unterstützung der Benutzer eine Organisation eine beliebige Anzahl von Aufgaben im Zusammenhang mit erfordern möglicherweise – spezifischen Aufgaben von einer Organisation zur nächsten variieren. Schließlich müssen diese Aufgaben durch ein Supportteam verwaltet werden, die diesen betrieblichen Aufgaben zugewiesen wurde. Zur Unterstützung der Benutzer in Teams sind häufig die folgenden Aufgaben erforderlich.

#### <a name="general-tasks"></a>Allgemeine Aufgaben

[Verwalten des Benutzerzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)

#### <a name="common-tasks-for-phone-system"></a>Allgemeine Aufgaben für das Telefonsystem

[Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user).

[Zuweisen oder Ändern einer Notfalladresse für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Erstellen und Verwalten von Wählplänen](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

#### <a name="common-tasks-for-audio-conferencing"></a>Allgemeine Aufgaben für Audiokonferenzen

[Ändern der Einstellungen für eine Audiokonferenzbrücke](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge)

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/manage-the-audio-conferencing-settings-for-a-user)

[Zurücksetzen der Audiokonferenz-PIN für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/reset-the-audio-conferencing-pin-for-a-user)

### <a name="license-management"></a>Lizenzverwaltung

Wie Ihre Organisation wächst oder verringert wird, ist es wichtig, Lizenzierung für aktuelle und zukünftige Anforderungen zu planen. Ist base Teams-Lizenz, zusätzlich zur Lizenzierung für Cloud-Sprachfunktionen ([Telefonsystem](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system?ui=en-US&rs=en-US&ad=US) und [Audiokonferenzen](https://products.office.com/skype-for-business/audio-conferencing)).

Für Teams erfordern Telefonsystem Lizenzen Lizenzen [Aufrufen planen](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) . Plan Lizenzierung aufrufen, können Sie tätigen und Entgegennehmen von Anrufen nationalen und/oder internationale. Diese Pläne basieren auf verwendungs- und Minute Pools zugeordnet werden. Provisioning [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) , wird sichergestellt, dass Sie nie ausgeführt haben, nicht verfügbar ist.

Audiokonferenzen kann für tolled einwahlkonferenzen und nationalen Dial-Out-Konferenz-Dienste. Gebührenfreie einwahlkonferenzen oder Ausland Dial-Out-Szenarien möglicherweise führen Sie für die [Kommunikation haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) zusätzliche Gebühren anfallen erforderlich sind.

Communications haben können aufrufen planen und Audiokonferenzen Lizenzen ergänzen. Planen der Aufruf von Lizenzen und Kommunikation haben basieren auf Verwendung, und daher müssen überwacht und entsprechend für bereitgestellt werden.

Sie können den [PSTN-Verwendungsbericht](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) zur einfacheren Überwachen der Nutzung von Minuten planen aufrufen und Communications haben nutzen. Basierend auf den Ergebnissen dieser Aktivität, können Sie Ihre Lizenzierung entsprechend anpassen. In Kürze wird einen Bericht [PSTN Minute Pool](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) effektiver bei dieser Aufgabe unterstützen anbieten.

### <a name="telephone-number-management"></a>Telefon Nummer management

Es gibt zwei Methoden, um Zahlen in Teams zu erwerben: Sie können Telefonnummern in einen anderen Anbieter portieren, oder Sie können die Zahlen direkt aus Microsoft Nummern Inventar bereitstellen. [Erste](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)Rufnummern für Ihre Benutzer werden beide Methoden beschrieben.

Es besteht ein Grenzwert für den Zeitraum Telefonnummern, die Sie aus dem Microsoft Nummern Bestand bereitstellen können. Die Grenzwerte werden durch eine Reihe von Faktoren, die in [wie viele Rufnummern, die Sie abrufen können](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)beschriebenen bestimmt.
Die Grenzwerte für die hängt vom Typ von Zahlen –-gebührenfreie Service Zahlen, gebührenpflichtige Service Nummern und Nummern Abonnenten (Benutzer). Jeder verfügt über eine eigene Grenzwerte und muss separat verwaltet werden. Wenn Sie den Grenzwert abgelaufen sind (oder Sie haben den Grenzwert erreicht), können Sie auf den Grenzwert für eine Schrittweite anwenden. Dieser Prozess wird in der oben genannten Artikel beschrieben.

Unter Umständen bei eine Zahl steht nicht zur Verfügung, in einer Region bereitgestellt werden, auf dem Dienst verfügbar ist. Informationen über den Updateprozess für anfordernde Zahlen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Team erstellen (optional)

Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams. Wenn Sie eine genauere Kontrolle und [die Erstellung des neuen Teams einschränken](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions#permissions-to-create-teams) (und somit die Erstellung des neuen Office 365-Gruppen) haben möchten, können Sie die Gruppe erstellen und einen Satz von Administratoren Verwaltungsrechte delegieren. Wenn Ihre Organisation diese Option verfolgen möchte, finden Sie unter der Schritte in diesem Artikel ermöglicht den Benutzern, Anfragen zu senden, die von einer zugewiesenen Team verarbeitet werden.

<!--ENDOFSECTION-->

## <a name="dailyweeklymonthlyas-needed-tasks"></a>Täglich/wöchentlich/monatlich/bedarfsorientierte Aufgaben

| Aktivität                    | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                             | Trittfrequenz   | Team zugewiesen |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Verwalten des Diensts      | Verwaltung von Mandanten geltende Teams Einstellungen.                                                                                                                                                                                                                                                                                                                                                                           | Bei Bedarf |               |
| Verwalten des         | Verwaltung von benutzerbasierte Einstellungen und Lizenzierung in Teams.                                                                                                                                                                                                                                                                                                                                                           | Bei Bedarf |               |
| Lizenzverwaltung          | Planen von aktuellen und zukünftigen Anforderungen für die Benutzer- und Verbrauch-basierte Lizenzierung (plant aufrufen und Kommunikation haben) durch die Nutzung von [PSTN-Verwendungsbericht](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) und [Minute Pool PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) -Bericht. | Wöchentlich    |               |
| Telefon Nummer management | Verwalten Sie die Telefonnummern für künftiges Wachstum verfügbar, und passen Sie Inventar Ebenen entsprechend Ihren Anforderungen Organisationseinheiten.                                                                                                                                                                                                                                                                                                | Wöchentlich    |               |
| Team erstellen (optional)    | Überprüfen und Verarbeiten von Anforderungen für Team erstellen.                                                                                                                                                                                                                                                                                                                                                                          | Bei Bedarf |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>Quality of Experience überprüfen Guide
Qualität erleben Sie die Überprüfung Handbuch verfügt über eine Reihe von Aktivitäten, die Bewertung und-Wartung Anleitungen in wichtige Bereiche, die am stärksten zur Verbesserung der benutzerfreundlichkeit, wie in der folgenden Abbildung dargestellt.

![Die Schlüsselbereiche während einer QoS untersuchen erleben Sie die Überprüfung: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.] (media/plan-my-service-management-image2.png "Die Schlüsselbereiche während einer QoS untersuchen erleben Sie die Überprüfung: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.")

Ständig bewerten und Korrigieren von den in diesem Dokument beschriebenen Gebieten, können Sie ihre potenzielle Möglichkeit beeinträchtigen Benutzererlebnis reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

-   Unvollständige Firewall oder der Proxyserver-Konfiguration

-   Schlechte Wi-Fi-Abdeckung

-   Unzureichende Bandbreite

-   VPN

-   Verwenden von nicht optimierte oder integrierte Audiogeräten

-   Problematisch Subnetze oder Netzwerkgeräte

Der Anleitungen in im Handbuch für die Überprüfung von Quality Erfahrung behandelt Verwendung Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche beschrieben, mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die maximieren. Versucht, das Netzwerk zur Verbesserung der Audioqualität Optimierungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen. Nach dem benannt wird, sollten sie beginnen mit dem Inhalt im [Handbuch für die Qualität Experience-Überprüfung](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)vertraut machen.

<!--ENDOFSECTION-->