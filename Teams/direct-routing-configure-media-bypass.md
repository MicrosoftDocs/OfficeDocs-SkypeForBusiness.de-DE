---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie die medienumgehung mit dem direkten Routing des Telefonsystems konfigurieren.
ms.openlocfilehash: a9769e921ff493e67614cf903ca9206f6f50bac8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290453"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Konfigurieren der Medienumgehung mit direktem Routing

Bevor Sie die medienumgehung mit Direct Routing konfigurieren, stellen Sie sicher, dass Sie [Plan für medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)gelesen haben.

Um die medienumgehung zu aktivieren, müssen die folgenden Bedingungen erfüllt sein:

1.  Stellen Sie sicher, dass Ihr SBC-Anbieter (Session Border Controller) die medienumgehung unterstützt und Anweisungen zum Konfigurieren der Umgehungsfunktion für den SBC enthält. Informationen zu SBCS, welche die medienumgehung unterstützen, und Anweisungen finden Sie auf der Zertifizierungsseite.

2.  Sie müssen die medienumgehung auf dem Stamm mithilfe des folgenden Befehls aktivieren: **setzen-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.  Stellen Sie sicher, dass die erforderlichen Anschlüsse geöffnet sind. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks

Sie können alle Benutzer gleichzeitig wechseln, oder Sie können eine Phased approached (empfohlen) implementieren.

- **Alle Benutzer gleichzeitig umschalten.** Wenn alle Bedingungen erfüllt sind, können Sie den Bypass-Modus aktivieren. Allerdings werden alle Ihre Produktionsbenutzer gleichzeitig gewechselt. Da bei der Konfiguration von Trunks und Ports möglicherweise einige Probleme auftreten, kann dies auf die Benutzeroberfläche der Produktionsumgebung zurückzuführen sein. 

- **Phasen orientierter Ansatz (Empfohlen)**.  Erstellen Sie einen neuen trunk für denselben SBC (mit einem anderen Port), testen Sie ihn, und ändern Sie die Richtlinie für Online-VoIP-Routing, damit die Benutzer auf den neuen trunk verweisen können. 

  Dies ist die empfohlene Vorgehensweise, da Sie einen reibungsloseren Übergang und eine unterbrechungsfreie Benutzererfahrung ermöglicht. Dieser Ansatz erfordert die Konfiguration des SBC, einen neuen FQDN-Namen und die Konfiguration der Firewall. Hinweis Sie müssen sicherstellen, dass Ihr Zertifikat beide Trunks unterstützt. In San benötigen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.

![Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks](media/direct-routing-media-bypass-8.png)

Anweisungen zum Konfigurieren der Trunks und zur Durchführung der Migration finden Sie in der Dokumentation Ihres SBC-Anbieters:

- AudioCodes
- Multifunktionsleiste
- TE-Systems (AnyNode)    

Eine Liste der für die direkte Weiterleitung zertifizierten Session Border Controllers (SBCS) finden Sie in [der Liste der für das direkte Routing zertifizierten Session Broder-Controller](direct-routing-border-controllers.md).



## <a name="see-also"></a>Siehe auch

[Planen der medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)



