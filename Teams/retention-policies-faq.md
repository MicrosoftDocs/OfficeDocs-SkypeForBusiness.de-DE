---
title: Häufig gestellte Fragen zu Microsoft Teams-Aufbewahrungsrichtlinien
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Häufig gestellte Fragen zu Aufbewahrungsrichtlinien in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0eb556f53c617636f9169dbf0358455860c46b6
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018790"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Häufig gestellte Fragen zu Microsoft Teams-Aufbewahrungsrichtlinien

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Welche Arten von Richtlinien kann ich in Aufbewahrungsrichtlinien einrichten und wie funktionieren Sie?

Wenn Sie im Security #a0 Compliance Center eine Aufbewahrungsrichtlinie für Teams oder für andere Arbeitslasten einrichten, können Sie zwei Haupttypen von Richtlinien einrichten: 
- Bewahrung: mit diesen Richtlinien wird sichergestellt, dass Ihre Daten für einen bestimmten Zeitraum aufbewahrt werden, unabhängig davon, was in den Endbenutzertools geschieht. Sie stellen sicher, dass Daten aus Kompatibilitätsgründen aufbewahrt und in eDiscovery bis zu diesem Zeitpunkt verfügbar sind. Nach Ablauf der Zeit kann Ihre Richtlinie angeben, ob Sie nichts tun oder die Daten löschen möchten. Wenn Sie in Teams eine Erhaltungs Richtlinie für sieben Jahre erstellen, selbst wenn Endbenutzer ihre Teams-Nachrichten löschen, werden diese Nachrichten für eDiscovery sieben Jahre lang beibehalten.
- Löschen: mit diesen Richtlinien wird sichergestellt, dass Daten keine Haftung für Ihre Organisation darstellen. Nach der angegebenen Dauer werden die Daten aus allen relevanten Speicher in Teams gelöscht. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Können wir Teams in organisationsweite Richtlinien einbeziehen? 

Nein, zurzeit nicht. Sie müssen bestimmte Richtlinien für Teams-Chats und Kanal Nachrichten mithilfe der Teams-Standort Zeile oder dieser Teams-Cmdlets erstellen: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Diese Cmdlets verfügen auch über Get-und Sets-Versionen.

### <a name="are-these-retention-policies-retroactive"></a>Sind diese Aufbewahrungsrichtlinien rückwirkend? 

Ja, das sind Sie. Wenn Sie eine Aufbewahrungsrichtlinie erstellen, um Daten zu löschen, die älter als 60 Tage sind, werden die vor mehr als 60 Tagen erstellten Teams-Daten gelöscht. 

### <a name="what-is-the-default-retention-policy"></a>Was ist die Standardaufbewahrungsrichtlinie? 

Standardmäßig werden die Daten für Teams-Chat, Kanal und Dateien für immer aufbewahrt. Ein Benutzer kann etwas löschen, aber wenn keine Aufbewahrungsrichtlinien vorhanden sind, werden die Teams-Daten immer in Exchange Online-Postfächern (Benutzer und Gruppe) archiviert und bleiben für eDiscovery verfügbar. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Kann ich auf Gruppen von Benutzern oder Teams in einer Richtlinie abzielen? 

Ja, das ist möglich. Im Assistenten zum Erstellen von Richtlinien können Sie im Schritt Standorte Teams (Teams-**Kanal Nachrichten**) oder Benutzer (**Teamchat**) einbeziehen oder ausschließen und zielgerichtete Richtlinien für Ihre Organisation erstellen. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Was ist der Hauptunterschied zwischen der Verwendung der Zeile für den Speicherort des Gruppen Postfachs und der Zeile "Standort" des Teams Kanal Nachrichten in Aufbewahrungsrichtlinien? 

Wenn Sie die Zeilen für Gruppenpostfach und Benutzerpostfach für Exchange Online verwenden, werden die Teams-Daten aus den angegebenen Postfächern gelöscht. Dies entfernt jedoch nur Daten aus dem Postfach. Es werden keine anderen Teams-Daten wie Chats gelöscht. Wir empfehlen, dass Sie die Aufbewahrungsrichtlinien für Teams verwenden, um alle Team Daten ordnungsgemäß zu verwalten. Eine Aufbewahrungsrichtlinie für Teams entfernt Teams-Daten aus allen Speicherorten – Postfächer, Chat Dienst, Teams-Clients. 

Hinweis: durch Starten des Features Aufbewahrungsrichtlinien für Teams wird sichergestellt, dass nur Teams-Richtlinien Team Elemente löschen, die in Exchange-Postfachspeicher Orten (Benutzer oder Gruppe) gespeichert sind. Das Einrichten anderer Richtlinien für Postfächer kann keine Auswirkungen auf Team Elemente haben. Dies war in der Vergangenheit der Fall, wurde aber mit dem Start des Features "Aufbewahrungsrichtlinien" behoben. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Was passiert mit den Interop-Chats von Skype for Business Online und Teams – sind Sie von Aufbewahrungsrichtlinien betroffen?

Ja, Skype for Business Online und Teams-Interop-Chats funktionieren auf die gleiche Weise. Sobald der Skype for Business Online-Chat in Teams eingegangen ist, wird er in einem Teamchat-Thread zu einer Nachricht, die in das entsprechende Postfach aufgenommen wird. So funktioniert derselbe Flow – durch Löschrichtlinien für Teams werden diese Nachrichten aus dem teamthread gelöscht. Wenn jedoch das Unterhaltungsprotokoll für Skype for Business Online aktiviert ist und die Skype for Business Online-Clientseite in einem Postfach gespeichert wird, werden diese Chat-Daten nicht von einer Aufbewahrungsrichtlinie für Teams verarbeitet.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Kann ich diese mithilfe von Security #a0 Compliance Center-Cmdlets durchführen? Was sollte ich verwenden? 

Absolut. Sie können Teams-Aufbewahrungsrichtlinien mithilfe von [Security #a0 Compliance Center-PowerShell-Cmdlets]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)erstellen. Beachten Sie, dass es sich nicht um Exchange Online-Cmdlets handelt. Hier sind die für Teams erstellten Cmdlets. Sie folgen der vorhandenen Nomenklatur und dem Stil aus den heute verfügbaren Aufbewahrungs-Cmdlets im Security #a0 Compliance Center.

|Richtlinie|Regel|
|---|---|
|[Neu – TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Neu – TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Satz-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Satz-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Wenn es mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Dauer gibt, welche gewinnt man?

Wir befolgen [Grundsätze der Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), und wir empfehlen Ihnen, dies auch zu tun. Die kurze Antwort lautet: 
-   Beibehaltung gewinnt immer über Löschung
-   Der längste Aufbewahrungszeitraum gewinnt immer
-   Explizite Inklusion gewinnt über implizite Inklusion in Bezug auf Speicherorte
-   Kürzester Lösch Zeitraum gewinnt
