---
title: SIP-Trunking an Zweigstellenstandorten in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Erfahren Sie mehr über SIP-Trunking an Zweigstellenstandorten in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b8c1c930bb2500ca9330b14cce7fd5b341db60a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829899"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>SIP-Trunking an Zweigstellenstandorten in Skype for Business Server
 
Erfahren Sie mehr über SIP-Trunking an Zweigstellenstandorten in Skype for Business Server Enterprise-VoIP.
  
In einigen Fällen müssen Sie möglicherweise verteiltes SIP-Trunking an ausgewählten Zweigstellenstandorten implementieren. Informationen dazu, ob ein SIP-Trunk für einen Zweigstellenstandort benötigt wird, und ausführliche Informationen zu den unterstützten Topologieoptionen für die Bereitstellung von SIP-Trunks an Zweigstellenstandorten finden Sie [unter SIP-Trunking in Skype for Business Server.](sip-trunking.md)
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie sich für die Bereitstellung eines ZWEIGSTELLEN-SIP-Trunks entscheiden, müssen Sie eine standortspezifische Kostenanalyse durchführen. Beispielsweise sollte ein Unternehmen, das über einen zentralen Standort in Redmond, Washington und einen Zweigstellenstandort in New York verfügt, eine Analyse durchführen, um zu bestimmen, ob ein SIP-Trunk vom Standort New York zu einem lokalen Dienstanbieter implementiert werden soll.
  
Um festzustellen, ob ein verteilter SIP-Trunk in New York kostengünstig ist, identifizieren Sie, welche DID-Nummern (Direct Inward Dialing) den SIP-Trunk verwenden, und analysieren Sie die Anzahl der Anrufe, die New York in andere Regionen als Redmond (425) tätigt. Sie können DID-Beendigung für die Zweigstelle am zentralen Standort haben. Beispielsweise kann der Zentrale Standort Redmond DID-Nummern für den Zweigstellenstandort New York hosten. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks niedriger sind als die Kosten für diese Anrufe, sollten Sie die Implementierung eines SIP-Trunks am Zweigstellenstandort New York in Betracht ziehen. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie einen SIP-Trunk an einem Zweigstellenstandort bereitstellen, müssen Sie auch Ihre Resilienz- und Bandbreitenanforderungen ermitteln. Wenn die Verbindung zwischen Ihrem Zweigstellenstandort und dem zentralen Standort ausfallsicher ist und über ausreichende Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch Appliance am Zweigstellenstandort bereitstellen. Wenn die Verbindung zwischen Ihrem Zweigstellenstandort und dem zentralen Standort nicht ausfallsicher ist, stellen Sie eine Survivable Branch Appliance oder einen Survivable Branch Server mit einem Gateway oder SIP-Trunk am Zweigstellenstandort bereit. 
  

