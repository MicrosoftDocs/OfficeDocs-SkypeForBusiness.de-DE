---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die medienumgehung mithilfe des direkten Routings von Telefonsystemen konfigurieren, indem Sie alle Benutzer gleichzeitig wechseln oder eine phasenweise Implementierung implementieren (empfohlen).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d6bb25296b7a98e6fea7a59a5dd9406622dbd96
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904837"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Konfigurieren der Medienumgehung mit direktem Routing

Bevor Sie die medienumgehung mit Direct Routing konfigurieren, stellen Sie sicher, dass Sie [Plan für medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)gelesen haben.

Um die medienumgehung zu aktivieren, müssen die folgenden Bedingungen erfüllt sein:

1.    Stellen Sie sicher, dass Ihr SBC-Anbieter (Session Border Controller) die medienumgehung unterstützt und Anweisungen zum Konfigurieren der Umgehungsfunktion für den SBC enthält. Informationen zu SBCS, welche die medienumgehung unterstützen, und Anweisungen finden Sie auf der Zertifizierungsseite.

2.    Sie müssen die medienumgehung auf dem Stamm mithilfe des folgenden Befehls aktivieren: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.    Stellen Sie sicher, dass die erforderlichen Anschlüsse geöffnet sind. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks

Sie können alle Benutzer gleichzeitig wechseln, oder Sie können eine Phased approached (empfohlen) implementieren.

- **Alle Benutzer gleichzeitig umschalten.** Wenn alle Bedingungen erfüllt sind, können Sie den Bypass-Modus aktivieren. Allerdings werden alle Ihre Produktionsbenutzer gleichzeitig gewechselt. Da bei der Konfiguration von Trunks und Ports möglicherweise einige Probleme auftreten, kann dies auf die Benutzeroberfläche der Produktionsumgebung zurückzuführen sein. 

- **Phasen orientierter Ansatz (Empfohlen)**.  Erstellen Sie einen neuen trunk für denselben SBC (mit einem anderen Port), testen Sie ihn, und ändern Sie die Richtlinie für Online-VoIP-Routing, damit die Benutzer auf den neuen trunk verweisen können. 

  Dies ist die empfohlene Vorgehensweise, da Sie einen reibungsloseren Übergang und eine unterbrechungsfreie Benutzererfahrung ermöglicht. Dieser Ansatz erfordert die Konfiguration des SBC, einen neuen FQDN-Namen und die Konfiguration der Firewall. Hinweis Sie müssen sicherstellen, dass Ihr Zertifikat beide Trunks unterstützt. In San benötigen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.

![Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks](media/direct-routing-media-bypass-8.png)

Anweisungen zum Konfigurieren der Trunks und zur Durchführung der Migration finden Sie in der Dokumentation Ihres SBC-Anbieters:

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)

Eine Liste der für die direkte Weiterleitung zertifizierten Session Border Controllers (SBCS) finden Sie in [der Liste der für das direkte Routing zertifizierten Session Broder-Controller](direct-routing-border-controllers.md).



## <a name="related-topics"></a>Verwandte Themen

[Planen der medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)



