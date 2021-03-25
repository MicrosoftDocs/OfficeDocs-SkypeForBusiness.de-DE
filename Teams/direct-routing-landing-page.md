---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Hier finden Sie weitere Informationen zu Direct Routing, z. B. Konfiguration, erforderlichen Grundlegenden Bereitstellungsentscheidungen und Überlegungen zum Sprachrouting.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122209"
---
# <a name="phone-system-direct-routing"></a>Direktes Routing für Telefonsysteme

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie Besprechungen und [& bereitgestellt.](deploy-meetings-microsoft-teams-landing-page.md) Jetzt sind Sie bereit zum Hinzufügen von Cloud-Sprachauslastungen, und Sie haben sich entschieden, ihren eigenen Telefonieanbieter für die Konnektivität im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) mithilfe von Telefonsystem-Direct-Routing zu verwenden. Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Direct Routing sowie weitere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation berücksichtigen möchten. Sie sollten auch [Cloud Voice in Microsoft Teams lesen,](cloud-voice-landing-page.md) um weitere Informationen zu den Sprachangeboten von Microsoft in der Cloud zu erhalten.

## <a name="learn-more-about-direct-routing"></a>Weitere Informationen zu Direct Routing

In den folgenden Artikeln finden Sie weitere Informationen zum Konfigurieren und Verwenden von Telefonsystem-Direct-Routing. Für die Konfiguration von Direct Routing ist das Verständnis des PSTN-Routingentwurfs erforderlich. Sie sollten alle diese Artikel lesen, um zu verstehen, wie Sie Direct Routing planen und konfigurieren:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus können Sie je nach Ihren Anforderungen die folgenden Artikel lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Schauen Sie sich die folgende Sitzung an, um mehr über Direct Routing zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die wichtigsten Entscheidungen, die Sie bei Direct Routing berücksichtigen sollten. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer wird Direct Routing aktiviert? | Weitere Informationen finden Sie unter [Aktivieren von Benutzern für Direct Routing Service](direct-routing-configure.md). |
Habe ich die erforderlichen Lizenzen für Direct Routing? | Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Überlegungen zum Session Border Controller (SBC)

Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen.  Eine Liste der zertifizierten SBCs finden Sie unter [Unterstützte Sitzungsgrenzcontroller](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie werden SBCs bereitgestellt? | Weitere Informationen finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md) | 
Habe ich mehrere Mandanten? | Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Überlegungen zum Sprachrouting

Sie müssen das Telefonsystem so konfigurieren, dass die Anrufe an die jeweiligen SBCs weiterrouten.

|Frage|Aktion |
|:------------|:-------|
| Welche Sprachroutingrichtlinien, PSTN-Nutzungs- und Sprachrouten muss ich erstellen? | Informationen zum Sprachrouting finden Sie unter [Konfigurieren von Voice routing](direct-routing-configure.md).
| Welche Benutzer werden der von mir definierten Sprachroutingrichtlinie zugewiesen? | Weitere Informationen finden Sie in [den Beispielen unter Konfigurieren von Voice routing](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Sicherstellen, dass eingehende Anrufe mit TeamsUpgradePolicy im Teams-Client landen

Direktes Routing wird nur von Microsoft Teams unterstützt. Um PSTN-Anrufe über Direct Routing zu empfangen, müssen Sie TeamsUpgradePolicy konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden. Benutzer müssen sich im Modus "Teams Only" befinden, den Sie ausführen können, indem Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuweisen. 

|Frage|Aktion |
|:------------|:-------|
|Was bedeutet der Modus "Nur Teams"? | Weitere Informationen finden Sie unter [Migrations- und Interoperabilitätsleitfäden für Organisationen, die Teams zusammen mit Skype for Business verwenden.](./migration-interop-guidance-for-teams-with-skype.md)|
|||

## <a name="additional-deployment-considerations"></a>Zusätzliche Überlegungen zur Bereitstellung

Möglicherweise sollten Sie basierend auf den Anforderungen und der Konfiguration Ihrer Organisation Folgendes berücksichtigen:

| Frage| Aktion |
| :------------|:-------|
| Verfügen Sie über eine vorhandene Skype for Business Server-Bereitstellung mit konfigurierter Hybridkonnektivität? |  Informationen dazu, wie Benutzerkonten in einer Hybridumgebung bereitgestellt und verwaltet werden, finden Sie unter Benutzerkonten in einer Hybridumgebung [mit PSTN-Konnektivität.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Migrieren Sie vom Anrufplan oder aus einer lokalen Skype for Business-Umgebung zu Direct Routing? | Weitere Informationen zum Migrieren zu Direct Routing aus einer vorhandenen Umgebung finden Sie unter [Migrieren zu Direct Routing](direct-routing-migrating.md). |
|||