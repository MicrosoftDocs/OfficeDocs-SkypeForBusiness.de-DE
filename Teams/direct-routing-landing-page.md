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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Angebotsseite für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ded644f552c233b712f43de212f2269ee6e70b2
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018801"
---
# <a name="phone-system-direct-routing"></a>Direktes Routing für Telefonsysteme

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Sie haben möglicherweise [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt. Jetzt sind Sie bereit, Cloud-Sprach-Workloads hinzuzufügen, und Sie haben sich entschieden, Ihren eigenen Telefonie-Betreiber für die PSTN-Konnektivität (Public Switched Telephone Network) zu verwenden, indem Sie direktes Routing für Telefonsysteme verwenden. Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.

Dieser Artikel beschreibt die wichtigsten Bereitstellungsentscheidungen für das direkte Routing sowie zusätzliche Faktoren, die Sie berücksichtigen sollten, basierend auf den Anforderungen Ihrer Organisation. Weitere Informationen über die Cloud-Sprachangebote von Microsoft finden Sie auch unter [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md).

## <a name="learn-more-about-direct-routing"></a>Hier finden Sie weitere Informationen zu direktem Routing

In den folgenden Artikeln finden Sie weitere Informationen zur Konfiguration und Verwendung von direktem Routing für das Telefonsysteme. Für die Konfiguration des direkten Routings sind Kenntnisse des PSTN-Routing Designs erforderlich. Lesen Sie alle diese Artikel, um zu verstehen, wie Sie direktes Routing planen und konfigurieren können:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Zusätzlich können Sie je nach Ihren Anforderungen die folgenden Artikel lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- In der folgenden Sitzung erfahren Sie mehr über direktes Routing: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Diese Kernetscheidungen sind für das direkte Routing zu berücksichtigen. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer werde ich das direkte Routing aktivieren? | Weitere Informationen finden Sie unter[Aktivieren von Benutzern für den direkten Routing-Service](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Habe ich die erforderlichen Lizenzen für das direkte Routing? | Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Überlegungen zum Session Border Controller (SBC)

Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen.  Eine Liste der zertifizierten SBCS finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie werde ich SBC bereitstellen? | Weitere Informationen finden Sie unter [Konfigurieren von direktem Routing](direct-routing-configure.md) | 
Habe ich mehrere Mandanten? | Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Überlegungen zum VoIP-Routing

Sie müssen das Telefonsystem so konfigurieren, um die Anrufe an die jeweiligen SBCs weiterzuleiten.

|Frage|Aktion |
|:------------|:-------|
| Welche VoIP-Routing Richtlinien, die PSTN-Nutzung und die VoIP-Routen muss ich erstellen? | Weitere Informationen zum VoIP-Routing finden Sie unter [Konfigurieren von VoIP-Routing](direct-routing-configure.md#configure-voice-routing).
| Welche Benutzer werden der von mir definierten VoIP-Routing-Richtlinie zugeordnet? | Weitere Beispiele finden Sie unter [Konfigurieren von VoIP](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Stellen Sie sicher, dass eingehende Anrufe mit TeamsUpgradePolicy im Team-Client eingehen.

Direktes Routing wird nur von Microsoft Teams unterstützt. Um PSTN-Anrufe über das direkte Routing zu tätigen oder zu empfangen, müssen Sie die erforderlichen TeamsUpgradePolicy konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden. Benutzer müssen sich im Modus „Nur Teams“ befinden, indem Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuweisen. 

|Frage|Aktion |
|:------------|:-------|
|Was bedeutet der Modus „Nur Teams“? | Weitere Informationen finden Sie unter[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Zusätzliche Bereitstellungsüberlegungen

Je nach den Anforderungen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, Folgendes zu berücksichtigen:

| Frage| Aktion |
| :------------|:-------|
| Haben Sie eine bestehende Skype für Business Server-Bereitstellung mit hybrider Konnektivität konfiguriert? |  Weitere Informationen darüber, wie Benutzerkonten in einer hybriden Umgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Migrieren Sie von einem Anrufplan oder von einer lokalen Skype for Business Umgebung auf direktes Routing? | Weitere Informationen zur Migration auf direktes Routing von einer bestehenden Umgebung finden Sie unter [Migration auf direktes Routing](direct-routing-migrating.md). |
|||
