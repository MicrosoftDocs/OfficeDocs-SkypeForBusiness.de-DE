---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Medienumgehung mit Telefonsystem Direct-Routing für Microsoft Teams konfigurieren, indem Sie alle Benutzer auf einmal wechseln oder einen phasenweise ansatzweiser Ansatz implementieren (empfohlen).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcbc893d3549e491d40268ae3417f5203d755ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598579"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Konfigurieren der Medienumgehung mit direktem Routing

Bevor Sie die Medienumgehung mit Direct Routing konfigurieren, vergewissern Sie sich, dass Sie den Artikel Planen der Medienumgehung [mit Direct-Routing gelesen haben.](direct-routing-plan-media-bypass.md)

Zum Aktivieren der Medienumgehung müssen die folgenden Bedingungen erfüllt sein:

1.    Stellen Sie sicher, dass ihr SBC-Anbieter (Session Border Controller) die Medienumgehung unterstützt und Anweisungen zum Konfigurieren der Umgehung für den SBC bietet. Auf der Zertifizierungsseite finden Sie Informationen zu SBCs, die die Medienumgehung unterstützen, und Anweisungen.

2.    Sie müssen die Medienumgehung für den Trunk mit dem folgenden Befehl aktivieren: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Stellen Sie sicher, dass die erforderlichen Ports geöffnet sind. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrieren von nicht umgangenen Trunks zu umgehenden Trunks

Sie können alle Benutzer gleichzeitig wechseln oder einen phasenweise ansatzweiser Ansatz implementieren (empfohlen).

- **Gleichzeitiges Wechseln aller Benutzer** Wenn alle Bedingungen erfüllt sind, können Sie den Umgehungsmodus aktivieren. Alle Produktionsbenutzer werden jedoch gleichzeitig umgestellt. Da beim Konfigurieren von Trunks und Ports zunächst einige Probleme auftreten können, ist die Benutzererfahrung in der Produktionsumgebung möglicherweise davon betroffen. 

- **Phasenweiser Ansatz. (Empfohlen)**.  Erstellen Sie einen neuen Trunk für denselben SBC (mit einem anderen Port), testen Sie ihn, und ändern Sie die Online-Voiceroutingrichtlinie für die Benutzer so, dass sie auf den neuen Trunk verweisen. 

  Dies ist der empfohlene Ansatz, da er einen reibungslosen Übergang und unterbrechungsfreie Benutzeroberfläche ermöglicht. Dieser Ansatz erfordert die Konfiguration des SBC, einen neuen FQDN-Namen und die Konfiguration der Firewall. Beachten Sie, dass Ihr Zertifikat beide Trunks unterstützt. In SAN müssen zwei Namen **(sbc1.contoso.com** und **sbc2.contoso.com)** oder ein Platzhalterzertifikat verwendet werden.

![Migrieren von nicht umgangenen Trunks zu umgehungsfähigen Trunks)](media/direct-routing-media-bypass-8.png)

Anweisungen zum Konfigurieren der Trunks und zum Durchführen der Migration finden Sie in der Dokumentation Ihres SBC-Anbieters:

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Kommunikationen im Menüband](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Dokumentation zur TE-Systems-Bereitstellung (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Eine Liste der für Direct Routing zertifizierten Session Border Controller (SBCs) finden Sie unter Liste der [Session Broder Controller,](direct-routing-border-controllers.md)die für Direct Routing zertifiziert sind.



## <a name="related-topics"></a>Verwandte Themen

[Planen der Medienumgehung mit Direct-Routing](direct-routing-plan-media-bypass.md)



