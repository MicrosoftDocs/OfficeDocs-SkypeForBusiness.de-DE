---
title: Teams Contact Center
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: 'Übersicht über die integrierte #A0 (Contact Center as a Service) für Microsoft Teams'
appliesto:
- Microsoft Teams
ms.openlocfilehash: d34a1790a082e1defab399828cceb5c0082dc70d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909489"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Kontaktcenterintegrationen für Microsoft Teams

Das Integrieren beliebter Kontaktcenterlösungen in Microsoft Teams ist eine häufige Notwendigkeit für Kunden, die Funktionen für Anrufe in Teams bereitstellen.  Dieser Artikel enthält eine Übersicht über die Integration von Kontaktcenterlösungen in Microsoft Teams sowie zusätzliche Informationen zu den Partnerlösungen, die am Zertifizierungsprogramm für verbundene Kontaktcenter für Microsoft Teams teilnehmen.

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>Was ist eine Kontaktcenterintegration für Microsoft Teams?

Die heutigen Kontaktcenter bieten weit mehr als nur Support – sie stellen eine der Hauptkontakte für Interaktionen und ungefiltertes Feedback auf die Erfahrungen eines Kunden mit einer Marke bei. Aufgrund der Breite der Kanäle, über die sich heutige Kunden gerne beteiligen – Telefon, E-Mail, Text, soziale Netzwerke – und der erweiterten Menge von Berührungspunkten im Zusammenhang mit den Kaufprozessen des heutigen Tages haben viele Organisationen zwei zusätzliche Möglichkeiten erkannt:

1. Jedes Mitglied der Organisation verfügt über das Potenzial, direkt an der Einbindung eines Kunden beteiligt zu sein, und muss daher mit den entsprechenden Tools ausgestattet sein.

2. Für diesen erweiterten Umfang von Kundeninteraktionen sind Tools erforderlich, mit deren Hilfe Konsistenz, kontinuierliche Verbesserung und Skalierung verbessert werden können.

Microsoft Teams unterstützt Arbeitsströme von Kundeninteraktionen, indem es als Hub für interne und externe Kundenverbindung über alle Kommunikationsmodi hinweg, einschließlich Chat, Videobesprechungen und Anrufen, agiert. Bei einigen Unternehmen stellen die Cloud-Sprachfunktionen von Microsoft Teams, einschließlich der automatischen Telefonisten und Anrufwarteschleifen, die Features und die Konfiguration bereit, die ihren Anforderungen entsprechen. [](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) [](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)

Für andere, die integrierte Lösungen mit Geschäftstools und Workflows wünschen, um den Kunden zu unterstützen, ist Microsoft Teams auch in einige der branchenführenden CCaaS-Lösungsanbieter (Contact Center as a Service) integriert.

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Connected Contact Center für Microsoft Teams Certification Program

Die APIs ermöglichen es Partnern, #A0 für Teams zu entwickeln und zu integrieren. Darüber hinaus haben wir das Connected Contact Center für Microsoft Teams-Zertifizierungsprogramm entwickelt, um Kunden die Sicherheit zu geben, dass die Lösung jedes teilnehmenden Partners getestet und verifiziert wurde, um die Qualität, Kompatibilität und Zuverlässigkeit sicherzustellen, die von den Microsoft-Lösungen erwartet wird.

Die folgenden Partner sind dabei, ihre Lösung für Microsoft Teams zu zertifizieren und sind bereit, Kunden zu engagieren:

|  Partner                                                                                                                               |  Website der Lösung                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `8x8` | https://www.8x8.com/products/integrations/8x8-voice-for-microsoft-teams?locale=us |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | www.contactcenter4all.com |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| 'Geomant' | https://www.geomant.com/buzzeasy-contact-centre-for-microsoft-teams                                          |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |

Diese Liste wird aktualisiert, sobald weitere Partner beitreten und die Zertifizierungskriterien erfüllen.

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>Wie funktionieren Kontaktcenterlösungen in Microsoft Teams?

Microsoft Teams bietet eine Reihe von Funktionen zur Unterstützung der Entwicklung von Sprachlösungen von Drittanbietern, darunter:

