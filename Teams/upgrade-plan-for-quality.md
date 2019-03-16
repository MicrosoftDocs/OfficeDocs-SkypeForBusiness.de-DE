---
title: Planen von dienstverwaltung und Qualität | Technische Bereitschaft
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Verwenden Sie diese Anleitung um kennen zu lernen die Anforderungen, die zum Bereitstellen und Verwalten von eine hohe Qualität Microsoft-Teams, Bereitstellung erforderlich sind.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45dafd29302dc26dae80461a7c4082c6a73469c8
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649516"
---
![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft] (media/upgrade-banner-tech-readiness.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft")

Dieser Artikel ist Teil technische Bereitschaft Stufe des Ihrem Upgrade Weg, eine Aktivität, die gleichzeitig mit der User Readiness Phase ausgeführt werden. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
- [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
- [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>Planen der Qualität

Wenn Sie Audio-, Video- oder Besprechungen bereitstellen, können Sie einige zusätzliche Schritte zur Optimierung Ihrer Umgebung für diese Funktionalität nutzen. Sie erhalten hier eine Übersicht über die Anforderungen, die bei einer qualitativ hochwertigen Microsoft Teams-Bereitstellung erfüllt sein müssen. Sie können eine erfolgreiche Bereitstellung durch Planung für dienstverwaltung und die Qualität, vor der ersten Bereitstellung Pilot- oder Produktionsserverfarm sicherzustellen.

Die Anleitungen sind in die folgenden Abschnitte unterteilt:

- Der erste Abschnitt enthält eine Übersicht über die Benutzerfreundlichkeit und die für die Qualität maßgeblichen Komponenten. Dabei werden die Bereiche hervorgehoben, auf die Sie sich vor dem Onboarding in Microsoft Teams konzentrieren müssen.

- Im zweiten Abschnitt erhalten Sie Anleitungen zum Planen eines Supportmodells für die Verwaltung von Microsoft Teams vor der ersten Benutzerpilot- oder Produktionsbereitstellung. Dieser Abschnitt beschreibt die Aufgaben, die Sie regelmäßig ausführen müssen, um eine dauerhaft hohe Qualität der Teams-Bereitstellung zu gewährleisten. Darüber hinaus erhalten Sie weitere Anleitungen, die Ihnen helfen sollen, diese Aufgaben zu verstehen und umzusetzen.

- Der dritte Abschnitt enthält konkrete Anleitungen zum Planen des Netzwerks und der Endpunkte in Ihrer Organisation im Hinblick auf die Unterstützung von Microsoft Teams.

- Abschließend werden die nächsten Schritte zusammengefasst und Verweise auf verwandte Inhalte bereitgestellt.

## <a name="key-technical-components-that-affect-user-experience"></a>Erleben Sie die wichtige technische Komponenten, die Einfluss auf Benutzer

In diesem Abschnitt werden die wichtigsten technischen Komponenten, die Benutzerinteraktion betreffen überprüft. Vor der Betrachtung der wichtigen Komponenten müssen Sie sich darüber im Klaren sein, was Benutzerfreundlichkeit bedeutet und wie wichtig sie dafür ist, die Geschäftsziele Ihrer Organisation zu verwirklichen. Wie wird nun die Benutzerfreundlichkeit definiert?

### <a name="user-experience-defined"></a>Definition der Benutzerfreundlichkeit

Geschäftlicher Ziele können realisiert werden bei der Bereitstellung von Microsoft-Teams, und wenn Benutzern Teams als Zusammenarbeit und Kommunikation ihrer kernlösung übernommen. Qualität kann eine positive Benutzer wünschen, ein Key-Attributs in treibende Verwendung und Akzeptanz sicherzustellen. Durch die Bereitstellung von hoher Qualität Dienst, der Personen Delights, Einzelpersonen und Teams Confidence erhalten und finden neue und innovative Wege zur Verwendung des Diensts, Geschäftsvorteile Laufwerk.

Im Mittelpunkt steht dabei, wie die Benutzer Microsoft Teams wahrnehmen, das heißt, was sie bei der Nutzung des Diensts empfinden und wie sie ihm gegenüber eingestellt sind. Was fließt nun in die Benutzerfreundlichkeit ein? Es reicht von Benutzern zu wissen, wie und warum Sie Teams und integrieren es in ihrer täglichen Workflow außergewöhnliche Anrufqualität auftritt und zuverlässig, unabhängig davon, wo sie sind Verbindung hergestellt wird. Benutzerinteraktion ist sehr große Natur. Dieser Artikel befasst sich nur auf die technischen Elemente, die von Ihrer Organisation gesteuert werden können. Weitere Informationen zur benutzerbereitschaft finden Sie unter [Vorbereiten Ihrer Organisation für Teams](https://aka.ms/SkypeToTeams-UserReadiness).

Es gibt bestimmte Anforderungen für die Bereitstellung, die für eine hervorragende Benutzerfreundlichkeit unabdinglich sind – insbesondere bei Verwendung der Cloud-VoIP-Funktionen in Microsoft Teams. Microsoft Teams muss unbedingt gegenüber anderen Investitionen in Kommunikation und Zusammenarbeit bevorzugt behandelt werden, das heißt, der Echtzeit-Datenverkehr muss entsprechend priorisiert werden. Der folgende Abschnitt enthält eine Übersicht über die wichtigen Komponenten, die sich auf die Benutzerfreundlichkeit auswirken. In den weiteren Abschnitten erhalten Sie Anleitungen zum Planen der Bereitstellung und zum Warten der wichtigen Komponenten der Qualität.

### <a name="key-components-of-quality"></a>Wichtige Komponenten der Qualität

Eine Organisation oder unterstützenden Partner zu Beginn der Planung für die drei wichtigsten Komponenten während der Phase technische Bereitschaft einer Bereitstellung Teams: service-Management, Netzwerk und Endpunkte. Die Kombination aller drei Bereiche bildet die Grundlage der Qualität der Benutzerfreundlichkeit.

![Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung.](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung.")

#### <a name="service-management"></a>Dienstverwaltung

Die Dienstverwaltung kann in zwei getrennte Zuständigkeitsbereiche unterteilt werden:

- **Zuständigkeit von Microsoft**. Microsoft ist für die Infrastrukturkomponenten zuständig, aus denen der Office 365-Dienst besteht. Microsoft ist den Kunden gegenüber dafür verantwortlich, sicherzustellen, dass alle Benutzer, die Verbindungen mit Microsoft Teams herstellen, den Dienst als zuverlässig und qualitativ hochwertig wahrnehmen.

- **Zuständigkeit des Kunden**. Sie und Ihre Organisation sind für die Verwaltung verschiedener Aspekte des Office 365-Diensts, des lokalen Netzwerks und der Benutzerendpunkte zuständig. Wenn zum Beispiel neue IP-Adressen zu Office 365 hinzugefügt werden, müssen Sie die entsprechenden Firewalls aktualisieren, um die Kommunikation mit den neuen Endpunkten zuzulassen und Unterbrechungen für die Benutzer zu vermeiden.

Detaillierte Anleitungen für die Planung der Dienstverwaltung finden Sie unter [Planen der Dienstverwaltung](#plan-for-service-management).

#### <a name="network"></a>Netzwerk

In den meisten Organisationen wurden die Netzwerke ursprünglich so entworfen, dass sie den Zugriff auf Daten und Anwendungen in den eigenen Datencentern ermöglichen. Cloudbasierte Anwendungen wie Office 365 erfordern Änderungen an diesen Netzwerken, damit die für Microsoft Teams erforderlichen Zugriffsmethoden und Datenflüsse unterstützt werden. Vor der Aktivierung von Benutzern für Microsoft Teams in der Organisation müssen Sie das aktuelle Netzwerk bewerten und optimieren. Dies ist äußerst wichtig, wenn Sie Cloud-VoIP-Funktionen nutzen.

In herkömmlichen Netzwerken müssen die Benutzer die Umkreisnetzwerke einer Organisation durchlaufen, um auf Microsoft Teams zuzugreifen. Viele Organisationen verfügen über sicherheitsbasierte Geräte wie beispielsweise Proxyserver, Firewalls und VPNs, die möglicherweise den Netzwerkdatenverkehr blockieren oder behindern bzw. einen nicht optimierten Pfad für den Netzwerkdatenverkehr bereitstellen.

Darüber hinaus müssen die internen Kernnetzwerke optimiert und richtig dimensioniert werden, um ausreichende Kapazität und Qualität für die Unterstützung der Teams-Arbeitsauslastungen (einschließlich Echtzeitmedien) bereitzustellen. Sie können mithilfe von Bandbreitenplanung, Wartung und Optimierung sicherstellen, dass das Netzwerk einen qualitativ hochwertigen und effizienten Pfad zu Office 365 bereitstellt.

Detaillierte Anleitungen für die Netzwerkplanung finden Sie unter [Planen der Netzwerkqualität](#plan-for-network-quality).

#### <a name="endpoints"></a>Endpunkte

Microsoft Teams unterstützt eine breite Palette von Endpunkten. Sie können Microsoft Teams überall und über praktisch alle Geräte nutzen, seien es PCs, Tablets oder Telefone.

Um Ihre Benutzer die beste Leistung zu bieten möglich ist, müssen Sie diese wichtige Aspekte berücksichtigen: Führen Sie die Endpunkte erfüllen die Teams Hardware und Software? Sind die Endpunkte für die Unterstützung von WLAN-Netzwerken konfiguriert und optimiert? Über welche Geräte möchten Sie Sprachanrufe tätigen und annehmen? Sind diese Geräte für Microsoft Teams optimiert?

Detaillierte Anleitungen für die Endpunktplanung finden Sie unter [Planen der Endpunktqualität](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Planen der Dienstverwaltung

Die Dienstverwaltung ist ein umfangreiches Thema, das den täglichen Betrieb des Microsoft Teams-Diensts nach der Bereitstellung und der Aktivierung für die Benutzer abdeckt. Der Teams-Dienst umfasst Microsoft Office 365 und die lokal bereitgestellten Infrastrukturkomponenten (zum Beispiel das Netzwerk).

Die Dienstverwaltung ist für die meisten Organisationen höchstwahrscheinlich kein neuer Begriff. Vermutlich haben Sie bereits Prozesse und Tasks implementiert, die mit vorhandenen Diensten verknüpft sind. Wahrscheinlich können Sie auf Vorhandenem aufbauen, wenn Sie jetzt die Dienstverwaltung für die zukünftige Unterstützung von Microsoft Teams planen.

Die Dienstverwaltung umfasst alle Aktivitäten und Prozesse, die bei der End-to-End-Verwaltung von Microsoft Teams anfallen. Wie bereits beschrieben fallen einige Komponenten der Dienstverwaltung (die Infrastrukturkomponenten, aus denen der Office 365-Dienst selbst besteht) unter die Zuständigkeit von Microsoft, während der Kunde seinen Benutzern gegenüber für die Verwaltung der verschiedenen Aspekte von Microsoft Teams, dem Netzwerk und den bereitgestellten Endpunkten verantwortlich ist. Im Mittelpunkt dieses Abschnitts des Dokuments steht die Zuständigkeit des Kunden aus der Perspektive der Dienstverwaltung.

![Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf der Dienstverwaltung.](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf der Dienstverwaltung.")

### <a name="introduction-to-the-operations-guide"></a>Einführung in das Betriebshandbuch

**Was?**, **Wer?** und **Wie?** sind drei wichtige Fragen, die im Hinblick auf die Dienstverwaltung beantwortet werden müssen.

Bei der Beantwortung dieser drei Fragen können Sie das [Betriebshandbuch](1-drive-value-operate-my-service.md) zu Hilfe nehmen. Das Handbuch enthält Listen mit Aktivitäten, die täglich, wöchentlich, monatlich bzw. nach Bedarf ausgeführt werden müssen. Diese Aktivitäten und Aufgaben sind unerlässlich für eine dauerhaft qualitativ hochwertige Teams-Bereitstellung. Bestimmen, die zum Ausführen bestimmter Aktivitäten in Service-Management zuständig sind, ist ein wichtiger Aspekt der Planung, die Sie einem frühen Zeitpunkt in der [Phase Planung](upgrade-enlist-stakeholders.md) sicherstellen eine erfolgreiche Bereitstellung ausführen müssen. Wenn Sie die Aufgaben und Aktivitäten ermittelt haben, müssen die Gruppen oder Einzelpersonen, die Sie den Aufgaben und Aktivitäten zuweisen, diese verstehen und befolgen. Das Betriebshandbuch enthält Informationen und Anleitungen zur Ausführung der einzelnen Aufgaben und/oder Verweise auf externe Inhalte.

### <a name="operational-role-mapping"></a>Zuordnung der operativen Rollen

Die frühzeitige Planung der Dienstverwaltung ist ein wichtiger Meilenstein, da die Betriebsphase mit der Aktivierung der ersten Pilotbenutzer beginnt. Das Projektteam muss die erforderlichen Aufgaben und Aktivitäten überprüfen und ihnen zustimmen, die für die einzelnen operativen Aufgaben zuständigen Teams identifizieren und dann die Zusage und Genehmigung der jeweiligen Teams einholen.

Nach Abschluss der Genehmigung muss das zuständige Team mit der Operationalisierung dieser Rollen und Zuständigkeiten beginnen. Dazu können Schulungen und Vorbereitungsmaßnahmen, Aktualisierungen des Modells für die personelle Besetzung oder Sicherstellen der Bereitschaft externer Partner gehören.

Rollen zuordnen, wie Sie Ihr [Projektteam](upgrade-enlist-stakeholders.md) sammeln kann alle Teams Starten ihrer betriebsbezogenen Aufgaben während der Pilotphase, und lernen Sie Vorgänge, und stellen Sie sicher, dass Sie nach dem Starten der bereitstellungs abgeschlossen ist.

Das Betriebshandbuch enthält eine Liste mit allgemeinen Aufgaben, die typischen für die meisten Szenarien geeigneten Rollen zugeordnet sind. Sie müssen diese Zuständigkeiten an die Gegebenheiten in Ihrer Organisation anpassen.

### <a name="the-quality-champion-role"></a>Die Rolle des Qualitätspioniers

Eine Gruppe oder Einzelperson muss für die Qualität in allen Organisationen verantwortlich sein. Dies ist die wichtigste Rolle bei der Dienstverwaltung. Beim Qualitätspionier handelt es sich um eine Kundenrolle, die einer Person oder Gruppe zugewiesen wird, die sich stark für die Benutzerfreundlichkeit engagiert. Diese Rolle setzt die Fähigkeit voraus, Trends in der Umgebung zu erkennen, und muss gefördert werden, damit die Person oder Gruppe in Zusammenarbeit mit anderen Teams Verbesserungen vorantreiben kann. Der beste Kandidat als Qualitätspionier ist normalerweise der Besitzer des Kundendiensts. Dies kann – je nach Größe und Komplexität der Organisation – eine beliebige Person oder Gruppe sein, die sich stark für die Benutzerfreundlichkeit engagiert.

Der Qualitätspionier nutzt vorhandene Tools und dokumentierte Prozesse, beispielsweise das Anrufqualitäts-Dashboard (AQD) und das Handbuch für die Überprüfung der Erlebnisqualität, um die Benutzerfreundlichkeit zu überwachen, Qualitätstrends zu erkennen und gegebenenfalls Verbesserungen zu fördern. Der Qualitätspionier arbeitet mit den jeweiligen Teams zusammen, um Verbesserungsmaßnahmen voranzutreiben, und unterrichtet einen Lenkungsausschuss über den Fortschritt und die offenen Probleme.

Die mit der Rolle verknüpften Aufgaben und Aktivitäten sind im Betriebshandbuch dokumentiert. Diese Rolle sollte bei der [Planung der Stufe](https://aka.ms/SkypeToTeams-Plan)zugewiesen werden. Ein wichtiger Schritt bei der Operationalisierung der Rolle des Qualitätspioniers besteht darin, das für die Rolle erforderliche Wissen zu erwerben und sicherzustellen, dass die zur Ausführung der Aufgaben erforderlichen Komponenten vorhanden sind. Eine wichtige Aufgabe dieser Rolle besteht darin, eine regelmäßige Überprüfung der Erlebnisqualität auszuführen.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Einführung in das Handbuch für die Überprüfung der Erlebnisqualität

Das Handbuch für die Überprüfung der Erlebnisqualität enthält Aktivitäten zum Bewerten und Bereitstellen von Verbesserungsanleitungen in wichtigen Bereichen, die größten Auswirkungen auf die Verbesserung der Benutzerfreundlichkeit haben (siehe folgende Abbildung).

![Dieses Diagramm veranschaulicht die wichtigen Bereiche, die bei einer Überprüfung der Erlebnisqualität betrachtet werden.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Dieses Diagramm veranschaulicht die wichtigen Bereiche, die bei einer Überprüfung der Erlebnisqualität betrachtet werden.")

Durch kontinuierliches Bewerten und Verbessern der in diesem Dokument beschriebenen Bereiche können Sie die Wahrscheinlichkeit verringern, dass sie sich nachteilig auf die Benutzerfreundlichkeit auswirken. Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:

- Unvollständige Firewall- oder Proxykonfiguration

- Schlechte WLAN-Abdeckung

- Unzureichende Bandbreite

- VPN

- Verwendung nicht optimierter oder integrierter Audiogeräte

- Problematische Subnetze oder Netzwerkgeräte

Die Anleitungen im Handbuch für die Überprüfung der Erlebnisqualität konzentrieren sich auf die Verwendung des online verfügbaren Anrufqualitäts-Dashboards (AQD) als primäres Tool zum Melden und Untersuchen der einzelnen beschriebenen Bereiche. Der Schwerpunkt liegt dabei auf Audio, um die Einführung und die Auswirkungen zu maximieren. Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.

Wir empfehlen dringend, den Qualitätspionier frühzeitig zu ernennen. Der ernannte Qualitätspionier sollte sich dann mit dem Inhalt des Handbuchs für die Überprüfung der Erlebnisqualität vertraut machen.

Das Handbuch für die Überprüfung der Erlebnisqualität finden Sie [hier](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Planen der Netzwerkqualität

Die Planung der Netzwerkqualität steht im Mittelpunkt des folgenden Abschnitts.

![Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf dem Netzwerk.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf dem Netzwerk.")

Wie bereits erwähnt muss die Netzwerkqualität unbedingt vor dem Onboarding in Microsoft Teams geplant werden. Weitere Anleitungen zur Netzwerkvorbereitung finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md).

In den meisten Organisationen können Netzwerke aus verwalteten und nicht verwalteten Netzwerken bestehen.

Verwaltete Netzwerke sind Komponenten der Netzwerkinfrastruktur, über die eine Organisation die direkte Kontrolle hat. Daher haben verwaltete Netzwerke einen direkten Einfluss auf die Qualität, die für Arbeitsauslastungen mit Echtzeit-Datenverkehr bereitgestellt werden kann.

Nicht verwaltete Netzwerke dagegen sind Segmente des Netzwerks, über die ein Kunde begrenzte oder gar keine Kontrolle hat.

Internetverbindungen zwischen der Organisation und Office 365 sind Netzwerke, über die ein Kunde begrenzte Kontrolle hat. Die Netzwerke werden von einem ISP verwaltet, aber Organisationen sollten in der Lage sein, die Qualität des Netzwerks zu beeinflussen, indem sie größere Bandbreite bereitstellen, sich für Routenoptimierungen aussprechen oder notfalls den ISP wechseln.

Heimnetzwerke in Hotels oder Cafés sind Beispiele für Netzwerke, über die der Kunde keine Kontrolle hat.

In den folgenden Abschnitten konzentrieren wir uns auf die Qualitätsanforderungen verwalteter Netzwerke.

### <a name="key-network-planning-areas"></a>Wichtige Bereiche der Netzwerkplanung

Die folgenden Abschnitte konzentrieren sich auf die für die Bereitstellung eines qualitativ hochwertigen Netzwerks wichtigen Bereiche.

> [!NOTE]
> Viele Netzwerke entwickeln sich im Lauf der Zeit weiter, sei es durch Upgrades, durch Erweiterung oder durch andere geschäftliche Anforderungen. Stellen Sie sicher, dass Sie über betriebliche Prozesse verfügen, mit denen diese Bereiche im Rahmen der Planung der Dienstverwaltung gewartet werden.

#### <a name="bandwidth"></a>Bandbreite

Die Bandbreitenplanung stellt einen wichtigen Aspekt der Netzwerkvorbereitung dar. Stellen Sie unbedingt sicher, dass ausreichende Bandbreite für die Microsoft Teams-Arbeitsauslastungen zur Verfügung steht. Damit Sie ein vorhandenes Netzwerk richtig dimensionieren können, müssen Sie sich darüber im Klaren sein, was zurzeit bereitgestellt ist, wie die aktuelle Auslastung aussieht und wie viel verfügbare Bandbreite letztlich verbleibt.

Zum Messen der aktuellen Auslastung müssen Sie das Netzwerk überwachen. Diese Messung kann dann als Ausgangspunkt für die Bandbreitenplanung dienen. Darüber hinaus sollte das Netzwerk während und nach der Bereitstellung ständig überwacht werden, um sicherzustellen, dass die Bereitstellung für das Netzwerk ausreicht.

> [!NOTE]
> Beim Überwachen der Netzwerkauslastung dürfen Sie auf keinen Fall Tagesdurchschnittswerte verwenden. Diese Durchschnittswerte können Zeiten außerhalb der Kernzeiten enthalten, die das Ergebnis verzerren. Bei Durchschnittswerten sind Spitzenzeiträume möglicherweise nicht sichtbar, sodass zugrunde liegende Probleme verschleiert werden.

Der [Netzwerkplaner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) hilft Ihnen, mit wenigen einfachen Schritten die Netzwerkanforderungen für Ihre Bereitstellung zu ermitteln und zu organisieren. Wenn Sie mithilfe des Tools die Details zum Netzwerk Ihrer Organisation und zur Nutzung von Cloud-VoIP zusammenstellen, können Sie eine ungefähre Berechnung der Netzwerkanforderungen für Ihre Cloud-VoIP-Bereitstellung erhalten und diese Details zur Berichterstellung verwalten und exportieren und Bereiche betrachten, die Sie näher untersuchen möchten. Außerdem erhalten Sie Informationen zu den nächsten Schritten.

#### <a name="quality-of-service-qos"></a>Quality of Service (QoS)

QoS sollte in allen Segmenten des verwalteten Netzwerks implementiert werden, selbst in Netzwerken, in denen angemessene Bandbreite bereitgestellt ist. Im letzteren Fall fungiert QoS als Risikominderung bei unvorhergesehener Netzwerklast. Wenn QoS implementiert ist, wird VoIP-Datenverkehr priorisiert, sodass sich diese unvorhergesehenen Ereignisse nicht auf die Qualität auswirken.

Eine QoS-Implementierung sollte Bereiche des Netzwerks einschließen, vom Endpunkt bis hin zu den Ausgangspunkten und von den Ausgangspunkten zurück zum Endpunkt. Damit wird sichergestellt, dass VoIP-Datenverkehr in beiden Richtungen priorisiert wird. QoS sollte sowohl in Kabelnetzwerken als auch in WLAN-Netzwerken implementiert werden.

Bei der Implementierung von QoS in Ihrem Netzwerk können Sie die Anleitungen unter [Quality of Service in Microsoft Teams](qos-in-teams.md) zu Hilfe nehmen.

#### <a name="proxy-servers"></a>Proxyserver

Viele Organisationen betrachten an das Internet gerichteten Datenverkehr als Sicherheitsrisiko und mindern dieses Risiko, indem sie den Datenverkehr an den Ausgangspunkten im Netzwerk überwachen und bewerten. Zur Erfüllung dieser Anforderung können Sie Geräte aus der Klasse der Proxyserver bereitstellen.

Ein Proxyserver kann Probleme verursachen, wenn er Pakete überprüft oder die Nutzlast ändert. Dies kann zu Fehlern beim Anrufaufbau, unterbrochenen Anrufen und schlechter Anrufqualität führen. Wenn Echtzeitmedien gezwungen werden, einen Proxyserver zu durchlaufen, wird der Medienstapel in Microsoft Teams gezwungen, einen Failback zu TCP auszuführen. Dies kann die Qualität weiter verringern. UDP wird immer gegenüber TCP bevorzugt.

Außerdem ist ein Proxyserver möglicherweise nicht dazu gedacht, die zusätzliche Last von Office 365 und insbesondere Microsoft Teams-Arbeitsauslastungen einschließlich Echtzeitmedien zu verarbeiten.

Aufgrund der möglicherweise durch einen Proxyserver entstehenden Probleme und dieser zusätzlichen Kapazitätsbedenken empfiehlt Microsoft, den Proxyserver zu umgehen und eine direkte Verbindung mit Office 365 herzustellen.

Die für die Umgehung des Proxyservers erforderliche Konfiguration ist je nach Anbieter unterschiedlich, aber in der Regel wird dabei die automatische Proxy-Konfigurationsdatei (PAC-Datei) aktualisiert. Bei der PAC-Datei handelt es sich um eine Konfigurationsdatei, in der beschrieben wird, welcher Datenverkehr den Proxy durchläuft und welcher Datenverkehr diesen umgeht.

Manche Proxyserveranbieter stellen einen automatisierten Prozess bereit, um sicherzustellen, dass die Konfiguration auf dem aktuellen Stand ist. Wenn Ihr Anbieter diesen automatischen Prozess nicht bereitstellt, können Sie unter <https://aka.ms/o365proxies> eine aktualisierte PAC-Datei herunterladen.

[Proxyserver für Teams oder Skype für Unternehmen Online und Teams](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>Firewalls

Für den Zugriff auf Microsoft Teams müssen Sie sicherstellen, dass die richtigen Ports und Protokolle für alle IP-Adressen und Protokolle von Office 365 geöffnet sind. Dies ist auch für eine qualitativ hochwertige Bereitstellung unerlässlich. Wenn Sie sicherstellen möchten, dass die Firewall richtig konfiguriert ist, reicht es nicht aus, einfach einen Anruf zu tätigen oder an einer Telefonkonferenz teilzunehmen.

Wenn in der Firewall nur TCP geöffnet ist, wird die Sitzung eingerichtet, aber der bevorzugte Transport (UDP) wird nicht ausgehandelt. Die höchste Benutzerfreundlichkeit erzielen Sie, wenn sowohl TCP als auch UDP in der Firewall geöffnet ist.

TCP ist zustandsbehaftet und wird daher für Echtzeitmedien nicht bevorzugt und nur als Failbacknetzwerktransport für Microsoft Teams bereitgestellt. Wenn bei TCP eine Paketverzögerung oder ein Paketverlust auftritt, müssen diese Pakete erneut übermittelt werden, bis sie bestätigt werden. Dies kann dazu führen, dass nicht mehr relevante Medienpakete mit der zeitgerechten Übermittlung aktueller Medienpakete konkurrieren. Der Teams-Client des Benutzers versucht, den Audioinhalt zu strecken. Dies kann je nach Netzwerkbedingungen zu hörbaren Artefakten führen. Angesichts des zusätzlichen Aufwands für TCP kann aus einer allgemein akzeptablen Benutzerfreundlichkeit eine mangelhafte Benutzerfreundlichkeit werden. Aus diesem Grund ist der zustandslose Netzwerktransport über UDP erforderlich.

Eine umfassende Anleitung für das Öffnen der Firewall für Microsoft Teams finden Sie im Artikel [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips).

Nach dem Öffnen der Firewall können Sie mit dem  [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885)  die Konnektivität für Cloud-VoIP-Funktionen validieren.

> [!IMPORTANT]
> Die IPs und URLs von Microsoft Office 365 ändern sich im Lauf der Zeit. Wichtig ist, dass Sie im Rahmen der Planung der Dienstverwaltung sicherstellen, dass ein betrieblicher Prozess vorhanden ist und dass eine Gruppe für das Überwachen der [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips) verantwortlich ist und entsprechende Aktualisierungen vornimmt.

#### <a name="local-internet-egress"></a>Lokaler Internetausgang

Viele Netzwerke wurden für die Verwendung einer Hub-Spoke-Topologie entworfen. In dieser Topologie durchläuft der Internetdatenverkehr normalerweise das WAN zu einem zentralen Datencenter und tritt dann in das Internet aus. Dies geschieht häufig, um die Netzwerksicherheitsgeräte zu zentralisieren und dadurch die Gesamtkosten zu reduzieren.

Der Rücktransport des Datenverkehrs durch das WAN erhöht die Latenz und hat negative Auswirkungen auf die Qualität und die Benutzerfreundlichkeit. Da Microsoft Teams im großen globalen Netzwerk von Microsoft ausgeführt wird, gibt es oft einen Netzwerkpeering-Standort in der Nähe des Benutzers. Benutzer erzielen wahrscheinlich eine bessere Leistung, indem sie ihre Daten so schnell wie möglich aus einem lokalen Internetpunkt in der Nähe ihres Standorts heraus und in unser für VoIP optimiertes Netzwerk leiten. Bei einigen Arbeitsauslastungen werden DNS-Anforderungen verwendet, um den Datenverkehr an den nächstgelegenen Front-End-Server zu senden. In diesen Fällen ist es wichtig, dass bei Verwendung eines lokalen Ausgangspunkts auch lokale DNS-Auflösung genutzt wird.

Durch Optimieren des Netzwerkpfads zum globalen Netzwerk von Microsoft wird die Leistung verbessert und letztendlich die größtmögliche Benutzerfreundlichkeit erzielt. Weitere Details finden Sie im Blogbeitrag [Erzielen der besten Konnektivität und Leistung in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

VPNs leisten vielen Organisationen wertvolle Dienste. Leider werden sie in der Regel nicht für die Unterstützung von Echtzeitmedien entworfen oder konfiguriert. Manche VPNs unterstützen möglicherweise UDP nicht. Außerdem entsteht durch VPNs eine zusätzliche Verschlüsselungsebene über dem bereits verschlüsselten Mediendatenverkehr. Darüber hinaus leidet möglicherweise aufgrund des Hairpinnings des Datenverkehrs durch ein VPN-Gerät die Effizienz der Konnektivität mit dem Microsoft Teams-Dienst. Des Weiteren werden VPNs nicht zwangsläufig im Hinblick auf die Kapazität für die Verarbeitung der erwarteten für Microsoft Teams erforderlichen Lasten entworfen.

Es wird empfohlen, einen alternativen Pfad bereitzustellen, der das VPN für Teams-Datenverkehr umgeht. Dies wird allgemein als VPN mit geteiltem Tunnel bezeichnet. Getrenntes Tunneln bedeutet, dass Datenverkehr für Office 365 nicht das VPN durchläuft, sondern direkt zu Office 365 geleitet wird. Diese Änderung wirkt sich positiv auf die Qualität aus, bietet aber auch den sekundären Vorteil, dass die Last für die VPN-Geräte und das Netzwerk der Organisation reduziert wird.

Wenn Sie einen geteilten Tunnel implementieren möchten, erkundigen Sie sich bei Ihrem VPN-Anbieter nach den Konfigurationsdetails.

#### <a name="wi-fi"></a>WLAN

Wie VPNs werden auch WLAN-Netzwerke nicht zwangsläufig für die Unterstützung von Echtzeitmedien entworfen oder konfiguriert. Die Planung und/oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Microsoft Teams ist bei der Bereitstellung von Qualität eine wichtige Überlegung.

Beim Optimieren eines WLAN-Netzwerks kommen verschiedene Faktoren zum Tragen.

- Implementieren Sie QoS oder Wi-Fi Multimedia (WMM), um sicherzustellen, dass Mediendatenverkehr gegenüber den WLAN-Netzwerken entsprechend priorisiert wird.

- Planen und optimieren Sie die WLAN-Bänder und die Platzierung der Zugriffspunkte. Der 2,4-GHz-Bereich bietet zwar möglicherweise je nach Platzierung des Zugriffspunkts eine angemessene Qualität, aber Zugriffspunkte werden oft durch andere Heimanwendergeräte beeinflusst, die im gleichen Bereich betrieben werden. Der 5-GHz-Bereich ist aufgrund seiner Dichte besser für Echtzeitmedien geeignet, erfordert jedoch mehr Zugriffspunkte, um eine ausreichende Abdeckung zu erzielen. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.

- Wenn Dual-Band-WLAN-Netzwerke bereitgestellt sind, ziehen Sie die Implementierung von Bandsteuerung in Betracht. Diese Technik wird von WLAN-Anbietern implementiert, um Dual-Band-Clients zur Verwendung des 5-GHz-Bereichs zu veranlassen.

- Kanalüberlappung: Wenn Zugriffspunkte im gleichen Kanal zu nah beieinander positioniert sind, können sie Signalüberlappung verursachen und unbeabsichtigt in Wettstreit miteinander treten. Dies führt zu einer mangelhaften Benutzerfreundlichkeit. Stellen Sie sicher, dass Zugriffspunkte, die sich nah beieinander befinden, nicht überlappende Kanäle verwenden.

Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wir empfehlen Ihnen, sich bei Ihrem Anbieter nach konkreten Anleitungen zu erkundigen.

### <a name="network-readiness-assessment"></a>Bewertung der Netzwerkbereitschaft

Zu den Aktivitäten im Zusammenhang mit der Netzwerkbereitschaft gehört eine Netzwerkbewertung. Wenn Sie die Planung und Konfiguration abgeschlossen haben, können Sie sich mit der Bewertung vor dem Onboarding der Benutzer in Microsoft Teams grundlegende Informationen zur Qualität Ihres Netzwerks verschaffen. Die Bewertungsergebnisse helfen Ihnen auch, vor dem Aktivieren von Benutzern für Microsoft Teams Verbesserungsmaßnahmen zu identifizieren und zu priorisieren.

Die Netzwerkbewertung sollte für Kabelnetzwerke und WLAN-Netzwerke in allen Gebäuden, die für Cloud-VoIP-Funktionen in Microsoft Teams aktiviert werden, ausgeführt werden.

Die Netzwerkbewertung kann mit Unterstützung eines Microsoft-Partners, mit Drittanbietertools oder mit dem [Microsoft Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885) durchgeführt werden. Wir auch bieten weitere Anweisungen zum Ausführen der Bewertung, verwenden das Microsoft-Netzwerk-Assessment-Tool als Teil des Bereitschaft der Anleitung [hier](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>Planen der Endpunktqualität

Wie Sie im folgenden Diagramm sehen, stellen Endpunkte einen wichtigen Baustein einer Bereitstellung von hoher Qualität für die Benutzer bereit.

![Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf Endpunkten.](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Dieses Diagramm zeigt die drei Komponenten der Qualität sowie die Überlappungen aller drei Komponenten mit der Dienstverwaltung. Der Schwerpunkt liegt auf Endpunkten.")

Microsoft Teams-Endpunkte können auf vielen Geräten ausgeführt werden, beispielsweise auf PCs, Macs, Tablets und mobilen Geräten. Für die Benutzerfreundlichkeit spielt nicht nur das Gerät eine Rolle, sondern auch, wie Benutzer eine Verbindung mit dem Gerät herstellen – beispielsweise mithilfe des in das Gerät integrierten Mikros und Lautsprechers, über Ohrhörer oder über ein optimiertes Headset. Die Verwendung eines optimierten Headsets kann sich positiv auf die allgemeine Benutzerfreundlichkeit auswirken.

Die folgenden Anleitungen zur Endpunktplanung sollen Ihnen helfen, für Ihre Organisation ein erfolgreiches Onboarding in Microsoft Teams sicherzustellen.

### <a name="endpoint-capability"></a>Endpunktfunktionen

Der erste Teil der Planung besteht darin, sicherzustellen, dass alle PCs und anderen Geräte in der Organisation Microsoft Teams ausführen können. Dazu müssen Sie nicht nur die Hardwareanforderungen betrachten, sondern sich auch verdeutlichen, was außerdem im Hintergrund auf dem PC geschieht. Viele Organisationen führen weitere Software aus, beispielsweise Angriffserkennungssysteme und Antischadsoftware, die Basisleistung eines Geräts beeinflussen kann.

Microsoft Teams-Clients sind für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android, iOS und Windows Mobile) verfügbar. Informationen zu den Softwareanforderungen für die einzelnen Plattformen finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben. Clientseitige Firewalls können nicht nur verhindern, dass ein Anruf aufgebaut wird, sondern sich auch auf die Anrufqualität auswirken. Konfigurieren Sie die entsprechenden Ausschlüsse in der Clientfirewall anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips). Ihr Drittanbieter sollte über konkrete Anleitungen zum Erstellen der Ausschlüsse verfügen.

> [!NOTE]
> Microsoft Teams aktualisiert automatisch die Windows-Firewall mit einer entsprechenden Firewallkonfiguration.

### <a name="wi-fi-recommendations-for-endpoints"></a>WLAN-Empfehlungen für Endpunkte

Zum Planen und Bereitstellen eines optimierten WLAN-Netzwerks, das Echtzeit-Arbeitsauslastungen in Microsoft Teams unterstützen soll, gehört eine umfassende Planung. Die folgenden Abschnitte enthalten allgemeine Anleitungen, die Ihnen helfen sollen, einige häufige Fallstricke beim Planen von Endpunkten zu vermeiden.

#### <a name="wi-fi-drivers"></a>WLAN-Treiber

Manche WLAN-Treiber können problematisch sein. So kann beispielsweise ein Treiber ein sehr aggressives Verhalten beim Roaming zwischen Zugriffspunkten aufweisen, was zu einer mangelhaften Anrufqualität führt. Wichtig ist auch (obwohl dies nicht häufig der Fall ist), sicherzustellen, dass die WLAN-Treiber auf dem PC vor der Bereitstellung aktualisiert und getestet werden.

#### <a name="wi-fi-bands"></a>WLAN-Bänder

WLAN-Geräte verwenden heute im Wesentlichen zwei Bänder: 2,4 GHz und 5,0 GHz. Wenn Ihre Organisation beide Bänder bereitstellt, sollten Sie die Treibereinstellungen so konfigurieren, dass das 5,0-GHz-Band bevorzugt wird. Dieses Band ist im Hinblick auf den Durchsatz erheblich dichter und von den im 2,4-GHz-Band auftretenden Störungen weniger betroffen. Bei dieser Empfehlung wird angenommen, dass Sie das 5,0-GHz-Netzwerkband richtig optimiert haben.

#### <a name="wi-fi-radio-type"></a>WLAN-Funkstandard

Planen Sie mit Geräten, die neueren WLAN-Funkstandards unterstützen. Sie können eine sehr gute WLAN-Leistung erzielen, wenn Sie auf den bereitgestellten Geräten 802.11ac oder einen neueren Standard nutzen.

#### <a name="wireless-avoidance"></a>WLAN-Vermeidung

Manche Organisationen möchten WLAN ganz vermeiden. In diesem Zusammenhang wird Benutzern manchmal empfohlen, eine direkte Verbindung mit einem Kabelnetzwerk herzustellen. In manchen Fällen sieht die Reihenfolge der Netzwerkbindungen eine Bevorzugung der WLAN-Verbindung vor, die dann weiterhin verwendet wird, obwohl der PC über die Kabelverbindung verbunden ist. Wenn Sie dieses unbeabsichtigte Verhalten vermeiden möchten, konfigurieren Sie die Bindungsreihenfolge so, dass dieses Szenario vermieden wird.

#### <a name="80211-power-save-protocol"></a>802.11-Protokoll für den Energiesparmodus

Wenn Ihre Organisation WLAN-Zugriffspunkte oder -Router ohne Unterstützung für das 802.11-Protokoll für den Energiesparmodus verwendet, sind unterbrochene Anrufe oder mangelhafte Anrufqualität in Microsoft Teams auf Windows-Geräten möglich. Wenn die WLAN-Zugriffspunkte oder -Router nicht aktualisiert werden können, sollten Sie auf Geräten, die mit Akku betrieben werden, die Windows-Einstellungen für den Energiesparplan aktualisieren. Weitere Details und Konfigurationsanleitungen finden Sie im folgenden [Supportartikel](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Geräte für Microsoft Teams

Microsoft Teams kann für Besprechungen oder als Telefonsystem verwendet werden. Bei der Verwendung dieser Funktionen spielt das für Microsoft Teams verwendete Gerät eine wichtige Rolle für die Benutzerfreundlichkeit.

Benutzer, die einen integrierten PC-Lautsprecher und ein integriertes Mikrofon verwenden, empfinden diese Konfiguration möglicherweise als akzeptabel. Diese Geräte sind jedoch in der Regel nicht im Hinblick auf die Rauschunterdrückung optimiert, und jede Art von Hintergrundgeräusch kann sich auf die anderen Gesprächspartner auswirken. Die Nutzung von für diese Szenarien optimierten Geräten kann eine hohe Qualität sicherstellen.

Alle Geräte müssen den Anforderungen der Benutzer entsprechen. Sie müssen Geräte wie beispielsweise Headsets auf die verschiedenen Personas und Anwendungsfälle in der Organisation abstimmen. Im Rahmen des Planungsprozesses sollte eine Zuordnung von Personas zu Geräten erstellt werden.

Wenn Sie die Geräte ausgewählt haben, nehmen Sie sie zur endgültigen Validierung in den Pilottestplan auf. Nutzen Sie in der Pilotphase Umfragen, um Feedback zu sammeln, damit Sie sicherstellen können, dass Sie die optimale Gerätestrategie verwenden.

Zurzeit empfehlen wir die Verwendung von Geräten, die über das Skype for Business-Zertifizierungsprogramm zertifiziert wurden. Über dieses Programm zertifizierte Geräte finden Sie im Lösungskatalog für [USB-Geräte mit Skype for Business-Zertifizierung](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Weitere Details finden Sie unter [Client und Geräte – Vorbereitungsworkshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13).

## <a name="client-updates"></a>Clientupdates

Einer der wichtigen Vorteile von Microsoft Teams besteht darin, dass der Client automatisch auf dem aktuellen Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet. Die Downloadgröße des Clients beträgt etwa 100 MB.

Organisationen können den Updateprozess nicht steuern oder über eine Richtlinieneinstellung verwalten. Um das Risiko eines in einem neueren Build erkannten Problems zu mindern, wird auf dem Endpunkt die letzte als funktionierend bekannte Version beibehalten. Wenn ein Problem mit einem neuen Build vorliegt, kann der Microsoft Teams-Dienst auf dem Endpunkt automatisch die vorherige Version wiederherstellen.

## <a name="next-steps-and-references"></a>Nächste Schritte und Verweise

Diese Tabelle enthält eine Zusammenfassung der Planungsaktivitäten mit Links zu verwandten Inhalten.

| Bereich | Details | Referenzen |
|---|---|---|
| Planen der Dienstverwaltung | Durchführen einer Übung zur Zuordnung der operativen Rollen <br/> Genehmigung durch die verantwortlichen Teams <br/> Vorbereitung der Rollen | [Betriebshandbuch](1-drive-value-operate-my-service.md) |
| | Ernennen von Qualitätspionieren <br/> Vorbereitung der Qualitätspioniere| [Vertrautmachen mit dem AQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Handbuch für die Überprüfung der Erlebnisqualität](https://aka.ms/qerguide) |
| | Installieren von Vorlagen für die Überprüfung der Erlebnisqualität <br/> Hochladen einer Gebäudedatei | [QERLite-Vorlagen](https://aka.ms/qertemplates) <br/> [Hochladen von Gebäudeinformationen](turning-on-and-using-call-quality-dashboard.md)|
| Planen der Netzwerkqualität | Ausführen des Netzwerkplaners | [Netzwerkplaner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implementieren von QoS | [Quality of Service in Microsoft Teams](qos-in-teams.md) |
| | Umgehen von Proxyservern | [Anleitungen für Proxys](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implementieren eines VPNs mit geteiltem Tunnel | [Anleitung für VPNs mit geteiltem Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimieren von WLAN-Netzwerken für Echtzeitmedien | Zurateziehen von Drittanbietern |
| | Implementieren eines lokalen Internetausgangs | [Lokaler Internetausgang](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementieren der Netzwerkkonnektivität <br/> Überprüfen der Netzwerkverbindung | [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips) |
| | | [Network Assessment-Tool](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Ausführen einer Netzwerkbewertung | [Bewertung der Netzwerkbereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Planen der Endpunktqualität | Aktualisieren der Endpunktfirewalls | [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips) |
| | Validieren der Softwareanforderungen | [Clients für Microsoft Teams abrufen](get-clients.md) |
| | Implementieren der WLAN-Empfehlungen für Endpunkte | Zurateziehen von Drittanbietern |
| | Erstellen einer Zuordnung von Personas zu Geräten <br/> Bereitstellen von Geräten und Durchführen von Pilottests für die Geräte | [Client und Geräte – Vorbereitungsworkshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Gerätekatalog](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Nachdem Sie die Planung abgeschlossen haben, fahren Sie fort mit dem nächsten Schritt: [Vorbereiten der Umgebung für Teams](https://aka.ms/SkypeToTeams-TechnicalReadiness).