---
title: Einführung in die richtlinienbasierte Aufzeichnung von Teams für den Anruf & Besprechungen
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informationen zu Teamrichtlinien basierter Aufzeichnung für den Anruf & Besprechungen
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294050"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Einführung in die richtlinienbasierte Aufzeichnung von Teams für Anrufe & Besprechungen

Mithilfe einer richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen übernehmen, unter Verwendung einer Verwaltungsrichtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies in den entsprechenden Unternehmens-oder Aufsichtsrichtlinien erforderlich ist.

Teams wurden verbessert, um die Integration von Drittanbieter-Aufzeichnungslösungen zu unterstützen, einschließlich der Plattformfunktionen, Benutzer Erfahrungen und administrativen Schnittstellen, die für die Bereitstellung einer End-to-End-Lösung für die Konfiguration, Verwaltung, Aufzeichnung, Speicherung und Analyse von Teams-Kommunikationen erforderlich sind. Dazu gehören Kommunikationsplattform-APIs und Ereignisse für die Aufzeichnung, die Folgendes bietet:

- Nahtlose, qualitativ hochwertige Medien Erfassung auf allen Geräten und alle unterstützten Endpunkte für Audio, Video, Bildschirmfreigabe und Chat.

- Unterstützung für die Interaktions Erfassung zwischen Teams-Benutzern und unterstützten Anruf Endpunkten (Teams, Mobile Teams, Skype for Business, PSTN)

- Neue administrative Richtlinien für die Konformitäts Aufzeichnung, einschließlich der Integration in vorhandene Teams administrative Anruf-und Besprechungstools und-Richtlinien

- Für Benutzer von Teams mit einer separaten Lizenz aktiviert

Die Integrationsfunktionen der Kompatibilitäts Aufzeichnung wurden auch bei Ignite 2019 in der [<span class="underline">Sitzung Compliance Recording und Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)überprüft.

## <a name="teams-interaction-recording-overview"></a>Übersicht über die Interaktions Aufzeichnung für Teams

Anwendungsfälle für die Interaktions Aufzeichnung können effektiv in vier primäre Kategorien von Aufzeichnungsfunktionen aufgeteilt werden – Bequemlichkeit, funktionelle, organisatorische und rechtmäßige abfangfunktion, wie in der Abbildung dargestellt:

![Screenshot der Interaktions Aufzeichnung was und warum.](media/recording-taxonomy.png "Das Bild zeigt die Aufzeichnungs Kategorien.")

Jede der Kategorien umfasst unterschiedliche Anforderungen für die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.

|                        | Komfort        | Funktions         | Org-allgemein      | Org-reguliert | Rechtmäßiger Abschnitt   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Initiator              | Benutzer               | App/Lösung       | Administrator (System)     | Administrator (System)  | Lea                |
|  Target                 | Pro Anruf/Besprechung | Pro Anruf/Besprechung | Pro Anruf/Besprechung | Pro Benutzer        | Pro Endpunkt/did |
| Speicher Besitzer          | Benutzer               | App                | Admin              | Compliance      | Lea                |
| Benachrichtigung erforderlich? | Ja                 | Ja                 | Ja                 | Ja             | Nein                 |
| Zugriffs Besitzer           | Benutzer               | App                | Admin              | Compliance      | Lea                |
| Aufbewahrungsrichtlinie?      | Optional           | Ja                 | Ja                 | Ja              | Ja                |

Teams bietet verschiedene Funktionen für die [<span class="underline">bequeme</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) und funktionelle Aufzeichnung für Besprechungen und Live-Events. Die organisatorische Aufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen einführen, in einer administrativen Richtlinie festlegen können, ob Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung nach Maßgabe der einschlägigen Unternehmens-oder Aufsichtsrichtlinien festgelegt werden sollen. Benutzern, die dieser Richtlinie unterliegen, ist bewusst, dass Ihre digitalen Interaktionen mit Teams aufgezeichnet werden, Sie aber nicht in der Lage sind, die Aufzeichnung zu deaktivieren, und nach Abschluss der Interaktion keinen Zugriff auf die Aufzeichnung hat. Die Aufzeichnung wird Teil des Organisations Archivs, das Compliance-und juristischen Personen für eDiscovery, rechtliche Aufbewahrung und andere Unternehmens Aufbewahrungszwecke zur Verfügung steht.

