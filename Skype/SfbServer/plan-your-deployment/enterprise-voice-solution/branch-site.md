---
title: Zweigstellen-SIP-Trunking in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Erfahren Sie mehr über das SIP-Trunking an Zweigstellenstandorten in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813715"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Zweigstellen-SIP-Trunking in Skype for Business Server
 
Erfahren Sie mehr über das SIP-Trunking an Zweigstellenstandorten in Skype for Business Server Enterprise-VoIP.
  
In einigen Fällen müssen Sie möglicherweise verteiltes SIP-Trunking an ausgewählten Zweigstellenstandorten implementieren. Informationen dazu, ob ein SIP-Trunk für einen Zweigstellenstandort erforderlich ist, sowie Details zu den unterstützten Topologieoptionen für die Bereitstellung von SIP-Trunks an Zweigstellenstandorten finden Sie unter ["SIP-Trunking" in Skype for Business Server.](sip-trunking.md)
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie sich für die Bereitstellung eines Zweigstellen-SIP-Trunks entscheiden, müssen Sie eine standortspezifische Kostenanalyse durchführen. Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einem Zweigstellenstandort in New York eine Analyse durchführen, um festzustellen, ob ein SIP-Trunk vom Standort New York an einen lokalen Dienstanbieter implementiert werden soll.
  
Um festzustellen, ob ein verteilter SIP-Trunk in New York kostengünstig ist, identifizieren Sie, welche Direct Inward Dialing (DID)-Nummern den SIP-Trunk verwenden, und analysieren Sie die Anzahl der Anrufe, die New York in anderen Bereichen als Redmond (425) tätigt. Sie können die DID-Beendigung für den Zweigstellenstandort am zentralen Standort haben. Am zentralen Standort "Redmond" können beispielsweise die DID-Nummern für den Zweigstellenstandort "New York" hosten. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks geringer sind als die Kosten dieser Anrufe, sollten Sie die Implementierung eines SIP-Trunks am Zweigstellenstandort New York in Betracht ziehen. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie einen Zweigstellen-SIP-Trunk bereitstellen, müssen Sie auch ihre Anforderungen an Ausfallsicherheit und Bandbreite ermitteln. Wenn die Verbindung zwischen Ihrem Zweigstellenstandort und dem zentralen Standort ausfallsicher ist und über ausreichend Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch Appliance am Zweigstellenstandort bereitstellen. Wenn die Verbindung zwischen Ihrem Zweigstellenstandort und dem zentralen Standort nicht ausfallsicher ist, stellen Sie eine Survivable Branch Appliance oder einen Survivable Branch Server mit einem Gateway oder einem SIP-Trunk am Zweigstellenstandort zur Verfügung. 
  

