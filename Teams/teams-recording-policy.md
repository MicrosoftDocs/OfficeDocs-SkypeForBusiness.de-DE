---
title: Einführung in Teams richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über Teams richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen
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
ms.openlocfilehash: b9b12d77823f6fcf5417370b496507b627858c6c
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681986"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Einführung in Teams richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen

Mithilfe einer richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen einführen, mithilfe einer Administrativen Richtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies durch die jeweilige Unternehmens- oder Behördliche Richtlinie erforderlich ist.

Teams wurde verbessert, um die Integration von Aufzeichnungslösungen von Drittanbietern zu unterstützen, einschließlich plattformbasierter Funktionen, Benutzeroberflächen und Verwaltungsschnittstellen, die erforderlich sind, um eine End-to-End-Lösung zum Konfigurieren, Verwalten, Aufzeichnen, Speichern und Analysieren Teams Kommunikation bereitzustellen. Verbesserungen umfassen ApIs und Ereignisse für die Kommunikationsplattform für die Aufzeichnung, die Folgendes bieten:

- Nahtlose, hochwertige Medienaufnahme auf allen Geräten und allen unterstützten Endpunkten für Audio, Video, Bildschirmfreigabe und Chat.

- Unterstützung für die Interaktionserfassung zwischen Teams Benutzern und unterstützten Anrufendpunkten (Teams, Teams Mobile, Skype for Business, PSTN)

- Neue administrative Richtlinien für die Complianceaufzeichnung, einschließlich der Integration in vorhandene Teams administrative Anruf- und Besprechungstools und -richtlinien

Die Complianceaufzeichnung kann für benutzer mit Microsoft 365 A3/A5/E3/E5/Business Premium und Office 365 A3/A5/E3/E5 aktiviert werden. 

Die Integrationsfunktionen der Complianceaufzeichnungslösung wurden auch auf der Ignite 2019 in der [Sitzung zur Complianceaufzeichnung und Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40) überprüft.

## <a name="teams-interaction-recording-overview"></a>Übersicht über Teams-Interaktionsaufzeichnung

Anwendungsfälle für die Interaktionsaufzeichnung können effektiv in vier Hauptkategorien von Aufzeichnungsfunktionen unterteilt werden: Komfort, Funktionalität, organisatorische und rechtmäßige Überwachung, wie in der Abbildung dargestellt:

> [!div class="mx-imgBorder"]
> ![Screenshot der Interaktionsaufzeichnung, was und warum.](media/recording-taxonomy.png "Die Abbildung zeigt die Aufnahmekategorien.")

Jede der Kategorien umfasst unterschiedliche Anforderungen an die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.

| Typ                   | Komfort (normale Teams-Aufzeichnung) | Organisation – reguliert (Compliance-Aufzeichnung) |
| ---------------------- | ------------------ | --------------- |
| Initiator              | Benutzer               | Admin (System)  |
| Target                 | Anruf pro Anruf/Besprechung | Benutzerspezifische Richtlinie        |
| Storage Besitzer          | Benutzer               | Compliance      |
| Benachrichtigung erforderlich? | Ja                | Ja             |
| Access-Besitzer           | Benutzer               | Compliance      |
| Aufbewahrungsrichtlinie?      | Optional           | Ja             |

Teams bietet verschiedene Funktionen für [die bequeme](./cloud-recording.md) und funktionale Aufzeichnung von Besprechungen und Liveereignissen. Die Aufzeichnung von Organisationen bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen annehmen, durch eine Administrative Richtlinie festlegen können, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies durch die jeweilige Unternehmens- oder Regulierungsrichtlinie erforderlich ist. Benutzer im Rahmen dieser Richtlinie wissen, dass ihre digitalen Interaktionen mit Teams aufgezeichnet werden, die Aufzeichnung jedoch nicht deaktivieren können und keinen Zugriff auf die Aufzeichnung haben, sobald die Interaktion abgeschlossen ist. Die Aufzeichnung wird Teil des Organisationsarchivs, das Compliance- und Juristischen Mitarbeitern für eDiscovery, gesetzliche Aufbewahrungspflichten und andere Aufbewahrungsverwendungen im Unternehmen zur Verfügung steht.

## <a name="example-user-needs"></a>Beispiel für Benutzeranforderungen

