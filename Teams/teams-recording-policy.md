---
title: Einführung in die richtlinienbasierte Aufzeichnung von Teams für Anrufe & Besprechungen
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informationen zur richtlinienbasierten Aufzeichnung von Teams für Anrufe & Besprechungen
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
ms.openlocfilehash: 7972febeab134f0ec075418e351c35ef7e273fcf
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439670"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Einführung in die richtlinienbasierte Aufzeichnung von Anrufen & Besprechungen

Mithilfe einer richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen übernehmen, mithilfe einer Verwaltungsrichtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies in der relevanten Unternehmens- oder Aufsichtsrichtlinie erforderlich ist.

Teams wurde erweitert, um die Integration von Aufzeichnungslösungen von Drittanbietern zu unterstützen, einschließlich der Plattformfunktionen, Der Benutzererfahrungen und administrativen Schnittstellen, die erforderlich sind, um eine End-to-End-Lösung zum Konfigurieren, Verwalten, Aufzeichnen, Speichern und Analysieren von Teams-Kommunikationen bereitzustellen. Zu den Verbesserungen gehören APIs der Kommunikationsplattform und Ereignisse für die Aufzeichnung, die Folgendes bietet:

- Nahtlose, qualitativ hochwertige Medienaufnahme auf allen Geräten und allen unterstützten Endpunkten für Audio, Video, Bildschirmfreigabe und Chat.

- Unterstützung für die Interaktionserfassung zwischen Teams-Benutzern und unterstützten Anrufendpunkten (Teams, Teams Mobile, Skype for Business, PSTN)

- Neue Verwaltungsrichtlinien für die Complianceaufzeichnung, einschließlich der Integration in vorhandene Administrative Anrufe und Besprechungstools und -richtlinien von Teams

Die Complianceaufzeichnung kann für Benutzer von Microsoft 365 A3/A5/E3/E5/Business Premium und Office 365 A3/A5/E3/E5 aktiviert werden. 

