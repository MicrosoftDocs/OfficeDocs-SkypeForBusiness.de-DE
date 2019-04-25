---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Zielseite zum direkten Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59f7cf4f1249956f3c763d12fcd96bf5c10a9fac
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298652"
---
# <a name="phone-system-direct-routing"></a>Direktes Routing für Telefonsysteme

Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Sie können nun Cloud VoIP Arbeitslasten hinzufügen, und Sie haben entschieden, Telefonie-Anbieter für die Verbindungen (Public Switched Telephone Network, PSTN) zu verwenden, mithilfe von Telefon System direkten Routing. Mit direktem Routing können Sie mit nahezu jedes beliebigen Telefonie Netzbetreiber Telefonsystem.

Dieser Artikel beschreibt Core Bereitstellung Entscheidungen für das direkte Routing sowie weitere Aspekte zu beachten, dass Sie möchten möglicherweise bedenken sollten, basierend auf der Anforderungen Ihrer Organisation. [Cloud-VoIP in Microsoft-Teams,](cloud-voice-landing-page.md) lesen Sie auch weitere Informationen zu VoIP Cloudlösungen von Microsoft.

## <a name="learn-more-about-direct-routing"></a>Erfahren Sie mehr über die direkte Routing

Die folgenden Artikel enthalten weitere Informationen zum Konfigurieren und Telefon System direktes Routing. Konfigurieren von direkten Routing erfordert Verständnis der PSTN-routing-Entwurf. Lesen Sie alle in diesen Artikeln zu verstehen, wie beim Planen und Konfigurieren von direkten Routing:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direktem Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus sollten Sie je nach Bedarf die folgenden Artikel lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migration zu direktem Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Sehen Sie sich die folgenden Sitzung Weitere Informationen zum direkten Routing: [Direktes Routing in Microsoft-Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Core Entscheidungen zu berücksichtigende zum direkten weiterleiten. 

|Frage|Aktion |
| :------------|:-------|
|Für welche Benutzer aktivieren ich direkten Routing? | Weitere Informationen finden Sie unter [Aktivieren von Benutzern für direkte Routingdienst](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Habe ich die erforderlichen Lizenzen für das direkte Routing? | Weitere Informationen finden Sie unter [Lizenzierung und anderen Anforderungen an](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Session Border Controller (SBC) Aspekte

Mit direktem Routing verbinden Sie Ihre eigene Session Border Controller (SBC) direkt mit Telefonsystem.  Eine Liste mit zertifizierten SBCs finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).

|Frage|Aktion |
|:------------|:-------|
| Wo und wie werden ich SBCs bereitstellen? | Weitere Informationen finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md) | 
Ist mehrere Mandanten vorhanden? | Weitere Informationen finden Sie unter [Configure a Session Border Controller für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>VoIP-routing Aspekte

Sie müssen so konfigurieren Sie Telefonsystem so, dass die Aufrufe an die bestimmte SBCs weitergeleitet.

|Frage|Aktion |
|:------------|:-------|
| Welche VoIP-Routingrichtlinien zurückgegeben, PSTN-Verwendung und VoIP-Routen benötige ich erstellen? | VoIP-routing-Informationen finden Sie unter [Konfigurieren der VoIP-Routing](direct-routing-configure.md#configure-voice-routing).
| Welche Benutzer werden die VoIP-routing-Richtlinie zugewiesen werden, die ich definieren? | Siehe die Beispiele in [VoIP-Routing konfigurieren](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="calling-and-interop-policies"></a>Aufrufen und Interop-Richtlinien

Direktes Routing wird nur mit Microsoft-Teams, unterstützt. Zum tätigen oder Entgegennehmen von Anrufen über direkte Weiterleitung PSTN, müssen Sie zum Konfigurieren der erforderlichen Richtlinien, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden. Sie können die Benutzer zum Festlegen von Teams als bevorzugter Client für Anrufe durch Konfigurieren des Benutzers für Teams nur Kopfzeilen herunterladen, oder Konfigurieren von Teams als bevorzugter Client aufrufende durch Zuweisen von der TeamsCallingPolicy und die TeamsInteropPolicy konfigurieren.

|Frage|Aktion |
|:------------|:-------|
|Wie soll ich Teams als bevorzugter Client für Anrufe festlegen? | Weitere Informationen finden Sie unter [Microsoft-Teams festgelegt, als der bevorzugte Client für Benutzer aufrufen](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Weitere Bereitstellungsaspekte

Möglicherweise möchten Sie die folgenden Punkte beachten basierend auf Ihrer Organisation Anforderungen und Konfiguration:

| Frage| Aktion |
| :------------|:-------|
| Haben Sie eine vorhandene Skype für Business Server-Bereitstellung mit hybridkonnektivität konfiguriert? |  Zu verstehen, wie Benutzerkonten in einer hybridumgebung bereitgestellt werden, und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Zum direkten Routing aus aufrufen planen oder aus einem Skype für Business lokalen Umgebung migrieren Sie? | Um weitere Informationen zum Migrieren zu direkten Routing von einer vorhandenen Umgebung zu verstehen, finden Sie unter [Migrating zum direkten Routing](direct-routing-migrating.md). |
|||