<table>
<thead>
<tr class="header">
<th>Persona</th>
<th>Bedürfnisse</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aufgezeichnete Benutzer</td>
<td><ul>
<li><p>Werden Sie benachrichtigt, wenn die Aufzeichnung ausgeführt wird.</p></li>
<li><p>Informieren Sie sich, wenn Richtlinien- und/oder Aufzeichnungsfehler Änderungen am Anrufverhalten verursachen.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Kommunikationsadministrator</td>
<td><ul>
<li><p>Verstehen Sie, warum und wie Sie Aufzeichnungsrichtlinien auf Teams Benutzer/Endpunkte anwenden/erzwingen.</p></li>
<li><p>Konfigurieren und Verwalten Teams Aufzeichnungsrichtlinien für die Organisation.</p></li>
<li><p>Überwachen und Behandeln von Aufzeichnungsproblemen bei Teams Anrufen und Besprechungen.</p></li>
<li><p>Unterstützen Sie den internen Compliance Officer mit Betriebsanalysen zu Nutzung, Qualität und Zuverlässigkeit.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Compliance Officer</td>
<td><ul>
<li><p>Sammeln Sie alle Teams Kommunikationen auf die Art und Weise, die erforderlich ist, um compliance-Verpflichtungen in den entsprechenden regionalen Grenzen zu erfüllen.</p></li>
<li><p>Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktionsinhalten. Häufige Beispiele sind:</p>
<ul>
<li><p><strong>Metadaten</strong> - Teilnehmer, Uhrzeit, Richtung, gewählte Nummer, Ursprungsnummer, benutzerdefinierte Geschäftsdaten</p></li>
<li><p><strong>Inhalt</strong> – Transkription, Gefühl, Phonetik, verwandte Interaktionen</p></li>
</ul></li>
<li><p>Analysieren und interagieren Sie mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während der Erfassung zu überwachen.</p></li>
<li><p>Stellen Sie die Sicherheit der gesammelten Kommunikation sicher und verhindern Sie Manipulationen in allen Phasen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Übersicht über die Lösungsarchitektur

Complianceaufzeichnungslösungen sind in Teams integriert, wie im folgenden Diagramm dargestellt:

