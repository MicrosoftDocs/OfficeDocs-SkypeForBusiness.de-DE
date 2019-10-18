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
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Startseite für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: decbe74eaece7508c2118175bd25f8acab200cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572190"
---
# <a name="phone-system-direct-routing"></a>Direktes Routing für Telefonsysteme

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleichthaben Sie [Besprechungen #a0 Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Nun können Sie Cloud-VoIP-Arbeitsauslastungen hinzufügen, und Sie haben sich entschieden, mithilfe des direkten Routings des Telefonsystems ihren eigenen Telefoniedienstanbieter für PSTN-Verbindungen (Public Switched Telephone Network) zu verwenden. Mit der direkten Weiterleitung können Sie das Telefon System mit praktisch jedem Telefonnetzbetreiber verwenden.

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für das direkte Routing sowie weitere Überlegungen beschrieben, die Sie je nach den Anforderungen Ihrer Organisation berücksichtigen sollten. Sie sollten auch [Cloud-VoIP in Microsoft Teams](cloud-voice-landing-page.md) lesen, um weitere Informationen zu den Cloud-sprach angeboten von Microsoft zu erhalten.

## <a name="learn-more-about-direct-routing"></a>Weitere Informationen zum direkten Routing

In den folgenden Artikeln finden Sie weitere Informationen zum Konfigurieren und Verwenden des direkten Routings für das Telefon System. Für die Konfiguration des direkten Routings ist das Verständnis des PSTN-Routingentwurfs erforderlich. Sie sollten alle diese Artikel lesen, um zu erfahren, wie Sie das direkte Routing planen und konfigurieren können:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus empfiehlt es sich, je nach Ihren Anforderungen die folgenden Artikel zu lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Schauen Sie sich die folgende Sitzung an, um mehr über Direct Routing zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die wichtigsten Entscheidungen, die bei der direkten Weiterleitung zu Bedenken sind. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer wird die direkte Weiterleitung aktiviert? | Weitere Informationen finden Sie unter [Aktivieren von Benutzern für den direkten Routing Dienst](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Habe ich die erforderlichen Lizenzen für die direkte Weiterleitung? | Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Überlegungen zu Session Border Controller (SBC)

Mit Direct Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt mit dem Telefon System verbinden.  Eine Liste der zertifizierten SBCS finden Sie unter [unterstützte Session Border Controllers](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie kann ich SBCS bereitstellen? | Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md) . | 
Habe ich mehrere Mandanten? | Weitere Informationen finden Sie unter [Konfigurieren eines Sitzungs Grenz Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Überlegungen zum VoIP-Routing

Sie müssen das Telefon System so konfigurieren, dass die Anrufe an den jeweiligen SBCS weitergeleitet werden.

|Frage|Aktion |
|:------------|:-------|
| Welche VoIP-Routing Richtlinien, PSTN-Nutzung und VoIP-Routen muss ich erstellen? | Informationen zum VoIP-Routing finden Sie unter [Konfigurieren des VoIP-Routings](direct-routing-configure.md#configure-voice-routing).
| Welche Benutzer werden der von mir definierten VoIP-Routing Richtlinie zugewiesen? | Sehen Sie sich die Beispiele unter [Konfigurieren des VoIP-Routings](direct-routing-configure.md#configure-voice-routing)an. |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Sicherstellen, dass eingehende Anrufe im Team-Client mit TeamsUpgradePolicy landen

Das direkte Routing wird nur von Microsoft Teams unterstützt. Wenn Sie PSTN-Anrufe über direkte Weiterleitung empfangen möchten, müssen Sie TeamsUpgradePolicy so konfigurieren, dass eingehende Anrufe in Teams empfangen werden. Benutzer müssen sich im Modus "nur für Teams" befinden, was Sie tun können, indem Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zuweisen. 

|Frage|Aktion |
|:------------|:-------|
|Was bedeutet "nur für Teams"? | Weitere Informationen finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Weitere Überlegungen zur Bereitstellung

Je nach den Anforderungen und der Konfiguration Ihrer Organisation empfiehlt es sich, die folgenden Punkte zu bedenken:

| Frage| Aktion |
| :------------|:-------|
| Verfügen Sie über eine vorhandene Skype for Business Server-Bereitstellung mit konfigurierter Hybrid Konnektivität? |  Informationen dazu, wie Benutzerkonten in einer Hybridumgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Migrieren Sie vom Anrufplan zur direkten Weiterleitung oder von einer lokalen Skype for Business-Umgebung? | Weitere Informationen zum Migrieren zu direktem Routing aus einer vorhandenen Umgebung finden Sie unter [Migrieren zu direktem Routing](direct-routing-migrating.md). |
|||