Die Integrationsfunktionen der Complianceaufzeichnungslösung wurden auch auf Ignite 2019 in der [<span class="underline">Complianceaufzeichnungs- und Microsoft Teams-Sitzung überprüft.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Übersicht über die Aufzeichnung von Teams-Interaktionen

Verwendungsfälle für Interaktionsaufzeichnungen können effektiv in vier Hauptkategorien der Aufzeichnungsfunktion unterteilt werden: Convenience, Functional, Organizational und Lawful Intercept, wie in der Abbildung dargestellt:

![Screenshot mit der Interaktion, in der was und warum aufgezeichnet wird.](media/recording-taxonomy.png "Die Abbildung zeigt die Aufzeichnungskategorien.")

Jede der Kategorien enthält unterschiedliche Anforderungen an die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung behandelt wird.

| Typ                   | Komfort (normale Teams-Aufzeichnung) | Organisation – Reguliert (Complianceaufzeichnung) |
| ---------------------- | ------------------ | --------------- |
| Initiator              | Benutzer               | Administrator (System)  |
|  Target                 | Pro Anruf/Besprechung | Benutzerspezifische Richtlinie        |
| Speicherbesitzer          | Benutzer               | Compliance      |
| Benachrichtigung erforderlich? | Ja                | Ja             |
| Access Owner           | Benutzer               | Compliance      |
| Aufbewahrungsrichtlinie?      | Optional           | Ja             |

Teams bietet verschiedene Funktionen für die [<span class="underline">bequeme</span>](./cloud-recording.md) und funktionale Aufzeichnung für Besprechungen und Liveereignisse. Organisationsaufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen übernehmen, im Rahmen einer Verwaltungsrichtlinie festlegen können, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollten, wie dies in der relevanten Unternehmens- oder Aufsichtsrichtlinie erforderlich ist. Benutzern unter dieser Richtlinie ist bewusst, dass ihre digitalen Interaktionen mit Teams aufgezeichnet werden, die Aufzeichnung aber nicht deaktivieren können und nach Abschluss der Interaktion keinen Zugriff auf die Aufzeichnung haben. Die Aufzeichnung wird Teil des Organisationsarchivs, das compliance- und juristischen Mitarbeitern für eDiscovery, rechtliche Aufbewahrung und andere Verwendungen von Unternehmensaufbewahrung zur Verfügung steht.

## <a name="example-user-needs"></a>Beispiel für Benutzeranforderungen

<table>
<thead>
<tr class="header">
<th><strong>Persona</strong></th>
<th><strong>Anforderungen</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aufgezeichnete Benutzer</td>
<td><ul>
<li><p>Werden Sie benachrichtigt, wenn die Aufzeichnung ausgeführt wird.</p></li>
<li><p>Informieren Sie sich, wenn ein Richtlinien- und/oder Aufzeichnungsfehler Änderungen am Anrufverhalten verursacht.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Kommunikationsadministrator</td>
<td><ul>
<li><p>Verstehen Sie, warum und wie Aufzeichnungsrichtlinien auf Teams-Benutzer/-Endpunkte angewendet/erzwungen werden.</p></li>
<li><p>Konfigurieren und Verwalten von Teams-Aufzeichnungsrichtlinien für die Organisation.</p></li>
<li><p>Überwachen und Behandeln von Aufzeichnungsproblemen bei Anrufen und Besprechungen von Teams.</p></li>
<li><p>Unterstützen Sie den internen Compliance Officer mit betriebsinternen Analysen zu Nutzung, Qualität und Zuverlässigkeit.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Compliance Officer</td>
<td><ul>
<li><p>Sammeln Sie alle Teams-Kommunikationen auf die Weise, die erforderlich ist, um Complianceverpflichtungen in geeigneten regionalen Grenzen zu erfüllen.</p></li>
<li><p>Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktionsinhalten. Häufige Beispiele sind:</p>
<ul>
<li><p><strong>Metadaten</strong> - Teilnehmer, Uhrzeit, Richtung, gewählte Nummer, Ursprungsnummer, Benutzerdefinierte Geschäftsdaten</p></li>
<li><p><strong>Inhalt</strong> – Transkription, Stimmung, Phonetik, verwandte Interaktionen</p></li>
</ul></li>
<li><p>Analysieren und interagieren Sie mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während der Gesammelten zu überwachen.</p></li>
<li><p>Stellen Sie die Sicherheit der gesammelten Kommunikation sicher und verhindern Sie Manipulationen in allen Phasen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Übersicht über die Lösungsarchitektur

Complianceaufzeichnungslösungen sind in Teams integriert, wie in der folgenden Abbildung dargestellt:

![Screenshot mit der Einstellung der benutzerdefinierten Team-App](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss, wenn eine Teams-Besprechung oder ein Anruf gesendet und empfangen wird.")

## <a name="recorder"></a>Recorder

Die Kernkomponente der Lösung für die Complianceaufzeichnung ist der Recorder.
Recorder werden als skalierbare Azure-basierte Dienste (Bots) erstellt, die [<span class="underline">die Kommunikationsplattform</span>](/graph/cloud-communications-concept-overview) von Microsoft nutzen und sich als Anwendungen bei Microsoft Graph registrieren. Der Recorder bietet die direkte Interaktion mit den APIs der Kommunikationsplattform für Anrufe und [<span class="underline">Besprechungen</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) von Teams und stellt den Endpunkt für die Medienaufnahme zur Verfügung.

Es [<span class="underline">steht eine Beispielanwendung für die Complianceaufzeichnung</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) zur Verfügung, die zeigt, wie Sie den Bot konfigurieren, die App-Instanz erstellen und die Compliancerichtlinien zuweisen. Das Beispiel enthält auch Beispiele für die API-Verwendung zum Aufzeichnen bestimmter Interaktionen wie die Behandlung des Routings von eingehenden [<span class="underline">Anrufen,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)das Ändern von Aufzeichnungszuständen und das Entfernen des Benutzers, der [<span class="underline">aufgezeichnet wird.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)
Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).

Die genaue Implementierung des Aufzeichnungsdiensts variiert je nach Partner, muss jedoch so konzipiert sein, dass mehrere Aufzeichnungen unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erzielen, um die Latenz von Teams auf den Recorder zu verringern. Darüber hinaus wird erwartet, dass Die Aufzeichnungen selbst resilienz- und redundanzgemäß gestaltet werden.

Partner müssen die mindestens erforderliche Version der Microsoft Graph-Kommunikations-APIs und SDKs mit Microsoft bestätigen, bevor sie ihre Lösung zur Zertifizierung einreichen, um sicherzustellen, dass alle Anforderungen der Integration von Complianceaufzeichnungen unterstützt werden.

Zwei spezifische Anforderungen, die für das Szenario der Complianceaufzeichnung von grundlegender Bedeutung sind, sind:

- Recorder bot must be deployed in Azure

- Recorder bot must run on a Windows VM in Azure

Die Azure- und Windows-VM-Anforderungen gelten nur für die Komponente "Teams Bot", was bedeutet, dass ein Partner die restliche Plattform ihrer Wahl implementieren kann, sofern er die relevanten Leistungs- und Funktionsanforderungen für die Complianceaufzeichnung erfüllen kann.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Complianceaufzeichnungsrichtlinienzuordnung und -bereitstellung

IT-Administratoren können ermitteln, welche Benutzer aufgezeichnet werden sollen und welcher Recorder für jeden Benutzer verwendet werden soll, indem sie Richtlinien für die Complianceaufzeichnung erstellen und zuweisen. Aufzeichnungen werden automatisch zur Teilnahme an Unterhaltungen eingeladen, die auf der Konfiguration dieser Richtlinien basieren, wenn eine Kommunikationsinteraktion stattfindet. Richtlinien für die Complianceaufzeichnung werden mit [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) verwaltet und können auf Mandanten-, Benutzer- und Sicherheitsgruppenebene für jede Organisation angewendet werden. Weitere Informationen finden Sie unter Microsoft Docs für [<span class="underline">Besprechungsrichtlinien,</span>](./meeting-policies-in-teams.md) [<span class="underline">Aufrufen von Richtlinien und</span>](./teams-calling-policy.md) [<span class="underline">Gruppenrichtlinien.</span>](./assign-policies.md#assign-a-policy-to-a-group)

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

2. Erstellen Sie eine Richtlinie für die Complianceaufzeichnung.

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Weisen Sie die Richtlinie für die Complianceaufzeichnung einem Benutzer zu.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Benutzererfahrungen

Die Unterstützung für Benachrichtigungen wird mithilfe der Teams-Clienterfahrungen aktiviert. Die Benutzererfahrung kann entweder visuell oder audio sein.

**Teams-Clients – visuelle Hinweise**
- Desktop/Web
- Mobile Geräte (iOS/Android)
- Teams-Telefone
- Teams-Räume

**Andere Endpunkte – Audiohinweise**
- SIP-Telefone
- Skype for Business
- Audiokonferenz
- PSTN-Anrufer

## <a name="compliance-recording-for-teams-certification-programs"></a>Complianceaufzeichnung für Zertifizierungsprogramme für Teams

Neben der Veröffentlichung öffentlich verfügbarer APIs, mit denen Partner CCaaS-Lösungen in Teams entwickeln und integrieren können, haben wir die Complianceaufzeichnung für das Microsoft Teams-Zertifizierungsprogramm entwickelt, um Kunden die Sicherheit zu geben, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die Qualität, Kompatibilität und Zuverlässigkeit zu gewährleisten, die sie von #A0 erwarten.  

Die folgenden Partner haben ihre Lösung für Microsoft Teams zertifiziert.

|Partner|Lösungswebsite |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


Die folgenden Partner sind dabei, ihre Lösung für Microsoft Teams zu zertifizieren.

|Partner|Lösungswebsite |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Innovation in Der Eiche |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Rotes Feld |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

Diese Liste wird aktualisiert, sobald weitere Partner beitreten und die Zertifizierungskriterien erfüllen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie ein Anbieter sind, der am Zertifizierungsprogramm teilnehmen möchten, senden Sie eine  <a href= "mailto:Teamscategorypartner@microsoft.com">E-Mail an Teamscategorypartner@microsoft.com</a>.
