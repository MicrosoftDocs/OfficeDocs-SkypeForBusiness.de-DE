---
title: Microsoft-Teams, Aufbewahrungsrichtlinien – häufig gestellte Fragen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Häufig gestellte Fragen zu Aufbewahrungsrichtlinien in Microsoft-Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7597565afcd63872554e867d8f68929a3e214538
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461020"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft-Teams, Aufbewahrungsrichtlinien – häufig gestellte Fragen

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Welche Arten von Richtlinien kann ich in eingerichtet Aufbewahrungsrichtlinien und wie funktionieren?

In der & Security Compliance Center beim Einrichten einer Aufbewahrungsrichtlinie für Teams oder für alle anderen Arbeitslasten können Sie zwei Haupttypen von Richtlinien einrichten: 
- Permanentes: Diese Richtlinien sicher, dass Ihre Daten für einen bestimmten Zeitraum, unabhängig davon, was, in den Tools für die Endbenutzer geschieht beibehalten werden. Sie stellen Sie sicher, dass Daten aus Gründen der Einhaltung von Bestimmungen beibehalten werden und in eDiscovery bis zu diesem Zeitpunkt verfügbar läuft ab. Nach Ablauf die Zeit kann Ihre Richtlinie angeben, ob nichts Unternehmen oder Löschen der Daten. In Teams Wenn Sie eine Beibehaltung der Richtlinie für 7 Jahre erstellen, auch wenn Endbenutzer ihre Nachrichten Teams löschen werden diese Nachrichten weiterhin für eDiscovery für 7 Jahre beibehalten.
- Löschvorgang: Diese Richtlinien sicherstellen, dass Daten keine Haftung für Ihre Organisation. Nach der angegebenen Dauer werden Daten aus allen relevanten Speicher in Teams gelöscht. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Können wir die Teams im Org geltende Richtlinien werden? 

Nein, derzeit nicht. Sie müssen bestimmte Richtlinien für Teams Chat und Channel-Nachrichten mithilfe der Teams Speicherort Zeile oder diese Teams Cmdlets erstellen: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Diese Cmdlets Get haben, und legen Sie auch Versionen.

### <a name="are-these-retention-policies-retroactive"></a>Sind die folgenden Aufbewahrungsrichtlinien rückwirkende? 

Ja, Sie sind. Wenn Sie eine Aufbewahrungsrichtlinie zum Löschen von Daten, die älter als 60 Tage erstellen, wird vor mehr als 60 Tagen erstellte Teams Daten gelöscht. 

### <a name="what-is-the-default-retention-policy"></a>Was ist Standardaufbewahrungsrichtlinie? 

Standardmäßig werden Teams Chat, DDE-Kanal und Dateien Daten für immer beibehalten. Ein Benutzer kann etwas löschen, aber keine von Aufbewahrungsrichtlinien, Teams Daten werden immer in Exchange online-Postfächern (Benutzer und Gruppen) archiviert, und bleiben Sie dort für eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Kann ich Gruppen von Benutzern oder Teams in einer Richtlinie bereitgestellt? 

Ja, gehen Sie vor. Im Assistenten zum Erstellen von Richtlinien im Schritt Speicherorte können einschließen oder Ausschließen von Teams (**Teams channel Nachrichten**) oder Benutzer (**Teams Chat**) und gezielte Richtlinien für Ihre Organisation erstellen. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Was ist der Hauptunterschied zwischen der Verwendung der Gruppe Postfach Speicherort Zeile und Teams Channel Nachrichten Speicherort Zeile in Aufbewahrungsrichtlinien? 

Wenn Sie die Gruppenpostfach und Benutzer Postfach Speicherort Zeilen für Exchange Online verwenden, werden aus der angegebenen Postfächer Teams Daten gelöscht werden. Jedoch entfernt dies nur Daten aus dem Postfach. Es wird anderen Teams Daten, beispielsweise Chats Dienst nicht gelöscht. Es wird empfohlen, dass Sie Aufbewahrungsrichtlinien Teams verwenden, um alle Teams Daten ordnungsgemäß zu verwalten. Eine Aufbewahrungsrichtlinie Teams entfernt Teams Daten aus allen Speicherorten – Postfächer, Chat Speicherdienst, Teams Clients. 

Hinweis: Starten des Retention Policies Features für Teams stellt sicher, dass nur Teams Richtlinien innerhalb der Exchange-Postfach Speicherorte (Benutzer oder Gruppe) gespeicherten Teams Elemente löschen. Andere Richtlinien von Setup auf Postfächer kann nicht Teams Elemente auswirken. Dies wurde in der Vergangenheit true, aber mit der Einführung der Richtlinien aufbewahrungsfeature behoben wurde. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Was geschieht mit Skype für Business Online und Teams interop Chats – sie von Aufbewahrungsrichtlinien betroffen sind?

Ja, Skype für Business Online und Teams interop Chats die gleiche Weise arbeiten. Nachdem die Skype für Business Online Chat in Teams stammt, wird eine Meldung in einem Teams Chat Thread und ruft in das entsprechende Postfach aufgenommen. Damit die gleiche Works – flow löscht Teams Löschrichtlinien diese Nachrichten aus der Teams Thread. Jedoch ist wenn aufgezeichnete für Skype für Business Online eingeschaltet ist und aus der Skype für Business Online Clientseite die in einem Postfach gespeichert werden werden, diese chatdaten nicht durch eine Aufbewahrungsrichtlinie Teams behandelt.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Kann ich diese über Sicherheit & Compliance Center Cmdlets? Was soll ich verwenden? 

Absolut. Sie können Teams Aufbewahrungsrichtlinien mit [Sicherheit & Compliance Center Powershell-Cmdlets]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)erstellen. Denken Sie daran, dass diese nicht über Exchange Online-Cmdlets sind. Hier werden die Cmdlets, die wir für Teams erstellt haben. Sie führen Sie die vorhandenen Nomenklatur und Formatieren von Aufbewahrung Cmdlets heute in Security & Compliance Center verfügbar.

|Richtlinie|Regel|
|---|---|
|[Neue TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Neue TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Wenn es mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Dauer sind, welche wins?

Es folgen [Prinzipien von Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), und es wird empfohlen, dass Sie zu tun. Die Antwort ist: 
-   Permanentes immer im Wettbewerb löschen
-   Wins-längste immer Beibehaltung der Periode
-   Ausdrückliche Inklusion im Wettbewerb implizite Inklusion im Hinblick auf Speicherorte
-   Kürzeste Löschung Period wins
