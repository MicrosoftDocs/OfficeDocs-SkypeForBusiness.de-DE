---
title: Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über das Microsoft Teams-Telefonsystem mit Direct Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269920"
---
# <a name="direct-routing"></a>Direct Routing

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt. Jetzt können Sie VoIP-Workloads hinzufügen, und Sie haben sich entschieden, Ihren eigenen Telefonieanbieter für PSTN-Verbindungen (Public Switched Telephone Network) mithilfe des Telefonsystems mit Direct Routing zu verwenden. Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Direct Routing sowie zusätzliche Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation berücksichtigen sollten. Lesen Sie auch ["Planen Ihrer VoIP-Lösung](cloud-voice-landing-page.md) ", um weitere Informationen zu den Sprachangeboten von Microsoft zu erhalten.

## <a name="learn-more-about-direct-routing"></a>Weitere Informationen zu Direct Routing

Die folgenden Artikel enthalten weitere Informationen zum Konfigurieren und Verwenden von Direct Routing. Das Konfigurieren von Direct Routing erfordert Kenntnisse des PSTN-Routingentwurfs. Lesen Sie alle diese Artikel, um zu verstehen, wie Sie Direct Routing planen und konfigurieren:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus können Sie die folgenden Artikel je nach Ihren Anforderungen lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Sehen Sie sich die folgende Sitzung an, um mehr über Direct Routing zu erfahren: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die wichtigsten Entscheidungen, die für Direct Routing zu berücksichtigen sind. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer wird Direct Routing aktiviert? | Weitere Informationen finden [Sie unter Aktivieren von Benutzern für den Direct Routing-Dienst](direct-routing-configure.md). |
Habe ich die erforderlichen Lizenzen für Direct Routing? | Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Überlegungen zum Session Border Controller (SBC)

Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen. Eine Liste der zertifizierten SBCs finden Sie unter ["Unterstützte Session Border Controller"](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie werden SBCs bereitgestellt? | Weitere Informationen finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md) | 
Habe ich mehrere Mandanten? | Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Überlegungen zum VoIP-Routing

Sie müssen das Telefonsystem so konfigurieren, dass die Anrufe an die jeweiligen SBCs weitergeleitet werden.

|Frage|Aktion |
|:------------|:-------|
| Welche VoIP-Routingrichtlinien, PSTN-Nutzung und VoIP-Routen muss ich erstellen? | Informationen zum VoIP-Routing finden [Sie unter Konfigurieren von VoIP-Routing](direct-routing-configure.md).
| Welche Benutzer werden der von mir definierten VoIP-Routingrichtlinie zugewiesen? | Siehe die Beispiele unter [Konfigurieren von VoIP-Routing](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Sicherstellen, dass eingehende Anrufe mithilfe von TeamsUpgradePolicy im Teams-Client landen

Direct Routing wird nur von Microsoft Teams unterstützt. Um PSTN-Anrufe über Direct Routing zu empfangen, müssen Sie TeamsUpgradePolicy konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden. Benutzer müssen sich im TeamsOnly-Modus befinden, was Sie tun können, indem Sie ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zuweisen. 

|Frage|Aktion |
|:------------|:-------|
|Was bedeutet der TeamsOnly-Modus? | Weitere Informationen finden Sie unter [Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](./migration-interop-guidance-for-teams-with-skype.md).|
|||


