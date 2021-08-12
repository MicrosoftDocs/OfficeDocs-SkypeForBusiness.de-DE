---
title: Telefon direktes Systemrouting in Teams
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
description: Erfahren Sie mehr über die Direct Routing-Konfiguration, erforderliche wichtige Bereitstellungsentscheidungen und Überlegungen zum Voice Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55676d855d3e15c3f767203da981a4fae241f3128a270f5656d770a229f00059
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848070"
---
# <a name="phone-system-direct-routing"></a>Telefon direktes Routing des Systems

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Möglicherweise haben Sie Besprechungen [oder & bereitgestellt.](deploy-meetings-microsoft-teams-landing-page.md) Jetzt können Sie Cloud-Spracharbeitsauslastungen hinzufügen, und Sie haben sich entschieden, Ihren eigenen Netzbetreiber für pstN-Konnektivität (Public Switched Telephone Network) mithilfe von Telefonsystem Direct Routing zu verwenden. Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Direct-Routing sowie weitere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation berücksichtigen sollten. Lesen Sie außerdem [Cloud Voice in Microsoft Teams,](cloud-voice-landing-page.md) um weitere Informationen zu Den Cloud Voice-Angeboten von Microsoft zu erhalten.

## <a name="learn-more-about-direct-routing"></a>Weitere Informationen zu Direct-Routing

Die folgenden Artikel enthalten weitere Informationen zum Konfigurieren und Verwenden Telefonsystem Direct-Routings. Zum Konfigurieren von Direct Routing sind Kenntnisse des PSTN-Routingdesigns erforderlich. Lesen Sie alle diese Artikel, um zu verstehen, wie Sie Direct-Routing planen und konfigurieren:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus können Sie je nach Anforderungen auch die folgenden Artikel lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Schauen Sie sich die folgende Sitzung an, um mehr über Direct-Routing zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Kernentscheidungen, die Sie beim Direkten Routing berücksichtigen sollten. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer wird Direct Routing aktiviert? | Weitere Informationen finden Sie unter [Aktivieren von Benutzern für den Direct-Routingdienst.](direct-routing-configure.md) |
Habe ich die erforderlichen Lizenzen für Direct-Routing? | Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Überlegungen zum Session Border Controller (SBC)

Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen.  Eine Liste der zertifizierten SBCs finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie werden SBCs bereitgestellt? | Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md) | 
Habe ich mehrere Mandanten? | Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Überlegungen zur Sprachrouting-Weiterleitung

Sie müssen die Einzelnen Telefonsystem, um die Anrufe an bestimmte SBCs weiter zu routen.

|Frage|Aktion |
|:------------|:-------|
| Welche Voice Routing-Richtlinien, PSTN-Nutzung und Sprachrouten muss ich erstellen? | Informationen zum Voice Routing finden Sie unter [Konfigurieren von Voice Routing.](direct-routing-configure.md)
| Welche Benutzer werden der von mir definierten Voiceroutingrichtlinie zugewiesen? | Weitere Informationen finden Sie in den [Beispielen unter Konfigurieren von Voice Routing.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Sicherstellen, dass eingehende Anrufe mit TeamsUpgradePolicy im Teams-Client landen

Direktes Routing wird nur von anderen Microsoft Teams. Um PSTN-Anrufe über Direct-Routing zu empfangen, müssen Sie TeamsUpgradePolicy konfigurieren, um sicherzustellen, dass eingehende Anrufe in einem Teams. Benutzer müssen sich im Teams-Modus befinden, den Sie ausführen können, indem Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuweisen. 

|Frage|Aktion |
|:------------|:-------|
|Was bedeutet Teams "Nur Modus"? | Weitere Informationen finden Sie unter [Migrations- und Interoperabilitätsleitfade](./migration-interop-guidance-for-teams-with-skype.md)für Organisationen, die Teams mit Skype for Business.|
|||

## <a name="additional-deployment-considerations"></a>Zusätzliche Überlegungen zur Bereitstellung

Je nach anforderungen und Konfiguration Ihrer Organisation sollten Sie Folgendes berücksichtigen:

| Frage| Aktion |
| :------------|:-------|
| Verfügen Sie über eine vorhandene Skype for Business Server mit konfigurierter Hybridkonnektivität? |  Informationen dazu, wie Benutzerkonten in einer Hybridumgebung bereitgestellt und verwaltet werden, finden Sie unter Benutzerkonten in einer [Hybridumgebung mit PSTN-Anbindung.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Migrieren Sie aus dem Anrufplan oder aus einer lokalen Skype for Business Direct-Routing? | Weitere Informationen zum Migrieren von einer vorhandenen Umgebung zu Direct-Routing finden Sie unter [Migrieren zu Direct-Routing.](direct-routing-migrating.md) |
|||