> [!div class="mx-imgBorder"]
> ![Screenshot der benutzerdefinierten Team-App-Einstellung.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss, wenn eine Teams Besprechung oder ein Anruf gesendet und empfangen wird.")

> [!NOTE]
> Diese Lösung wurde speziell entwickelt, um richtlinienbasierte Complianceaufzeichnungen mit Teams zu ermöglichen. Jede andere Verwendung dieser Lösung wird nicht unterstützt.

## <a name="recorder"></a>Recorder

Die Kernkomponente der Compliance-Aufzeichnungslösung ist die Aufzeichnung.
Recorder werden als skalierbare Azure-basierte Dienste (Bots) erstellt, die die [Kommunikationsplattform von Microsoft verwenden](/graph/cloud-communications-concept-overview) und sich als Anwendungen bei Microsoft Graph registrieren. Die Aufzeichnung bietet die direkte Interaktion mit den [APIs der Teams-Kommunikationsplattform](/graph/api/resources/communications-api-overview) für Anrufe und Besprechungen und stellt den Endpunkt für die Medienaufnahme bereit.

Es [ist eine Beispielanwendung für die Complianceaufzeichnung verfügbar](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , die zeigt, wie Sie den Bot konfigurieren, die App-Instanz erstellen und die Compliancerichtlinien zuweisen. Das Beispiel enthält auch Beispiele für die API-Verwendung für die Aufzeichnung spezifischer Interaktionen wie die Behandlung des Routings [eingehender Anrufe](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [das Ändern des Aufzeichnungsstatus](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) und [das Entfernen des Benutzers, der aufgezeichnet wird](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph Dokumentation zu den spezifischen APIs finden Sie hier für [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) und [incomingContext](/graph/api/resources/incomingcontext).

Die genaue Implementierung des Aufzeichnungsdiensts variiert je nach Partner, muss jedoch so konzipiert sein, dass mehrere Recorder unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erreichen, um die Latenz von Teams zum Recorder zu verringern. Außerdem wird erwartet, dass recorders selbst unter Berücksichtigung von Resilienz und Redundanz konzipiert werden.

Partner müssen die mindestens erforderliche Version der Microsoft Graph Kommunikations-APIs und SDKs mit Microsoft bestätigen, bevor sie ihre Lösung zur Zertifizierung übermitteln, um sicherzustellen, dass alle Anforderungen der Integration von Complianceaufzeichnungen unterstützt werden.

Zwei spezifische Anforderungen, die für das Szenario der Complianceaufzeichnung von grundlegender Bedeutung sind:

- Recorder-Bot muss in Azure bereitgestellt werden

- Recorder-Bot muss auf einer Windows VM in Azure ausgeführt werden

Die Azure- und Windows VM-Anforderungen gelten nur für die Teams Bot-Komponente, was bedeutet, dass ein Partner den Rest der Plattform seiner Wahl implementieren kann, sofern er die relevanten Leistungs- und Funktionsanforderungen für die Complianceaufzeichnung erfüllen kann.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Zuweisung und Bereitstellung von Richtlinien für Die Complianceaufzeichnung

IT-Administratoren können ermitteln, welche Benutzer aufgezeichnet werden sollen und welche Aufzeichnung für jeden Benutzer verwendet wird, indem sie Richtlinien für die Complianceaufzeichnung erstellen und zuweisen. Aufzeichnungsgeräte werden automatisch eingeladen, an Unterhaltungen teilzunehmen, basierend auf der Konfiguration dieser Richtlinien, wenn eine Kommunikationsinteraktion stattfindet. Richtlinien für die Complianceaufzeichnung werden [mithilfe von Microsoft PowerShell](./teams-powershell-overview.md) verwaltet und können auf Mandanten-, Benutzer- und Sicherheitsgruppenebene für jede Organisation angewendet werden. Weitere Informationen zu Microsoft-Dokumentation für [Besprechungsrichtlinien](./meeting-policies-overview.md), [Anrufrichtlinien](./teams-calling-policy.md) und [Gruppenrichtlinien](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group) finden Sie.

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

   Siehe [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Weisen Sie die Richtlinie für die Complianceaufzeichnung einem Benutzer zu.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Siehe [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Benutzererfahrungen

Die Unterstützung für Benachrichtigungen wird mithilfe der Teams-Clientumgebungen aktiviert. Die Oberflächen können visuell oder audio sein.

**Teams Clients – visueller Hinweis**
- Desktop/Web
- Mobil (iOS/Android)
- Teams Smartphones
- Teams Räume

**Andere Endpunkte – Audiohinweis**
- SIP-Telefone
- Skype for Business
- Audiokonferenz
- PSTN-Anrufer

> [!NOTE]
> Die Complianceaufzeichnung wird bei Anrufwarteschleifen im Konferenzmodus nicht unterstützt. Verwenden Sie Anrufwarteschleifen im Übertragungsmodus.
> Die Complianceaufzeichnung funktioniert nicht, wenn Benutzer einen Internetausfall erlebt haben und PSTN-Anrufe mithilfe einer SBA tätigen und empfangen.

## <a name="compliance-recording-for-teams-certification-programs"></a>Complianceaufzeichnung für Teams Zertifizierungsprogramme

Neben der Veröffentlichung öffentlich verfügbarer APIs, die Es Partnern ermöglichen, CCaaS-Lösungen mit Teams zu entwickeln und zu integrieren, haben wir die Complianceaufzeichnung für Microsoft Teams Zertifizierungsprogramm entwickelt, um Kunden die Sicherheit zu bieten, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die Qualität, Kompatibilität und Zuverlässigkeit bereitzustellen, die sie von Microsoft-Lösungen erwarten.  

Die folgenden Partner haben ihre Lösung für Microsoft Teams zertifiziert.<br/><br/>

|Partner|Lösungswebsite |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|Audiocodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Synchronsprecher |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Aufschlussreiche Technologie |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Rotes Feld |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta See |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Die folgenden Partner sind dabei, ihre Lösung für Microsoft Teams zu zertifizieren.<br/><br/>

|Partner|Lösungswebsite |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


Diese Liste wird aktualisiert, wenn weitere Partner beitreten und die Zertifizierungskriterien erfüllen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie ein Anbieter sind, der am Zertifizierungsprogramm teilnehmen möchte, senden Sie E-Mails an [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
