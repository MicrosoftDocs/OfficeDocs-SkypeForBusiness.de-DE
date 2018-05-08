---
title: SIP-Trunking für Zweigstellenstandorte in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informationen Sie zu SIP-Trunking an Zweigniederlassungen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 862a39e7472ab461725957cea6e5a89e0c156286
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a>SIP-Trunking für Zweigstellenstandorte in Skype for Business Server 2015
 
Informationen Sie zu SIP-Trunking an Zweigniederlassungen in Skype für Business Server Enterprise-VoIP.
  
In einigen Fällen müssen Sie möglicherweise verteilten SIP-Trunking am ausgewählten Zweigniederlassungen implementieren. Um zu bestimmen, ob ein SIP Trunk erforderlich ist, für eine Zweigstelle und ausführliche Informationen zu den unterstützten Topologieoptionen für die Bereitstellung von SIP-Trunks in Zweigniederlassungen, finden Sie unter [SIP-Trunking in Skype für Business Server 2015](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie einen Branch Site SIP-Trunk bereitstellen möchten, müssen Sie eine standortspezifische Kostenanalyse ausführen. Beispielsweise sollte ein Unternehmen, das einen zentralen Standort in Redmond, Washington, und eine Zweigniederlassung in New York hat eine Analyse, um festzustellen, ob einen SIP-Trunk von New York-Website mit einem lokalen Dienstanbieter implementieren bewirken.
  
Zu bestimmen, ob ein verteilter SIP-Trunk in New York kostengünstigen ist, bestimmt, die direkte Nummer (Inward DIALING) Zahlen werden verwenden Sie den SIP-Trunk und analysieren die Anzahl von Aufrufen von New York zu Bereichen als "Redmond" (425) durch. Sie können DID-Beendigung für den Zweigstellenstandort am zentralen Standort verfügen. Beispielsweise kann am zentrale Standort "Redmond" DID-Nummern für die Zweigniederlassung New York hosten. Wenn die Kosten der Implementierung eines verteilten SIP-Trunks kleiner als die Kosten für diese Aufrufe ist, sollten Sie einen SIP-Trunk am Zweigstellenstandort New York implementieren. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie einen Branch Site SIP-Trunk bereitstellen, müssen Sie auch Ihre Anforderungen höhere Zuverlässigkeit und Bandbreite bestimmen. Wenn die Verknüpfung zwischen der Zweigstelle und dem zentralen Standort ausfallsichere ist und verfügt über genügend Bandbreite, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch Appliance am Zweigstellenstandort bereitstellen. Wenn die Verknüpfung zwischen der Zweigstelle und dem zentralen Standort nicht ausfallsicher ist, Bereitstellen einer Survivable Branch Appliance oder einen Survivable Branch Server mit einem Gateway oder SIP-Trunk am Zweigstellenstandort bereitstellen. 
  