## <a name="example-user-needs"></a>Beispiel für Benutzeranforderungen

<table>
<thead>
<tr class="header">
<th><strong>Persona</strong></th>
<th><strong>Muss</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aufgezeichnete Benutzer</td>
<td><ul>
<li><p>Benachrichtigt werden, wenn die Aufzeichnung gerade ausgeführt wird.</p></li>
<li><p>Informieren Sie sich, wenn der Richtlinien-und/oder Rekorder-Fehler Änderungen beim Anrufverhalten verursacht.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Kommunikations Administrator</td>
<td><ul>
<li><p>Erläutern Sie, warum und wie Sie Aufzeichnungs Richtlinien für Benutzer/Endpunkte von Teams anwenden/erzwingen.</p></li>
<li><p>Konfigurieren und Verwalten von Teams zum Aufzeichnen von Richtlinien für die Organisation</p></li>
<li><p>Überwachen und behandeln von Problemen mit der Aufzeichnung bei Anrufen und Besprechungen in Teams.</p></li>
<li><p>Unterstützen Sie den internen Compliance Officer mit betrieblichen Analysen zu Nutzung, Qualität und Zuverlässigkeit.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Compliance Officer</td>
<td><ul>
<li><p>Sammeln Sie alle Teams-Kommunikationen in der Weise, die erforderlich ist, um Compliance-Verpflichtungen in angemessenen regionalen Grenzen zu erfüllen.</p></li>
<li><p>Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktions Inhalten. Gängige Beispiele sind:</p>
<ul>
<li><p><strong>Metadaten</strong> - Teilnehmer, Zeit, Richtung, gewählte Nummer, Herkunftsnummer, benutzerdefinierte Geschäftsdaten</p></li>
<li><p><strong>Inhalt</strong> – Transkription, Sentiment, Phonetik, Verwandte Interaktionen</p></li>
</ul></li>
<li><p>Analysieren und interagieren Sie mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während der Erfassung zu überwachen.</p></li>
<li><p>Sicherstellen der Sicherheit der gesammelten Kommunikation und verhindern von Manipulationen in allen Phasen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Übersicht über die Lösungsarchitektur

Lösungen für die Compliance-Aufzeichnung sind in Teams integriert, wie in der folgenden Abbildung dargestellt:

![Screenshot mit der Einstellung "benutzerdefinierte App für Team"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss an, wenn eine Teams-Besprechung oder ein Anruf gesendet und empfangen wird.")

## <a name="recorder"></a>Recorder

Die wichtigste Komponente der Compliance-Aufzeichnungslösung ist die Aufzeichnung.
Datenschreiber sind als skalierbare Azure-based Services (Bots) konzipiert, die die [<span class="underline">Kommunikationsplattform von Microsoft nutzen</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) und sich als Anwendungen mit Microsoft Graph registrieren. Der Recorder bietet die direkte Interaktion mit den Teams für Anrufe und Besprechungen der [<span class="underline">Kommunikationsplattform-APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) und stellt den Endpunkt für die Medien aufnahmebereit.

Eine [<span class="underline">Beispielanwendung für Compliance-Recorder steht zur Verfügung</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , die zeigt, wie der bot konfiguriert, die app-Instanz erstellt und die Konformitätsrichtlinien zugewiesen werden. Das Beispiel enthält auch Beispiele für die API-Verwendung für die Aufzeichnung bestimmter Interaktionen, beispielsweise die Behandlung des [<span class="underline">eingehenden Anruf</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   Routings, [<span class="underline">Ändern der Aufnahme Zustände</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)und [<span class="underline">Entfernen des Benutzers, der aufgezeichnet wird</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph-Dokumentation zu den spezifischen APIs finden Sie hier für [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) und [<span class="underline">incomingcontext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

Die genaue Implementierung des Recorder-Diensts variiert je nach Partner, muss aber so konzipiert sein, dass mehrere Datenschreiber unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erreichen, um die Latenz von Teams auf die Aufzeichnung zu verringern. Außerdem wird davon ausgegangen, dass die Datenschreiber selbst mit Flexibilität und Redundanz konzipiert sind.

Partner müssen die mindestens erforderliche Veröffentlichungsversion der Microsoft Graph Communications-APIs und-SDKs mit Microsoft bestätigen, bevor Sie Ihre Lösung für die Zertifizierung übermitteln, um sicherzustellen, dass alle Anforderungen der Integration der Konformitäts Aufzeichnung unterstützt werden.

Zwei spezifische Anforderungen, die für das Szenario der Konformitäts Aufzeichnung grundlegend sind, sind:

- Recorder-bot muss in Azure bereitgestellt werden

- Der Recorder-bot muss auf einer Windows-VM in Azure ausgeführt werden

Die Azure-und Windows-VM-Anforderungen gelten nur für die Teams-bot-Komponente, was bedeutet, dass ein Partner die restliche Plattform Ihrer Wahl implementieren kann, vorausgesetzt, Sie kann die relevanten Leistungs-und Funktionsanforderungen für die Compliance-Aufzeichnung erfüllen.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Richtlinienzuweisung und Bereitstellung von Compliance-Aufzeichnungen

IT-Administratoren können ermitteln, welche Benutzer aufgezeichnet werden und welche Aufzeichnung für jeden Benutzer verwendet werden soll, indem Sie Richtlinien für die Konformitäts Aufzeichnung erstellen und zuweisen. Datenschreiber werden automatisch zur Teilnahme an Unterhaltungen eingeladen, die auf der Konfiguration dieser Richtlinien basieren, wenn eine Kommunikations Interaktion stattfindet. Richtlinien für die Richtlinien Konformitäts Aufzeichnung werden mit [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) verwaltet und können für jede Organisation auf Mandanten-und Benutzerebene angewendet werden. Weitere Informationen zu Microsoft docs für [<span class="underline">Besprechungsrichtlinien</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) und [<span class="underline">Anruf Richtlinien</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)finden Sie hier.

1. Erstellen Sie eine Anwendungsinstanz in Ihrem Mandanten.

```powershell
PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
UserPrincipalName : cr.instance@contoso.onmicrosoft.com
ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
DisplayName       : ComplianceRecordingBotInstance
PhoneNumber       :
```

```powershell
PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

2. Erstellen einer Richtlinie für die Konformitäts Aufzeichnung

```powershell
PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

Identity                        : Global
ComplianceRecordingApplications : {}
Enabled                         : True
WarnUserOnRemoval               : True
Description                     : Test policy created by tenant admin
```

```powershell
PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
-ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Weisen Sie die Richtlinien für die Konformitäts Aufzeichnung einem Benutzer zu.

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a>Benutzererlebnisse

Die Unterstützung für Benachrichtigungen wird mithilfe der Erfahrungen des Teams-Clients aktiviert. Die Erfahrungen können entweder visuell oder Audio sein.

**Teams-Clients – visuelle Benachrichtigung**
- Desktop/Web
- Mobil (IOS/Android)
- Teams-Telefone
- Teams-Räume

**Andere Endpunkte-Audio-Hinweis**
- SIP-Telefone
- Skype for Business
- Audiokonferenz
- PSTN-Anrufer

## <a name="compliance-recording-for-teams-certification-programs"></a>Konformitäts Aufzeichnung für Teams-Zertifizierungsprogramme

Neben der Veröffentlichung öffentlich verfügbarer APIs, die Partnern die Entwicklung und Integration von CCaaS-Lösungen in Teams ermöglichen, haben wir das Zertifizierungsprogramm für die Compliance-Aufzeichnung für Microsoft Teams entwickelt, um Kunden die Gewissheit zu bieten, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die Qualität, Kompatibilität und Zuverlässigkeit zu gewährleisten, die Sie von Microsoft-Lösungen erwarten.  

Die folgenden Partner sind dabei, Ihre Lösung für Microsoft Teams zu zertifizieren.  

|Partner|Lösungs Website |
|:--|:--|
|ASC-Technologien |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Schön |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Rotes Feld |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Diese Liste wird aktualisiert, wenn weitere Partner teilnehmen und die Zertifizierungskriterien erfüllen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie ein Anbieter sind und versuchen, dem Zertifizierungsprogramm beizutreten, senden Sie <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@Microsoft.com</a>
