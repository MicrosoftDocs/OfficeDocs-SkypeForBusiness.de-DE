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
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Startseite für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dca9fda99973931cff70301da089f6d0c3f4a9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236586"
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
| Welche VoIP-Routing Richtlinien, PSTN-Nutzung und VoIP-Routen muss ich erstellen? | Informationen zum VoIP-Routing finden Sie unter [Konfigurieren des VoIP](direct-routing-configure.md#configure-voice-routing)-Routings.
| Welche Benutzer werden der von mir definierten VoIP-Routing Richtlinie zugewiesen? | Sehen Sie sich die Beispiele unter [Konfigurieren des VoIP](direct-routing-configure.md#configure-voice-routing)-Routings an. |
|||

### <a name="calling-and-interop-policies"></a>Anruf-und Interop-Richtlinien

Das direkte Routing wird nur von Microsoft Teams unterstützt. Sie müssen die erforderlichen Richtlinien konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden, um PSTN-Anrufe über direkte Weiterleitung zu tätigen oder zu empfangen. Sie können Benutzer so konfigurieren, dass Sie Teams als bevorzugten Client für Anrufe festlegen, indem Sie entweder den Benutzer für den Modus "nur für Teams" konfigurieren oder Teams als bevorzugten Anruf Client konfigurieren, indem Sie den TeamsCallingPolicy und den TeamsInteropPolicy zuweisen.

|Frage|Aktion |
|:------------|:-------|
|Wie kann ich Teams als bevorzugten Client für Anrufe einrichten? | Weitere Informationen finden Sie unter [Einrichten von Microsoft Teams als bevorzugter Anruf Client für Benutzer](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Weitere Überlegungen zur Bereitstellung

Je nach den Anforderungen und der Konfiguration Ihrer Organisation empfiehlt es sich, die folgenden Punkte zu bedenken:

| Frage| Aktion |
| :------------|:-------|
| Verfügen Sie über eine vorhandene Skype for Business Server-Bereitstellung mit konfigurierter Hybrid Konnektivität? |  Informationen dazu, wie Benutzerkonten in einer Hybridumgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Migrieren Sie vom Anrufplan zur direkten Weiterleitung oder von einer lokalen Skype for Business-Umgebung? | Weitere Informationen zum Migrieren zu direktem Routing aus einer vorhandenen Umgebung finden Sie unter [Migrieren zu direktem Routing](direct-routing-migrating.md). |
|||
