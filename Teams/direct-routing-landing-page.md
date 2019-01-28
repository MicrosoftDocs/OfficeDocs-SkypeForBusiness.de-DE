---
title: Telefon System direkten Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Zielseite zum direkten Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c2e225090c6d58db2184113dd43995847f9409
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595403"
---
# <a name="phone-system-direct-routing"></a>Telefon System direkten Routing

Sie haben den [Einstieg in die](get-started-with-teams-quick-start.md)abgeschlossen. Sie haben, Teams mit [Chat, Teams, Kanäle, &-apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation zurückgesetzt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Sie können nun Cloud VoIP Arbeitslasten hinzufügen, und Sie haben entschieden, Telefonie-Anbieter für die Verbindungen (Public Switched Telephone Network, PSTN) zu verwenden, mithilfe von Telefon System direkten Routing. Mit direktem Routing können Sie mit nahezu jedes beliebigen Telefonie Netzbetreiber Telefonsystem.

Dieser Artikel beschreibt Core Bereitstellung Entscheidungen für das direkte Routing sowie weitere Aspekte zu beachten, dass Sie möglicherweise konfigurieren möchten, basierend auf der Anforderungen Ihrer Organisation.  [Cloud-VoIP in Microsoft-Teams,](cloud-voice-landing-page.md) lesen Sie auch weitere Informationen zu VoIP Cloudlösungen von Microsoft.

## <a name="learn-more-about-direct-routing"></a>Erfahren Sie mehr über die direkte Routing


Die folgenden Artikel enthalten weitere Informationen zum Konfigurieren und Telefon System direktes Routing. Konfigurieren von direkten Routing erfordert Verständnis der PSTN-routing-Entwurf. Lesen Sie alle in diesen Artikeln zu verstehen, wie beim Planen und Konfigurieren von direkten Routing:

- [Planen von direktem Routing](direct-routing-plan.md) 
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)
- [Überwachung und Problembehandlung von direkten Routing](direct-routing-monitor-and-troubleshoot.md)

Darüber hinaus sollten Sie je nach Bedarf die folgenden Artikel lesen:

-  [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)
-  [Migrieren zu direkten Routing](direct-routing-migrating.md)
-  [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Sehen Sie sich die folgenden Sitzung Weitere Informationen zum direkten Routing: [Direktes Routing in Microsoft-Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Zentrale Bereitstellung Entscheidungen

Dies sind die Core Entscheidungen zu berücksichtigende zum direkten weiterleiten. 


|Fragen Sie sich|Aktion |
| :------------|:-------|
|Für welche Benutzer aktivieren ich direkten Routing? | Weitere Informationen finden Sie unter [Aktivieren von Benutzern für direkte Routingdienst](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Habe ich die erforderlichen Lizenzen für das direkte Routing? | Weitere Informationen finden Sie unter [Lizenzierung und anderen Anforderungen an](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Session Border Controller (SBC) Aspekte

Mit direktem Routing verbinden Sie Ihre eigene Session Border Controller (SBC) direkt mit Telefonsystem.  Eine Liste mit zertifizierten SBCs finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).

|Fragen Sie sich|Aktion |
|:------------|:-------|
| Wo und wie werden ich SBCs bereitstellen? | Weitere Informationen finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md) | 
Ist mehrere Mandanten vorhanden? | Weitere Informationen finden Sie unter [Configure a Session Border Controller für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>VoIP-routing Aspekte

Sie müssen so konfigurieren Sie Telefonsystem so, dass die Aufrufe an die bestimmte SBCs weitergeleitet.

|Fragen Sie sich|Aktion |
|:------------|:-------|
| Welche VoIP-Routingrichtlinien zurückgegeben, PSTN-Verwendung und VoIP-Routen benötige ich erstellen? | VoIP-routing-Informationen finden Sie unter [Konfigurieren der VoIP-Routing](direct-routing-configure.md#configure-voice-routing).
| Welche Benutzer werden die VoIP-routing-Richtlinie zugewiesen werden, die ich definieren? | Siehe die Beispiele in [VoIP-Routing konfigurieren](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="calling-and-interop-policies"></a>Aufrufen und Interop-Richtlinien

Direktes Routing wird nur mit Microsoft-Teams, unterstützt. Zum tätigen oder Entgegennehmen von Anrufen über direkte Weiterleitung PSTN, müssen Sie zum Konfigurieren der erforderlichen Richtlinien, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden. Sie können die Benutzer zum Festlegen von Teams als bevorzugter Client für Anrufe durch Konfigurieren des Benutzers für Teams nur Kopfzeilen herunterladen, oder Konfigurieren von Teams als bevorzugter Client aufrufende durch Zuweisen von der TeamsCallingPolicy und die TeamsInteropPolicy konfigurieren.

|Fragen Sie sich|Aktion |
|:------------|:-------|
|Wie soll ich Teams als bevorzugter Client für Anrufe festlegen? | Weitere Informationen finden Sie unter [Microsoft-Teams festgelegt, als der bevorzugte Client für Benutzer aufrufen](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Weitere Bereitstellungsaspekte

Möglicherweise möchten Sie die folgenden Punkte beachten basierend auf Ihrer Organisation Anforderungen und Konfiguration:

| Fragen Sie sich| Aktion |
| :------------|:-------|
| Haben Sie eine vorhandene Skype für Business Server-Bereitstellung mit hybridkonnektivität konfiguriert? |  Zu verstehen, wie Benutzerkonten in einer hybridumgebung bereitgestellt werden, und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Zum direkten Routing aus aufrufen planen oder aus einem Skype für Business lokalen Umgebung migrieren Sie? | Um weitere Informationen zum Migrieren zu direkten Routing von einer vorhandenen Umgebung zu verstehen, finden Sie unter [Migrating zum direkten Routing](direct-routing-migrating.md). |
|||
