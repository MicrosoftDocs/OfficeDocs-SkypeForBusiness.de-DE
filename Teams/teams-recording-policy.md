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
ms.openlocfilehash: 2d8949a4eaa3365857768726a523ae480a94df55
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196769"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Einführung in die richtlinienbasierte Aufzeichnung von Anrufen und & Teams

Mithilfe richtlinienbasierter Aufzeichnungen können Organisationen, die Microsoft Teams für Anrufe und Besprechungen übernehmen, mithilfe einer Verwaltungsrichtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies durch die relevante Unternehmens- oder Gesetzliche Richtlinie vorgeschrieben ist.

Teams wurde verbessert, um die Integration von Aufnahmelösungen von Drittanbietern zu unterstützen, einschließlich der Plattformfunktionen, Benutzeroberflächen und Verwaltungsschnittstellen, die benötigt werden, um eine End-to-End-Lösung zum Konfigurieren, Verwalten, Aufzeichnen, Speichern und Analysieren der Kommunikation in Teams bereitzustellen. Zu den Verbesserungen gehören APIs für die Kommunikationsplattform und Ereignisse für die Aufzeichnung, die Folgendes bieten:

- Nahtlose, qualitativ hochwertige Medienaufzeichnung auf allen Geräten und allen unterstützten Endpunkten für Audio, Video, Bildschirmfreigabe und Chat.

- Unterstützung für die Erfassung von Interaktionen zwischen Teams-Benutzern und unterstützten Anrufendpunkten (Teams, Teams Mobile, Skype for Business, PSTN)

- Neue Administrative Richtlinien für die Complianceaufzeichnung, einschließlich integration in vorhandene Administrative Anruf- und Besprechungstools und Richtlinien für Teams

Die Complianceaufzeichnung kann für Benutzer von Microsoft 365 A3/A5/E3/E5/Business Premium und Office 365 A3/A5/E3/E5 aktiviert werden. 

