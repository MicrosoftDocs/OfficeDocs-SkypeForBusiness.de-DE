---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
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
description: Lesen Sie dieses Thema, um Informationen zum Konfigurieren der medienumgehung mit Phone System direktem Routing.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232695"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Konfigurieren der Medienumgehung mit direktem Routing

Vor dem Konfigurieren von Medien mit direktem Routing zu umgehen, achten Sie darauf, dass Sie [Plan für Medien mit direktem Routing umgehen](direct-routing-plan-media-bypass.md)gelesen haben.

Um die medienumgehung aktivieren, müssen die folgenden Bedingungen erfüllt sein:

1.  Stellen Sie sicher, dass Hersteller Ihres Session Border Controller (SBC) Wahl die medienumgehung unterstützt und bietet Anweisungen zum Konfigurieren auf die SBC umgehen. Finden Sie in der Zertifizierung-Seite, um Informationen und Anweisungen SBCs, welche Schriftarten Unterstützung von Medien zu umgehen.

2.  Sie müssen die medienumgehung auf den Trunk mithilfe des folgenden Befehls aktivieren: **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.

3.  Stellen Sie sicher, dass die erforderlichen Ports geöffnet sind. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrieren von nicht umgangen Trunks zur Umgehung aktivierten trunks

Sie können alle Benutzer gleichzeitig wechseln oder Implementieren einer phasenweisen erreicht (empfohlen).

- **Wechseln Sie alle Benutzer gleichzeitig.** Wenn alle erfüllt werden, können Sie die Bypass-Modus aktivieren. Allerdings werden alle produktionsbenutzern gleichzeitig gewechselt werden soll. Da einige Probleme zunächst möglicherweise beim Konfigurieren von Trunks und Ports treten, möglicherweise angenehmer Produktion betroffen sein. 

- **Phased Ansatz. (Empfohlen)**.  Erstellen Sie einen neuen Trunk für den gleichen SBC (mit einem anderen Port), testen sie das Formular, und ändern Sie die online VoIP-Routingrichtlinie für die Benutzer auf den neuen Trunk. 

  Dies ist die empfohlene Vorgehensweise, da es für ein fließender Übergang und einheitliche benutzererfahrung ermöglicht. Bei diesem Ansatz müssen die Konfiguration der SBC, einer neuen FQDN-Namen und die Konfiguration der Firewall. Beachten Sie, dass Sie benötigen, um sicherzustellen, dass Ihr Zertifikat beide Trunks unterstützt. SAN müssen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.

![Migration von nicht umgangen Trunks zu Trunks Umgehung aktiviert)](media/direct-routing-media-bypass-8.png)

Anweisungen zum Konfigurieren der Trunks und Durchführen der Migration finden Sie unter der vom Hersteller Ihrer SBC-Dokumentation:

- AudioCodes
- Bändchen
- TE-Systems (AnyNode)    

Eine Liste der für das direkte Routing certified Session Border Controller (SBCs) finden Sie unter [Liste der Sitzung Broder Controller für die direkte Weiterleitung zertifiziert](direct-routing-border-controllers.md).



## <a name="see-also"></a>Siehe auch

[Planen Sie die medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)



