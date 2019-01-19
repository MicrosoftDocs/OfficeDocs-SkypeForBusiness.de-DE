---
title: Planen von dienstverwaltung und Qualität | Technische Bereitschaft
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Verwenden Sie diese Anleitung um kennen zu lernen die Anforderungen, die zum Bereitstellen und Verwalten von eine hohe Qualität Microsoft-Teams, Bereitstellung erforderlich sind.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59c881c6c40b8877fee46e3956970a0c305d0a4a
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349529"
---
![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft] (media/upgrade-banner-tech-readiness.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft")

Dieser Artikel ist Teil technische Bereitschaft Stufe des Ihrem Upgrade Weg, eine Aktivität, die gleichzeitig mit der User Readiness Phase ausgeführt werden. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
- [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
- [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>Plan für die Qualität

Wenn Sie Audio-, Video- oder Besprechungen bereitstellen, können Sie einige zusätzliche Schritte zur Optimierung Ihrer Umgebung für diese Funktionalität nutzen. Dieser Inhalt bietet eine Übersicht über die Anforderungen, die zum Bereitstellen und Verwalten von eine hohe Qualität Microsoft-Teams, Bereitstellung erforderlich sind. Sie können eine erfolgreiche Bereitstellung durch Planung für dienstverwaltung und die Qualität, vor der ersten Bereitstellung Pilot- oder Produktionsserverfarm sicherzustellen.

Die Anleitung ist in die folgenden Abschnitte unterteilt:

- Zunächst wird eine Übersicht über die Benutzeroberfläche und die wichtigsten Komponenten, die Qualität Ihrer innen-. Dadurch wird die Bereiche konzentrieren vor Onboarding zu Microsoft-Teams hervorgehoben.

- Zweitens Anleitungen erhält bei der Planung eines Modells Unterstützung zum Verwalten von Microsoft-Teams, vor der ersten Benutzer Pilot- oder Produktionsserverfarm Bereitstellung. Dieser Abschnitt beschreibt die Aufgaben, die in regelmäßigen Abständen Verwaltung eine qualitativ hochwertige Teams Bereitstellung ausgeführt werden müssen. Darüber hinaus werden in diesem Abschnitt Weitere Leitlinien Sie starten zu verstehen und operationalizing dieser Aufgaben verwenden können.

- Dritte, spezielle Anweisungen hilft bei der Planung Ihrer Netzwerk- und Endpunkte in Ihrer Organisation zur Unterstützung von Microsoft-Teams.

- Nächste Schritte werden schließlich mit Referenzen zu verwandten Inhalten zusammengefasst.

## <a name="key-technical-components-that-affect-user-experience"></a>Erleben Sie die wichtige technische Komponenten, die Einfluss auf Benutzer

In diesem Abschnitt werden die wichtigsten technischen Komponenten, die Benutzerinteraktion betreffen überprüft. Bevor die wichtigsten Komponenten überprüfen, ist es wichtig, dass Sie die benutzerfreundlichkeit und ihre Bedeutung in Ihrer Organisation Unternehmensziele realisieren verstehen. Sehen wir uns an, wie wir zunächst die Benutzeroberfläche definieren.

### <a name="user-experience-defined"></a>Benutzeroberfläche definiert

Geschäftlicher Ziele können realisiert werden bei der Bereitstellung von Microsoft-Teams, und wenn Benutzern Teams als Zusammenarbeit und Kommunikation ihrer kernlösung übernommen. Qualität kann eine positive Benutzer wünschen, ein Key-Attributs in treibende Verwendung und Akzeptanz sicherzustellen. Durch die Bereitstellung von hoher Qualität Dienst, der Personen Delights, Einzelpersonen und Teams Confidence erhalten und finden neue und innovative Wege zur Verwendung des Diensts, Geschäftsvorteile Laufwerk.

Erfahrung mit Teams des Benutzers besteht im Wesentlichen dieses – Ihre Gefühle auszudrücken und überlegen in Richtung des Diensts. Was trägt dies auf die Benutzeroberfläche? Es reicht von Benutzern zu wissen, wie und warum Sie Teams und integrieren es in ihrer täglichen Workflow außergewöhnliche Anrufqualität auftritt und zuverlässig, unabhängig davon, wo sie sind Verbindung hergestellt wird. Benutzerinteraktion ist sehr große Natur. Dieser Artikel befasst sich nur auf die technischen Elemente, die von Ihrer Organisation gesteuert werden können. Weitere Informationen zur benutzerbereitschaft finden Sie unter [Vorbereiten Ihrer Organisation für Teams](https://aka.ms/SkypeToTeams-UserReadiness).

Es werden spezifische Anforderungen für die Bereitstellung, die Benutzererlebnis übermitteln extrem wichtig sind – insbesondere wenn über die Cloud-VoIP-features in Teams. Es ist wichtig, Microsoft-Teams, als ein wesentlicher mit anderen Investitionen Kommunikation und Zusammenarbeit in Echtzeit Datenverkehr entsprechend Priorisierung zu behandeln. Der folgende Abschnitt bietet eine Übersicht über die wichtigsten Komponenten, die benutzerfreundlichkeit auswirken. In weiteren Abschnitten bieten wir Ihnen Anleitungen zum Starten der Planung, Bereitstellung und Verwaltung von die wichtigsten Komponenten, die Qualität umfassen.

### <a name="key-components-of-quality"></a>Hauptkomponenten von Qualität

Eine Organisation oder unterstützenden Partner zu Beginn der Planung für die drei wichtigsten Komponenten während der Phase technische Bereitschaft einer Bereitstellung Teams: service-Management, Netzwerk und Endpunkte. Die Kombination aus allen drei Bereichen ist unerlässlich für die Qualität des Benutzererlebnisses.

![Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt.] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt.")

#### <a name="service-management"></a>Service-management

Service-Management kann in zwei unterschiedlichen Kategorien der Verantwortung unterteilt werden:

- **Microsoft Verantwortung**. Microsoft ist verantwortlich für die Infrastrukturkomponenten, die Office 365-Dienst umfasst. Microsoft ist verantwortlich für Kunden, um sicherzustellen, dass alle ihre Benutzer eine Verbindung mit Teams mit eine zuverlässige und qualitativ hochwertige Erfahrung bereitgestellt.

- **Verantwortung Kunden**. Sie und Ihre Organisation die Verantwortung für die Verwaltung von verschiedenen Aspekten der Office 365-Dienst, lokalen Netzwerk und benutzerendpunkte. Office 365 neue IP-Adressen hinzugefügt werden, müssen Sie die entsprechenden Firewalls Kommunikation an die neue Endpunkte zur Vermeidung von Störung der Benutzer aktualisieren.

Ausführliche Anleitungen für Servicemanagement-Planung finden Sie unter [Planen der Service-Verwaltung](#plan-for-service-management).

#### <a name="network"></a>Netzwerk

In den meisten Unternehmen wurden Netzwerke anfänglich bietet Zugriff auf Daten und Anwendungen, die in ihren Rechenzentren befand. Cloud-basierte Anwendungen wie Office 365 erfordern Änderungen an dieser Netzwerke zur Unterstützung der neuen Zugriff und Daten Abläufe, die Teams erforderlich sind. Bevor Sie Benutzer in Ihrer Organisation für Teams aktivieren können, müssen Sie bewerten und das aktuelle Netzwerk zu optimieren. Dies ist besonders wichtig, wenn Cloud Voice-Funktionen nutzen.

Im herkömmliche Netzwerke müssen Benutzer einer Organisation Teams Zugriff auf die Umkreisnetzwerke durchlaufen. Viele Organisationen verfügen über Security-basierte Geräte wie Proxyserver und Firewalls VPNs die blockieren, beeinträchtigen oder einen nicht optimierte Pfad für den Netzwerkdatenverkehr angeben können.

Darüber hinaus müssen die internen Netzwerken Core optimierte und zukünftiges anzugebende ausreichende Kapazität und die Qualität für die Unterstützung von Teams Arbeitslast, einschließlich Real-Time Media sein. Sie können Bandbreite, die Planung, Wartung, und Optimierung, um sicherzustellen, dass Ihr Netzwerk bietet einen hohe Qualität und effizienten Pfad zu Office 365.

Ausführliche Hilfestellungen zur Netzwerk planen finden Sie unter [Planen für die Netzwerkqualität](#plan-for-network-quality).

#### <a name="endpoints"></a>Endpunkte

Microsoft-Teams, unterstützt eine Vielzahl von Endpunkten. Über PCs Tablets-Telefone können Sie Teams an einer beliebigen Stelle von praktisch jedem Gerät zugreifen.

Um Ihre Benutzer die beste Leistung zu bieten möglich ist, müssen Sie diese wichtige Aspekte berücksichtigen: Führen Sie die Endpunkte erfüllen die Teams Hardware und Software? Haben Sie Konfiguration und Optimierung der Endpunkte um Wi-Fi-Netzwerke zu unterstützen? Verwenden auf welchen Geräten Sie das tätigen und annehmen von Anrufen? Werden diese Geräte sind für Teams optimiert?

Ausführliche Hilfestellungen zur Planung der Endpunkt finden Sie unter [Planen für die Qualität des Endpunkts](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Planen der Service-management

Service-Management ist ein weites, der täglichen Vorgänge des Diensts Microsoft-Teams abdeckt, nachdem es bereitgestellt und für Benutzer aktiviert wurde. Der Teams Service umfasst Microsoft Office 365 und die Infrastrukturkomponenten, die lokal bereitgestellt haben (beispielsweise Netzwerk).

Das Konzept der Service-Management ist wahrscheinlich nicht für die meisten Organisationen ein neues Konzept. Sie haben möglicherweise bereits implementiert, Prozesse und Aufgaben, bei die vorhandene Dienste zugeordnet sind. Dies bedeutet, dass Sie wahrscheinlich was Servicelevel beim Service-Management heute zur Unterstützung von Microsoft-Teams, in der Zukunft planen erweitern können.

Service-Management umfasst alle Aktivitäten und Prozessen beteiligt sind Microsoft-Teams, Ende zum Verwalten. Wie bereits beschrieben einige Komponenten von Service-Management – der Infrastrukturkomponenten, die Office 365-Dienst selbst umfasst – Microsofts Verantwortung sind, während der Kunde verantwortlich für die Benutzer zum Verwalten der verschiedenen Aspekte der Teams, ist die Netzwerk- und Endpunkte, die sie bereitstellen. In diesem Abschnitt des Dokuments konzentriert sich auf der Verantwortung des Kunden aus der Sicht Management Service.

![Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf dienstverwaltung.] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf dienstverwaltung.")

### <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

**Welche**, **wer**und **wie** sind drei wichtige Fragen, die bei dienstverwaltung beantwortet werden müssen.

Im [Betriebshandbuch](1-drive-value-operate-my-service.md) können Sie alle drei dieser Fragen zu beheben. Das Handbuch enthält eine Liste der Aktivitäten aus, die für einzelne täglich, wöchentlich, monatlich und bei Bedarf ausgeführt werden. Diese Aktivitäten und Aufgaben sind äußerst wichtig für die Verwaltung von Bereitstellungsproblemen Teams hoher Qualität. Bestimmen, die zum Ausführen bestimmter Aktivitäten in Service-Management zuständig sind, ist ein wichtiger Aspekt der Planung, die Sie einem frühen Zeitpunkt in der [Phase Planung](upgrade-enlist-stakeholders.md) sicherstellen eine erfolgreiche Bereitstellung ausführen müssen. Nachdem Sie die Aufgaben und Aktivitäten berechnet haben, müssen sie verstehen und dahinter die Gruppen oder Personen, die Sie ihnen zuweisen. Im Betriebshandbuch bietet Kenntnisse und Richtlinien zum Durchführen der Aufgaben und/oder zu externen Inhalten verweist.

### <a name="operational-role-mapping"></a>Betriebliche Rolle Zuordnung

Planen der Verwaltung von Service von einem frühen Zeitpunkt ist wichtigen Meilenstein, da der Betriebsphase beginnt, wenn die erste Pilotbenutzer aktiviert sind. Des Projektteams überprüfen, und bestätigen Sie auf der Aufgaben und Aktivitäten, die erforderlich sind, identifizieren das Team, das für jeden Vorgang betriebliche zuständig ist und klicken Sie dann erhalten Sie eine Zusage und Abnahme pro jeweiligen Team.

Nach Abnahme abgeschlossen ist, müssen Sie das zuständige Team starten operationalizing diese Rollen und Verantwortlichkeiten von. Dies kann enthalten, Schulung und Bereitschaft und Aktualisieren des Modells Personalplanung oder sicherstellen, dass externe Partner übermitteln können.

Rollen zuordnen, wie Sie Ihr [Projektteam](upgrade-enlist-stakeholders.md) sammeln kann alle Teams Starten ihrer betriebsbezogenen Aufgaben während der Pilotphase, und lernen Sie Vorgänge, und stellen Sie sicher, dass Sie nach dem Starten der bereitstellungs abgeschlossen ist.

Im Betriebshandbuch enthält eine Liste der allgemeinen Aufgaben, typische Rollen, die in den meisten Szenarien gültig sein sollte zugeordnet sind. Sie müssen diese Aufgaben funktioniert für Ihre Organisation anpassen.

### <a name="the-quality-champion-role"></a>Die Qualität Champion-Rolle

Eine Gruppe oder einzelne Anforderungen für die Qualität in allen Organisationen verantwortlich sein. Dies ist die wichtigste Funktion im Service-Management. Die Qualität Champion ist eine Kundenrolle, die an eine Person oder Gruppe, die über ihre Benutzer wünschen engagierten ist zugewiesen ist. Diese Rolle erfordert die Fähigkeiten Trends in der Umgebung und der Unterstützung durch die anderen Teams Remediation Laufwerk entwickelt erkennen. Der beste Kandidaten für die Qualität Champion ist in der Regel der Customer Service Besitzer, die – je nach Größe und Komplexität der Organisation – eine beliebige Person oder Gruppe, die zur Benutzerinteraktion engagierten ist werden konnte.

Die Qualität Champion nutzt vorhandenen Tools und dokumentierte Prozessen, wie etwa aufrufen Quality Dashboard (CQD) und eine Anleitung Qualität erleben Sie die Überprüfung zum Überwachen der Benutzer wünschen, identifizieren Qualität Trends und-Wartung Laufwerk bei Bedarf. Die Qualität Champion funktioniert mit den jeweiligen Teams auf Laufwerk Remediation Aktionen, einem Lenkungsausschuss-Berichte auf ihren Status und offener Probleme.

Die Aufgaben und Aktivitäten im Zusammenhang mit der Rolle wurden im Betriebshandbuch dokumentiert. Diese Rolle sollte bei der [Planung der Stufe](https://aka.ms/SkypeToTeams-Plan)zugewiesen werden. Ein wichtiger Schritt in der Rolle der Qualität Champion operationalizing wird die Rolle und sicherstellen, dass die erforderlichen Kenntnisse, dass die erforderlichen Komponenten direkte Zustellung über die Aufgaben sind erlangen. Eine wichtige Aufgabe für diese Rolle ist eine regelmäßige Überprüfung der Qualität Erfahrung ausgeführt.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Einführung in die im Handbuch für die Überprüfung von Quality Erfahrung

Qualität erleben Sie die Überprüfung Handbuch verfügt über eine Reihe von Aktivitäten, die bewerten und-Wartung Anleitungen in wichtige Bereiche, die am stärksten zur Verbesserung der benutzerfreundlichkeit, wie in der folgenden Abbildung dargestellt.

![Ein Diagramm zur Veranschaulichung der wichtige Bereiche, die während der Überprüfung Erfahrung Qualität untersucht wird.] (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Ein Diagramm zur Veranschaulichung der wichtige Bereiche, die während der Überprüfung Erfahrung Qualität untersucht wird.")

Ständig bewerten und Korrigieren von den in diesem Dokument beschriebenen Gebieten, können Sie ihre potenzielle Möglichkeit beeinträchtigen Benutzererlebnis reduziert. Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:

- Unvollständige Firewall oder der Proxyserver-Konfiguration

- Schlechte Wi-Fi-Abdeckung

- Unzureichende Bandbreite

- VPN

- Verwenden von nicht optimierte oder integrierte Audiogeräten

- Problematisch Subnetze oder Netzwerkgeräte

Der Anleitungen in im Handbuch für die Überprüfung von Quality Erfahrung behandelt Verwendung Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche beschrieben, mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die maximieren. Versucht, das Netzwerk zur Verbesserung der Audioqualität Optimierungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.

Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen. Nach dem benannt wird, sollten sie beginnen mit dem Inhalt im Handbuch für die Qualität Erfahrung-Überprüfung vertraut machen.

Im Handbuch für die Überprüfung von Quality Erfahrung finden Sie [hier](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Planen der Netzwerkqualität

Planen der Netzwerkqualität wird der Fokus für den folgenden Abschnitt sein.

![Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf das Netzwerk.] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf das Netzwerk.")

Wie bereits erwähnt, Planung für Netzwerkqualität vor Onboarding zu Microsoft-Teams, wichtig ist. Weitere Hinweise für Bereitschaft des Netzwerks finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams](prepare-network.md).

In den meisten Organisationen können Netzwerke verwaltete und nicht verwaltete Netzwerken umfassen.

Verwaltete Netzwerke sind Komponenten der Netzwerkinfrastruktur, der eine Organisation über direkte Steuerelement hat. Daher müssen verwaltete Netzwerken einen direkten Einfluss auf die Qualität, die in Echtzeit Datenverkehr Arbeitslasten bereitgestellt werden kann.

Umgekehrt sind nicht verwaltete Netzwerken Segmente des Netzwerks, dass ein Kunde in der Steuerelement oder keine Kontrolle über begrenzten Netzwerkressourcen.

Internet-Verbindungen zwischen der Organisation und Office 365 sind Netzwerken, in dem ein Kunde Steuerelement begrenzten Netzwerkressourcen. Die Netzwerke von einem Internetdienstanbieter verwaltet werden, aber Organisationen sollten in der Lage, die Qualität des Netzwerks beeinflussen, durch die Aktualisierung ihrer Bandbreite, die für die Route-Optimierungen durch oder – erfolglos – Internetdienstanbieter wechseln.

Private Netzwerke oder Netzwerke in Hotels oder Cafés sind Beispiele für Netzwerke beschrieben, in dem ein Kunde kein Steuerelement hat.

In den folgenden Abschnitten liegt der Schwerpunkt auf die Qualität Anforderungen von verwalteten Netzwerken.

### <a name="key-network-planning-areas"></a>Wichtige Bereiche für netzwerkplanung

In den folgenden Abschnitten Schwerpunkt liegt auf die wichtigsten Aspekte für die Übermittlung von einem Netzwerk hohe Qualität.

> [!NOTE]
> Viele Netzwerke weiterentwickelt über einen Zeitraum von Upgrades, Erweiterung oder anderen geschäftlichen Anforderungen. Stellen Sie sicher, dass Sie betriebliche Prozesse zum Verwalten dieser Bereiche als Teil Ihrer Service-Management-Planung verfügen.

#### <a name="bandwidth"></a>Bandbreite

Planen der Bandbreite ist ein wichtiger Aspekt der Aktivität Bereitschaft des Netzwerks. Sicherstellen, dass genügend für die Microsoft-Teams Arbeitslasten Bandbreite ist zwingend erforderlich. Um die richtige Größe einem vorhandenen Netzwerk können, müssen Sie verstehen, was derzeit, die aktuelle Auslastung bereitgestellt hat und – letztlich – die verbleibenden verfügbare Bandbreite.

Um die aktuelle Auslastung messen, müssen Sie das Netzwerk überwachen. Diese Messung kann dann als Ausgangspunkt für die Planung der Bandbreite verwendet werden. Darüber hinaus sollte das Netzwerk ständig überwacht werden, während der Bereitstellung und nach der Bereitstellung, um sicherzustellen, dass das Netzwerk ausreichend bereitgestellt ist.

> [!NOTE]
> Bei dem die Netzwerkauslastung Überwachung, ist es wichtig zu vermeiden der Verwendung von Durchschnittswerte über den Tag. Diese Durchschnittswerte können nicht Core Stunden enthalten, die das Ergebnis skew. Durchschnittswerte können Spitzenzeiten ausblenden und eine zugrunde liegende Problem maskieren.

Der [Planner Netzwerk](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) können Sie bestimmen und Organisieren netzwerkanforderungen für die Bereitstellung in nur wenigen Schritten. Mithilfe des Tools zum Erfassen von Netzwerkdetails und Cloud Voicemail Nutzung Ihrer Organisation erhalten Sie eine ungefähre Berechnung der die netzwerkanforderungen Sie benötigen für Ihre Cloud-VoIP-Bereitstellung verwalten und diese Details für die berichterstellung exportieren sowie Bereiche anzeigen für die weiteren Untersuchung und nächste Schritte.

#### <a name="quality-of-service-qos"></a>Dienstqualität (QoS)

QoS sollte alle Segmente des verwalteten Netzwerks, selbst Netzwerke implementiert werden, die für die Bandbreite angemessen bereitgestellt wurden. Im letzteren Fall fungiert QoS als eine Risikominderung bei einem unvorhergesehenen Netzwerklast. Wenn QoS implementiert wird, wird Sprachdatenverkehr priorisiert werden, damit diese Ereignisse unvorhergesehene Qualität keine Auswirkung auf.

Eine QoS-Implementierung sollte im Netzwerk, aus der Endpunkt bis hin zu den Ausgang Punkt und von der Ausgang Punkt zurück an den Endpunkt umfassen. Dadurch wird sichergestellt, dass VoIP-Datenverkehr für die eine Priorität in beide Richtungen zugewiesen ist. QoS für beide verkabelt implementiert werden sollten und Wi-Fi-Netzwerke.

Für die Implementierung von QoS in Ihrem Netzwerk, unterstützen die folgende Hinweise [Quality of Service in Microsoft-Teams](qos-in-teams.md)

#### <a name="proxy-servers"></a>Proxy-Server

Viele Organisationen Datenverkehr für das Internet als ein Sicherheitsrisiko anzeigen und diese dieses Risiko von monitoring sowie zum Auswerten von Datenverkehr an den Ausgang Punkten im Netzwerk minimieren. Proxy-Server sind eine Klasse von Geräten, die bereitgestellt werden können, um diese Anforderung erfüllen.

Beim Ausführen einer Paketinspektion oder Änderung an der Nutzlast, kann ein Proxyserver Problemen führen. Dies kann führen Setupfehler, Verworfene Anrufe und die Qualität der Anrufe schlechter Qualität aufrufen. Real-Time Media erzwungen wird, um einen Proxy-Server zu durchlaufen, wird der medienstapel in Teams erzwungen TCP, Failback der Qualität weiter verringern kann. UDP ist immer über TCP bevorzugte.

Darüber hinaus ein Proxyserver möglicherweise nicht so gestaltet werden, von Office 365 und insbesondere die Arbeitslasten Microsoft-Teams, die zusätzliche Last zu bewältigen – einschließlich Real-Time Media.

Microsoft empfiehlt aufgrund der potenzielle Probleme, die ein Proxyserver einführen kann, und diese zusätzliche Kapazität bedenken, Proxyserver und Herstellen einer direkten Verbindungs zu Office 365.

Zum Umgehen des Proxyservers erforderliche Konfiguration variiert je nach Hersteller, aber normalerweise häufige Ansatz umfasst das Aktualisieren der Proxy AutoConfig (PAC)-Datei. Die PAC-Datei ist eine Konfigurationsdatei, die beschreibt, welche Datenverkehr über den Proxy wird und welche Datenverkehr hierbei umgangen wird.

Manche Serverhersteller Proxy enthalten, dass ein automatisierter Prozess zur Sicherstellung der Konfigurations auf dem aktuellen Stand ist. Wenn Ihr Hersteller dieser automatische Prozess zur Verfügung steht, können Sie eine aktualisierte Datei PAC aus herunterladen <https://aka.ms/o365proxies>.

[Proxyserver für Skype für Unternehmen Online und Teams](/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Firewalls

Sicherstellen, dass die richtigen Ports und Protokolle für alle Office 365 IP-Adressen und URLs geöffnet sind ist erforderlich, um Zugriff auf Microsoft-Teams. Es ist außerdem für eine hohe Qualität Bereitstellung entscheidend. Einfach tätigen eines Anrufs oder teilnehmen an einer Telefonkonferenz ist nicht ausreichend, um sicherzustellen, dass die Firewall ordnungsgemäß konfiguriert ist.

Wenn nur TCP an der Firewall geöffnet wird, wird die Sitzung eingerichtet werden, sondern der bevorzugte Transport (UDP) wird nicht ausgehandelt werden. TCP und UDP sind erforderlich, um auf die Firewall, bietet die beste benutzerumgebung geöffnet sein.

Aufgrund seiner Natur dynamische TCP ist nicht für Real-Time Media bevorzugte und wird nur als einen Failback Netzwerktransport für Microsoft-Teams, bereitgestellt. Mit TCP Wenn Paket Verzögerung oder Verlust, müssen die Pakete erneut übertragen werden, bis sie bestätigt sind. Dies kann in Paketen Media führen, die nicht mehr mit rechtzeitige Bereitstellung von aktuellen Media-Pakete konkurrieren relevant sind. Der Client des Benutzers Teams versucht, Audio Dehnen und akustische Artefakte je nach netzwerkbedingungen erzeugen kann. Mit den Mehraufwand TCP wechseln auf benutzerfreundlich eine allgemein akzeptierte Erfahrung. Aus diesem Grund ist der statusfreie Netzwerktransport UDP erforderlich.

Vollständige Anleitung zum Öffnen der Firewalls für Microsoft-Teams, wird im Artikel [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) bereitgestellt.

Nachdem die Firewall geöffnet ist, können, verwenden Sie das [Tool zur Bewertung der Microsoft Network](https://www.microsoft.com/download/details.aspx?id=53885) zum Überprüfen der Konnektivität für Cloud-Sprachfunktionen.

> [!IMPORTANT]
> Die Microsoft Office 365 IP-Adressen und URLs werden über einen Zeitraum geändert. Im Rahmen der Service Management-Planung ist es wichtig, um sicherzustellen, dass ein Prozess, der betrieblichen vorhanden ist und eine Gruppe ist verantwortlich für die [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips) überwachen, und stellen Sie Updates entsprechend.

#### <a name="local-internet-egress"></a>Lokale Internet Ausgang

Viele Netzwerke wurden entwickelt, verwenden Sie einen Hub- and -spoke-Topologie. In dieser Topologie durchläuft Datenverkehr im Internet in der Regel das WAN an einem zentralen Datencenter bevor (Egresses) mit dem Internet herausstellt. Dies erfolgt häufig, um Sicherheit Netzwerkgeräte mit dem Ziel der Reduzierung der Gesamtkosten zentralisieren.

Back-Leinen zu lösen-Datenverkehr über das WAN nimmt die Wartezeit und wirkt sich negativ auf die Qualität und die Benutzeroberfläche. Da Microsoft-Teams, auf Microsoft Netzwerk für große globale ausgeführt wird, ist häufig ein Speicherort im Netzwerk Peers in der Nähe der Benutzer. Ein Benutzer in den meisten Fällen erhalten eine bessere Leistung so bald wie möglich egressing aus einer lokalen Internet Punkt erreicht bald ihrem Standort und unsere optimiert, VoIP Netzwerk an. Für einige Arbeitslasten-DNS-Anforderungen werden verwendet, um Datenverkehr zu senden, die am nächsten gelegenen Front-End-Server. In solchen Fällen ist es wichtig, dass es bei der Verwendung einer lokalen Austritt mit lokalen DNS-Auflösung gepaart ist.

Optimieren des Netzwerkpfades zur globalen Microsoft Netzwerk wird die Leistung verbessert und letztlich am besten für Benutzer bereitzustellen. Weitere Informationen finden Sie im Blogbeitrag [erste bewährte Konnektivität und Leistung in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

VPNs bieten eine wertvolle Service für viele Organisationen. Leider sie in der Regel nicht entwickelt und Real-Time Media-Unterstützung konfiguriert. Einige VPNs möglicherweise auch nicht UDP unterstützt werden. VPNs stellen auch eine zusätzliche Sicherheitsebene Verschlüsselung auf der Basis bereits verschlüsselt Mediendatenverkehr vor. Darüber hinaus Konnektivität mit dem Dienst Microsoft-Teams, effiziente aufgrund haarstrich Verankern-Datenverkehr über ein VPN-Gerät möglicherweise nicht. Darüber hinaus sind sie unbedingt aus Sicht der Kapazität unterstützt nicht die erwarteten Lasten aufzunehmen, die Teams erforderlich ist.

Es wird empfohlen, um einen alternativen Pfad bereitzustellen, der das VPN für Teams Datenverkehr umgeht. Dies wird auch als Split-Tunnel VPN bezeichnet. Split-tunneling bedeutet, dass dieser Datenverkehr für Office 365 durchlaufen wird nicht das VPN jedoch direkt an den Office 365. Diese Änderung haben eine positive Auswirkung auf die Qualität, sondern bietet auch den sekundären Vorteil Last aus VPN-Geräte und des Netzwerks der Organisation verringert.

Um ein Split-Tunnel zu implementieren, wenden Sie sich an den Anbieter für die Konfigurationsdetails für VPN.

#### <a name="wi-fi"></a>Wi-Fi

Wi-Fi-Netzwerke werden wie auch VPN nicht notwendigerweise entwickelt oder Real Time Media-Unterstützung konfiguriert. Planen von und/oder optimieren, ist ein Wi-Fi-Netzwerk zur Unterstützung von Teams ein wichtiger Aspekt für eine Bereitstellung Qualität.

Es gibt mehrere Faktoren, die ins Spiel für ein WLAN Netzwerk zu optimieren.

- Implementieren von QoS oder Wi-Fi Multimedia (WMM), um sicherzustellen, Mediendatenverkehr wird erste priorisiert entsprechend die Wi-Fi-Netzwerke.

- Planung und Optimierung der W-Fi Bereichen und Access zeigen Platzierung. Der Bereich mit 2,4 GHz möglicherweise eine angemessene wünschen, abhängig davon, wie Access Point bieten, jedoch Zugriffspunkte unterliegen häufig durch andere Consumer-Geräte, die in diesem Bereich verwendet werden. Bereich von 5 GHz erfordert weitere Zugriffspunkte zum Abrufen der ausreichenden Abdeckung jedoch ist für Real-Time Media aufgrund ihrer Dichte Bereich besser geeignet sind. Endpunkte müssen auch diesem Bereich unterstützen und nutzen Sie diese Bereiche entsprechend konfiguriert werden.

- Wenn dual-Band Wi-Fi-Netzwerke bereitgestellt werden, sollten Sie die Steuerung Band implementieren. Band Steuerung ist eine Technik implementiert Wi-Fi-Anbieter, Dual-Band-Clients für die Verwendung von 5 Ghz-Bereich zu beeinflussen.

- DDE-Kanal Überlappung – Wenn Zugriffspunkte im gleichen Kanal zu nahe beieinander können dazu führen, dass Signal Überlappung und versehentlich konkurrieren, wodurch eine schlechte Erfahrung für den Benutzer. Sicherstellen Sie, dass Zugriffspunkt, die nebeneinander auf Kanäle als nicht überlappen.

Jeder Hersteller drahtlosen verfügt über eine eigene Empfehlungen für die Bereitstellung von WLAN-Lösung. Es wird empfohlen, dass Sie den Hersteller für spezifische Leitfäden anzusehen.

### <a name="network-readiness-assessment"></a>Bewertung der Netzwerkbereitschaft.

Webpart bereitschaftsaktivitäten Netzwerk umfasst eine Bewertung Netzwerk. Nachdem Sie die Planung und Konfiguration abgeschlossen haben, kann die Bewertung Sie die Qualität des Netzwerks vor integrierte Benutzer zu verstehen und einen Basisplan auf Microsoft-Teams, gewähren. Die Bewertungsergebnisse auch helfen Ihnen beim Identifizieren und priorisieren Remediation-Maßnahmen vor dem Aktivieren von Benutzern für Teams.

Die Netzwerk-Bewertung sollte auf beide verkabelt ausgeführt werden, und Wi-Fi-Netzwerke für alle Gebäude, die für aktiviert ist, sind VoIP-Funktionen in Teams cloud.

Die Netzwerk-Bewertung kann mithilfe von Microsoft-Partner, Tools von Drittanbietern oder das [Tool zur Bewertung Microsoft-Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885)ausgeführt werden. Wir auch bieten weitere Anweisungen zum Ausführen der Bewertung, verwenden das Microsoft-Netzwerk-Assessment-Tool als Teil des Bereitschaft der Anleitung [hier](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>Plan für die Qualität der Endpunkt

Wie Sie aus der folgenden Abbildung sehen können, sind Endpunkte als wichtiger Baustein eine hohe Qualität Erfahrung für Benutzer bereitzustellen.

![Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagramm zur Veranschaulichung der drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.")

Microsoft-Teams, Endpunkte können auf vielen Geräten, einschließlich PCs, Macs, Tablets und mobilen Geräten ausführen. Teil der Erfahrung umfasst nicht nur das Gerät, aber wie ein Benutzer auf das Gerät verbindet – beispielsweise mithilfe des Geräts integrierten Mikrofon/Lautsprecher, Ohrstöpsel oder eine optimierte Kopfhörer. Mithilfe einer optimierten Kopfhörer kann die gesamten Benutzeroberfläche erweitern.

Die folgende Anleitung für die Planung der Endpunkt helfen Ihnen beim sicherstellen, dass Ihre Organisation eine erfolgreiche Onboarding Erfahrung mit Teams verfügt.

### <a name="endpoint-capability"></a>Endpunkt-Funktion

Der erste Teil der Planung ist, um sicherzustellen, dass alle PCs und andere Geräte in Ihrer Organisation Microsoft-Teams, ausführen können. Dieser Schritt umfasst nicht nur die hardwareanforderungen betrachten, aber auch zu verstehen, was der PC im Hintergrund Aufgaben verwendet wird. Viele Organisationen führen Sie andere Software, einschließlich Eindringungserkennungssysteme und Antischadsoftware, die die Leistung des base eines Geräts auswirken kann.

Microsoft-Teams, hat Clients verfügbaren Web, desktop (Windows und Mac) und Mobil (Android-, IOS- und Windows Mobile). Informationen zu den softwareanforderungen für jede Plattform finden Sie unter [Get-Clients für Microsoft-Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Endpunkt firewalls

Mithilfe der clientseitigen Firewalls können eine erhebliche Auswirkungen Benutzerinteraktion haben. Mithilfe der clientseitigen Firewalls können die Anrufqualität zusätzlich zu verhindern, dass einen Anruf aufgebaut wird beeinflussen. Konfigurieren Sie die entsprechenden Ausnahmen auf der Grundlage der Informationen in [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips)Clientfirewall. Ihre Drittanbieter müssen spezifische Leitfäden zum die Ausnahmen zu erstellen.

> [!NOTE]
> Microsoft-Teams, wird automatisch die Windows-Firewall mit einer geeigneten Firewallkonfiguration aktualisiert.

### <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi Empfehlungen für Endpunkte

Planung und Bereitstellung einer optimierten Wi-Fi-Netzwerk zur Unterstützung von Real-Time Arbeitslasten in Microsoft-Teams, erfordern erhebliche Planung. Die folgenden Abschnitte enthalten einige allgemeine Richtlinien, die Sie einige häufige Probleme zu vermeiden, bei der Planung für Endpunkte helfen kann.

#### <a name="wi-fi-drivers"></a>Wi-Fi-Treiber

Einige Wi-Fi-Treiber können problematisch sein. Als Beispiel möglicherweise ein Treiber sehr aggressive roaming-Verhaltens zwischen Zugriffspunkten, verursacht schlechter Anrufqualität. Dies ist keine allgemeine Sache, aber es ist wichtig, um sicherzustellen, dass Wi-Fi-Treiber auf dem PC aktualisiert und vor der Bereitstellung getestet wurden.

#### <a name="wi-fi-bands"></a>Wi-Fi-Bereichen

Es gibt hauptsächlich zwei Arten von Bereichen in Wi-Fi modernen Geräte, 2,4 GHz und 5,0 GHz verwendet. Wenn Ihre Organisation die beiden Bereichen bereitstellt, sollten Sie Ihre Einstellungen für Treiber, um die 5,0 GHz Band bevorzugen konfigurieren. Dieses Band ist viel dichter im Hinblick auf den Durchsatz und von der Störungen gesehen im Band mit 2,4 GHz kleiner betroffen waren. Diese Empfehlung wird davon ausgegangen, dass Sie ordnungsgemäß das 5,0 GHz Netzwerk Band optimiert haben.

#### <a name="wi-fi-radio-type"></a>Wi-Fi Radio-Typ

Planen von Geräten, die die neueren Wi-Fi Radio Typen unterstützen. Sie können eine sehr gute Wi-Fi Leistung erhalten, wenn Sie die 802.11ac nutzen oder höher auf den Geräten, die Sie bereitstellen.

#### <a name="wireless-avoidance"></a>Drahtlose Vermeidung

Manche Organisationen möchten Wi-Fi ganz zu vermeiden. In einigen Fällen wird dieser Anleitung über eine Empfehlung an Benutzer, um eine direkte Verbindung mit einem verkabelten Netzwerk bereitgestellt. In einigen Fällen kann die Reihenfolge der Bindung die drahtlose Verbindung bevorzugte haben und weiterhin, diese Verbindung verwenden, obwohl der PC verbunden ist, die eine drahtgebundene Verbindung verwenden. Um dieses unerwünschte Verhalten zu vermeiden, konfigurieren Sie die Bindungsreihenfolge für dieses Szenario zu vermeiden.

#### <a name="80211-power-save-protocol"></a>802.11 Power Protokoll speichern

Wenn Ihre Organisation drahtlosen Zugriffspunkte verwendet oder Router, die die 802.11 Leistungsfähigkeit nicht unterstützen Protokoll speichern, können Sie Verworfene Anrufe oder Anrufe schlechter Qualität Qualität in Microsoft-Teams, die auf Windows-Geräten ausgeführt auftreten. Ist es nicht möglich, Ihre drahtlosen Zugriffspunkt oder Router zu aktualisieren, sollten Sie Windows Power Planen der Einstellungen auf Geräten aktualisieren, die auf Batterie ausgeführt. Weitere Details und Konfiguration Leitlinien wird in der folgenden [Artikel unterstützen](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)bereitgestellt.

### <a name="devices-for-teams"></a>Geräte für Teams

Microsoft-Teams können für Besprechungen oder als Telefonsystem verwendet werden. Wenn Sie diese Features verwenden, spielt Schnittstellengerät für Teams verwendet wird eine wichtige Rolle, die Benutzeroberfläche.

Verwenden eine integrierte PC-Lautsprecher und ein Mikrofon mag für den Benutzer akzeptable, diese Konfiguration hat. Aber in der Regel werden nicht die Geräte für Noise Abbruch optimiert und jede Art von Umgebung Noise kann wirken sich downstream auf anderen auf den Anruf. Nutzen für diese Szenarien optimierte Geräte können Sie eine hohe Qualität Erfahrung sicherstellen.

Jedes Gerät muss die Anforderungen Ihrer Benutzer. Sie müssen auf Geräten wie Headsets für die verschiedenen Rollen anpassen und Anwendungsfälle in Ihrer Organisation. Eine Rolle-Geräte-Zuordnung Übung sollte als Teil des Planungsprozesses abgeschlossen werden.

Nachdem Sie die Geräte ausgewählt haben, können Sie diese in den Pilottest Plan für die endgültige Überprüfung. Optimal nutzen Umfragen während des Pilotprojekts zum Sammeln von Feedback, um Ihre Strategie für die Geräte stellen Sie sicher ist.

Zu diesem Zeitpunkt sollten mithilfe von Audiogeräte, die über die Skype für Business Zertifizierungsprogramm zertifiziert wurden. Rahmen dieses Programms zertifizierte Geräte finden Sie in den Katalog für [USB-Geräte zertifiziert für Skype für Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) Solutions.

Weitere Informationen finden Sie unter [Clients und-Geräten - Bereitschaft Workshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Clientupdates

Einer der wichtigsten Vorteile von Microsoft-Teams ist, dass der Client automatisch auf dem aktuellen Stand ist. Die Clients auf dem PC und Mac werden aktualisiert, mit einem Hintergrund, die für neue Builds überprüft und den neuen Client heruntergeladen, wenn die app im Leerlauf befindet. Die Client-Download-Größe beträgt ungefähr 100 MB.

Eine Organisation verfügen keines Steuerelement oder den Zugriff auf eine richtlinieneinstellung des Aktualisierungsvorgangs verwalten. Um das Risiko eines Problems zu verringern, die in einem neueren Build ermittelt werden kann, wird die letzte funktionierende Version auf den Endpunkt gespeichert. Liegt ein Problem mit einen neuen Build, kann der Dienst Microsoft-Teams, automatisch den Endpunkt auf die vorherige Version wiederherstellen.

## <a name="next-steps-and-references"></a>Nächste Schritte und Referenzen

Die folgende Tabelle enthält eine Zusammenfassung der Planungsaktivitäten mit Links zu verwandten Inhalten.

| Bereich | Beschreibung | Verweise |
|---|---|---|
| Planen der Service-management | Eine betriebsbereite Rolle Zuordnung Übung durchführen <br/> Genehmigung von verantwortlich teams <br/> Rolle Bereitschaft | [Betriebshandbuch](1-drive-value-operate-my-service.md) |
| | Benennen Sie die Qualität Champion(s) <br/> Belohnungen Bereitschaft Qualität| [Hier erfahren Sie, CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Handbuch für die Qualität Experience-Überprüfung](https://aka.ms/qerguide) |
| | Installieren von Vorlagen Qualität Erfahrung überprüfen <br/> Hochladen einer Datei zum Erstellen von | [QERLite Vorlagen](https://aka.ms/qertemplates) <br/> [Informationen zum Erstellen von hochladen](turning-on-and-using-call-quality-dashboard.md)|
| Planen der Netzwerkqualität | Führen Sie die Netzwerk-Planner | [Netzwerk-Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implementieren von QoS | [Quality of Service in Microsoft-Teams](qos-in-teams.md) |
| | Umgehen der Proxy-Server | [Proxy-Anweisungen](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implementieren von Split-Tunnel VPN | [VPN-Split Tunnel Anleitungen](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimieren der Leistung von Wi-Fi-Netzwerken für Real-Time media | Wenden Sie sich an von Drittanbietern |
| | Implementieren von lokalen Internet Ausgang | [Lokale Internet Ausgang](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementieren der Netzwerkkonnektivität <br/> Überprüfen der Netzwerkkonnektivität | [Office 365-URLs und IP-Adressen](https://aka.ms/o365ips) |
| | | [Tool zur Bewertung der Netzwerk](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Führen Sie Netzwerk-Bewertung | [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Plan für die Qualität der Endpunkt | Aktualisieren der Endpunkt firewalls | [Office 365-URLs und IP-Adressen](https://aka.ms/o365ips) |
| | Überprüfen Sie die erforderliche software | [Beziehen von Clients für Microsoft Teams](get-clients.md) |
| | Implementieren der Endpunkt Wi-Fi-Empfehlungen | Wenden Sie sich an von Drittanbietern |
| | Durchführen von Persona zum Zuordnen von Geräten <br/> Bereitstellen von Geräten und testen diese | [Client- und Gerätefunktionen - Bereitschaft Workshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Gerät-Katalog](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Nachdem Sie die Planung abgeschlossen haben, fahren Sie fort mit dem nächsten Schritt: [Vorbereiten der Umgebung für Teams](https://aka.ms/SkypeToTeams-TechnicalReadiness).