Die Integrationsfunktionen der Lösung für die Complianceaufzeichnung wurden auch auf Ignite 2019 in der [<span class="underline">Sitzung "Complianceaufzeichnung" und "Microsoft Teams" überprüft.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Übersicht über die Aufzeichnung von Interaktionen in Teams

Die Verwendungsfälle für die Interaktionsaufzeichnung können effektiv in vier Hauptkategorien der Aufzeichnungsfunktion eingeteilt werden: Benutzerfreundlichkeit, Funktional, Organisationsgemäßes und rechtmäßiges Abfangen, wie in der Abbildung gezeigt:

![Screenshot der Interaktionsaufzeichnung, was und warum.](media/recording-taxonomy.png "Die Abbildung zeigt die Aufzeichnungskategorien.")

Jede der Kategorien umfasst unterschiedliche Anforderungen für die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.

| Typ                   | Komfort (normale Teams-Aufzeichnung) | Organisation – Reguliert (Complianceaufzeichnung) |
| ---------------------- | ------------------ | --------------- |
| Abt.              | Benutzer               | Administrator (System)  |
|  Target                 | Pro Anruf/Besprechung | Benutzerspezifische Richtlinie        |
| Speicherbesitzer          | Benutzer               | Compliance      |
| Benachrichtigung erforderlich? | Ja                | Ja             |
| Zugriffsbesitzer           | Benutzer               | Compliance      |
| Aufbewahrungsrichtlinie?      | Optional           | Ja             |

Teams bietet verschiedene Funktionen [<span class="underline">für</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) bequeme und funktionale Aufzeichnungen für Besprechungen und Liveereignisse. Organisationsaufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen übernehmen, im Rahmen einer Verwaltungsrichtlinie festlegen können, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies durch die relevante Unternehmens- oder Gesetzliche Richtlinie vorgeschrieben ist. Den Benutzern dieser Richtlinie ist bewusst, dass ihre digitalen Interaktionen mit Teams aufgezeichnet werden, sie können die Aufzeichnung aber nicht deaktivieren und haben keinen Zugriff auf die Aufzeichnung, sobald die Interaktion abgeschlossen ist. Die Aufzeichnung wird Teil des Organisationsarchivs, das Compliance- und Rechtsmitarbeitern für eDiscovery, gesetzliche Aufbewahrung und andere Unternehmensaufbewahrungsrichtlinien zur Verfügung stehen.

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
<li><p>Werden Sie benachrichtigt, wenn die Aufzeichnung läuft.</p></li>
<li><p>Seien Sie informiert, wenn ein Fehler in der Richtlinie und/oder dem Recorder Änderungen am Anrufverhalten verursacht.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Kommunikationsadministrator</td>
<td><ul>
<li><p>Verstehen Sie, warum und wie Aufzeichnungsrichtlinien auf Teams-Benutzer/-Endpunkte angewendet bzw. erzwungen werden.</p></li>
<li><p>Konfigurieren und verwalten Sie die Aufzeichnungsrichtlinien für Teams für die Organisation.</p></li>
<li><p>Überwachen und Behandeln von Aufzeichnungsproblemen bei Anrufen und Besprechungen in Teams.</p></li>
<li><p>Unterstützen Sie den internen Compliance Officer mit Betriebsanalysen zu Nutzung, Qualität und Zuverlässigkeit.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Compliance Officer</td>
<td><ul>
<li><p>Sammeln Sie alle Teams-Kommunikationen auf die Art und Weise, die zur Erfüllung von Complianceverpflichtungen in geeigneten regionalen Grenzen erforderlich ist.</p></li>
<li><p>Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktionsinhalten. Häufige Beispiele sind:</p>
<ul>
<li><p><strong>Metadaten</strong> - Teilnehmer, Zeit, Richtung, gewählte Nummer, Ursprungsnummer, benutzerdefinierte Geschäftsdaten</p></li>
<li><p><strong>Inhalt</strong> – Transkription, Stimmung, Lautschrift, zugehörige Interaktionen</p></li>
</ul></li>
<li><p>Analysieren und Interagieren mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während deren Datenübertragung zu überwachen.</p></li>
<li><p>Stellen Sie die Sicherheit gesammelter Kommunikationen sicher, und verhindern Sie Manipulationen auf allen Stufen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Übersicht über die Lösungsarchitektur

Lösungen für die Complianceaufzeichnung sind wie in der folgenden Abbildung dargestellt in Teams integriert:

![Screenshot der Benutzerdefinierten Team-App-Einstellung](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss, wenn eine Besprechung oder ein Anruf in Teams gesendet und empfangen wird.")

## <a name="recorder"></a>Recorder

Die Kernkomponente der Complianceaufzeichnungslösung ist die Aufzeichnungsaufzeichnung.
Recorder werden als skalierbare Azure-basierte Dienste (Bots) entwickelt, die die Kommunikationsplattform von [<span class="underline">Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) nutzen und sich als Anwendungen bei Microsoft Graph registrieren. Die Aufzeichnung ermöglicht die direkte Interaktion mit den [<span class="underline">APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) der Kommunikationsplattform für Anrufe und Besprechungen in Teams und stellt den Endpunkt für die Medienaufnahme zur Verfügung.

Eine [<span class="underline">Beispielanwendung für Complianceaufzeichnungen ist verfügbar,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) die zeigt, wie der Bot konfiguriert, die App-Instanz erstellt und die Compliancerichtlinien zugewiesen werden. Das Beispiel enthält außerdem Beispiele für die API-Verwendung zum Aufzeichnen bestimmter Interaktionen, z. B. Behandeln der Weiterleitung eingehender [<span class="underline">Anrufe,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)Ändern des Aufzeichnungszuständes und Entfernen des Benutzers, der [<span class="underline">aufgezeichnet wird.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)
Die Diagrammdokumentation zu den spezifischen APIs finden Sie hier für [<span class="underline">"updateRecordingStatus"</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) und [<span class="underline">"incomingContext".</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

Die genaue Implementierung des Recorderdiensts variiert je nach Partner, muss aber so konzipiert sein, dass mehrere Rekorder unterstützt werden, um eine hohe Verfügbarkeit und eine geografische Verteilung der Bereitstellung zu erzielen, um die Latenz von Teams auf die Aufnahmegeräte zu verringern. Darüber hinaus wird erwartet, dass die Aufzeichnungen selbst unter dem Bedenken von Resilienz und Redundanz entworfen werden.

Partner müssen die mindestens erforderliche Releaseversion der Microsoft Graph-Kommunikations-APIs und SDKs mit Microsoft bestätigen, bevor sie ihre Lösung zur Zertifizierung übermitteln, um sicherzustellen, dass alle Anforderungen der Integration von Complianceaufzeichnungen unterstützt werden.

Zwei spezielle Anforderungen, die für das Szenario der Complianceaufzeichnung von grundlegender Bedeutung sind:

- Recorder bot must be deployed in Azure

- Der Recorder Bot muss auf einer Windows VM in Azure ausgeführt werden.

Die Azure- und Windows VM-Anforderungen gelten nur für die Teams-Bot-Komponente. Das bedeutet, dass ein Partner die restliche Plattform seiner Wahl implementieren kann, sofern er die relevanten Leistungs- und Funktionsanforderungen für die Complianceaufzeichnung erfüllen kann.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Richtlinienzuweisung und Bereitstellung für complianceaufzeichnungsrichtlinien

IT-Administratoren können durch Erstellen und Zuweisen von Richtlinien für die Konformitätsaufzeichnung festlegen, welche Benutzer aufgezeichnet werden und welche Aufzeichnenden für jeden Benutzer verwendet werden sollen. Aufzeichnungsgeräte werden basierend auf der Konfiguration dieser Richtlinien automatisch zur Teilnahme an Unterhaltungen eingeladen, wenn eine Kommunikationsinteraktion stattfindet. Richtlinien für die Complianceaufzeichnung werden mithilfe [<span class="underline">von Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) verwaltet und können auf Mandanten-, Benutzer- und Sicherheitsgruppenebene für jede Organisation angewendet werden. Weitere Informationen zu Microsoft Docs [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)für Besprechungsrichtlinien, [<span class="underline">Anrufrichtlinien</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) und Gruppenrichtlinien finden [<span class="underline">Sie.</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Weisen Sie einem Benutzer die Richtlinie für die Complianceaufzeichnung zu.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Benutzeroberflächen

Die Unterstützung für Benachrichtigungen wird mithilfe der Teams-Clienterfahrungen aktiviert. Die Be erleben kann entweder visuell oder audio sein.

**Teams-Clients – visuelle Hinweise**
- Desktop/Web
- Mobil (iOS/Android)
- Telefone in Teams
- Teams -Räume

**Andere Endpunkte – Audiohinweise**
- SIP Phones
- Skype for Business
- Audiokonferenz
- Anrufe über das Festnetz

## <a name="compliance-recording-for-teams-certification-programs"></a>Complianceaufzeichnung für Zertifizierungsprogramme für Teams

Zusätzlich zur Veröffentlichung öffentlich verfügbarer APIs, die Partnern das Entwickeln und Integrieren von #A0 in Teams ermöglichen, haben wir die Complianceaufzeichnung für das Zertifizierungsprogramm von Microsoft Teams entwickelt, um Kunden die Bestätigung zu geben, dass die Lösung jedes teilnehmenden Partners getestet und verifiziert wurde, um die Qualität, Kompatibilität und Zuverlässigkeit zu bieten, die von #A1 erwartet wird.  

Die folgenden Partner haben ihre Lösung für Microsoft Teams zertifiziert.

|Partner|Website der Lösung |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


Die folgenden Partner sind dabei, ihre Lösung für Microsoft Teams zu zertifizieren.

|Partner|Website der Lösung |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Rotes Feld |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Diese Liste wird aktualisiert, sobald weitere Partner beitreten und die Zertifizierungskriterien erfüllen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie als Lieferant am Zertifizierungsprogramm teilnehmen möchten, senden Sie eine <a href= "mailto:Teamscategorypartner@microsoft.com">E-Mail an Teamscategorypartner@microsoft.com.</a>