1. [Direct Routing Connectivity](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [Microsoft Graph Cloud Communication APIs](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. Plattform und Erweiterung von Teams

4. Teams SDKs

Zusammen ermöglichen diese Funktionen drei Integrationsmodelle:

  - **Verbinden** (über Direct-Routing)

  - **Verbinden und Erweitern** (Direct-Routing, Graph-APIs und Plattform für Teams-Apps)

  - **Erweitern und Power** (Einbetten von Teams-SDKs in 3p-Apps für systemeigene Teams-Interaktionen)

### <a name="connect"></a>Verbinden

Dieses Modell verbindet #A0 mit der Telefonsysteminfrastruktur von Microsoft Teams und ermöglicht so erweiterte Einblicke in Routing, Konfiguration und System. Bei diesem Modell kann die Partnerlösung für das Kontaktcenter auch Telefoniedienste für ausgewählte Nummern und Benutzer bereitstellen.

Agents, die auf dem Modell "Connect" integrierte Lösungen verwenden, können Informationen & Erkenntnisse sammeln und gegebenenfalls Anrufe direkt an Fachleute durchstellen, indem sie die ANWESENHEITSINFORMATIONEN in Teams verwenden, um deren Verfügbarkeit sicherzustellen.

Organisationen können die Weiterleitung an den optimalen Agent sicherstellen, indem sie automatisierte virtuelle Assistenten und qualifikationsbasierte Routingwarteschlangen einrichten.

**Feature-Highlights:**

Im Folgenden finden Sie zwar keine umfassende Liste der Featurefunktionen für dieses Integrationsmodell, die Schwerpunktbereiche umfassen jedoch:

  - Office 365-Authentifizierung für Agents, damit Agents über ihren integrierten #A0 eine Verbindung mit ihrem #A1 herstellen können 

  - Anwesenheitsanzeige von Teams-Benutzern 

  - Anrufflüsse über direktes Routing (wie in Testplänen angegeben) 

  - Supportübertragungen und Gruppenanrufe mit Teams-Benutzern 

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - Unterstützung von sip-Trunking mit mehreren Mandanten zur Unterstützung mehrerer Kunden mit SBC des Partners.  

  - Partner zum Implementieren des [ <span class="underline">zertifizierten Session Border Controllers (SBC) von Microsoft</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>Verbinden und Erweitern

Dieses Modell erweitert die Kontaktcenter-Mitarbeiter- und Agenterfahrungen durch die Integration in den Teams-Client mithilfe der [Teams-Clientplattform,](https://docs.microsoft.com/microsoftteams/platform/overview) [der Teams -Graph-APIs](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) und der [Cloudkommunikations-API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) und verwendet das Telefonsystem von Teams für alle Kontaktcenteranrufe und Anrufsteuerungserfahrungen. In diesem Modell fungiert der Kontaktcenterpartner neben Microsoft 365 als Telefonieanbieter.

Mithilfe von Connect- und Extend-basierten Lösungen können Agents von dynamischen kontextbezogenen Notizen profitieren, die Daten aus mehreren Systemen korrelieren, bevor sie ein Engagement starten, und dann aufwendige Kontextwechsel vermeiden, indem sie systemeigene in Teams für interne Zusammenarbeit und externe Kommunikation arbeiten.

Organisationen können Workflows und erweiterte Routingkonfigurationen bis hin zu einzelnen Personen entwerfen und die Qualität ihres Systems und ihrer Interaktionen messen.

**Feature-Highlights:**

Im Folgenden finden Sie zwar keine vollständige Liste der Featurefunktionen für dieses Integrationsmodell, jedoch werden die Hauptfokusbereiche hervorgehoben:

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - Teams-basierte App für Die Erfahrungen von Agenten 

  - Teams als primären Endpunkt für Anrufe für die Agents 

  - Teams-Clientanrufe für alle Anrufsteuerelemente

  - Die App für die Mitarbeitererfahrung sollte auch im Web- und mobilen Teamclient von Teams funktionieren können.

  - Analysen, Workflowverwaltung, rollenbasierte Erfahrungen für Agents in der #A0 in Teams

  - Integrierte Chat- und Zusammenarbeitserfahrungen in Teams-Clients 

  - Erhalten der Leistung und Qualität der Teamclienterfahrungen in allen Apps  

### <a name="extend-and-power"></a>Erweitern und Leistung

Dieses Modell ermöglicht es Partnern, native Azure-basierte Sprachanwendungen mithilfe der Anrufinfrastruktur und Clientplattform von Teams zu erstellen, um moderne, intelligente Lösungen für die Kunden- und Agentverbindung für die Zusammenarbeit zu bieten. Das Ziel von "Extend" und "Power" ist es, die Kreativität von Entwicklern zu fördern und die Produktivität von Kunden zu fördern.

Durch die direkte Nutzung von Azure können Partner ihre Lösung schnell in allen Regionen und Regionen von Teams bereitstellen und bereitstellen, wobei sie von unserem gemeinsamen, globalen Kommunikationsnetzwerk profitieren und gleichzeitig die Speicher-, Rechen- und Analysefunktionen von Azure & Cognitive Services nutzen.

Mit dem Erweiterungs- und Power-Integrationsmodell können Partner Kontaktcentermitarbeitern Kommunikationserfahrungen über den Kanal bieten und dabei künstliche Intelligenz integrieren, um anzupassen, wie und wann Teilnehmer – oder andere Dienste – mit der [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)an einem Anruf beteiligt sind.

**Feature-Highlights:**

Im Folgenden finden Sie zwar keine vollständige Liste der Featurefunktionen für dieses Integrationsmodell, aber diese Hervorhebungsbereiche werden zusätzlich zu den Bereichen hervorgehoben, die vom Connect- und Extend-Modell bereitgestellt werden.

  - Formale Mitarbeitererfahrungen, die nativ für die Kommunikation über den Kanal über das Teams SDK aktiviert wurden 

  - Verwenden von Teams Collaboration Services für die Zusammenarbeit von Agenten und Kundeninteraktionen  

  - Schnelle Bereitstellung von Clouddiensten, Bereitstellung überall 

  - Direkte Steuerung von Unterhaltungen und Interaktion mit Benutzern während Teams-Unterhaltungen 

### <a name="comparing-connected-contact-center-integration-models"></a>Vergleich der Integrationsmodelle für verbundene Kontaktcenter

In der nachstehenden Tabelle finden Sie eine Übersicht über die Integrationsmodelle, die Microsoft Teams unterstützt.

<table>
<thead>
<tr class="header">
<th></th>
<th>Teams-Sprach-Apps</th>
<th>Verbinden</th>
<th>Erweitern</th>
<th>Ein/Aus</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Clouddienstmodell</td>
<td>Azure</td>
<td>Partner</td>
<td><p>Partner +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>Wer betreibt die Lösung?</td>
<td>Microsoft</td>
<td>Partner</td>
<td>Partner</td>
<td>Partner</td>
</tr>
<tr class="odd">
<td>M365-Anmeldung</td>
<td>Ja</td>
<td>Ja</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>Benutzer mit Anrufen in Teams?</td>
<td>Informell, AUSTAUSCH</td>
<td>Informell, AUSTAUSCH</td>
<td>Informell, AUSTAUSCH, Formal</td>
<td>Informell, AUSTAUSCH, Formal</td>
</tr>
<tr class="odd">
<td>IW/NICHT-ERFAHRUNG</td>
<td>Microsoft Teams</td>
<td>Microsoft Teams</td>
<td><p>Teams +</p>
<p>Erweiterungen</p></td>
<td><p>Teams +</p>
<p>Erweiterungen</p></td>
</tr>
<tr class="even">
<td>Dienstkonnektivität</td>
<td>Plattform<br />
(Anrufpläne +DR)</td>
<td>Direktes Routing</td>
<td>Plattform<br />
(Anrufpläne + DR)</td>
<td>Plattform<br />
(Anrufpläne + DR)</td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie ein Anbieter sind, der am Zertifizierungsprogramm teilnehmen möchten, senden Sie eine <Teamscategorypartner@microsoft.com> E-Mail.
