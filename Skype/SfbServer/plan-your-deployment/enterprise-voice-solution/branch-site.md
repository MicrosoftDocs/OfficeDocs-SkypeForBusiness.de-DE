---
title: SIP-Trunking in der Zweigstelle in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informieren Sie sich über SIP-Trunking an Zweigstellen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277111"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>SIP-Trunking in der Zweigstelle in Skype for Business Server
 
Informieren Sie sich über SIP-Trunking an Zweigstellen in Skype for Business Server Enterprise-VoIP.
  
In einigen Fällen müssen Sie möglicherweise verteilte SIP-Trunking an ausgewählten Zweigstellen implementieren. Wenn Sie feststellen möchten, ob ein SIP-Trunk für eine Zweigstelle benötigt wird, und Details zu den unterstützten Topologie-Optionen für die Bereitstellung von SIP-Stämmen in Zweigstellen finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Beispielanalyse für die SIP-Trunkanforderungen an einer Zweigniederlassung

Wenn Sie sich für die Bereitstellung einer Zweigstelle SIP Trunk entscheiden, müssen Sie eine Website spezifische Kostenanalyse durchführen. Beispielsweise sollte ein Unternehmen mit einem zentralen Standort in Redmond, Washington und einer Zweigstelle in New York eine Analyse durchführen, um zu ermitteln, ob ein SIP-Trunk vom Standort New York zu einem lokalen Dienstanbieter implementiert werden soll.
  
Wenn Sie feststellen möchten, ob ein verteilter SIP-Trunk in New York kostengünstig ist, ermitteln Sie, welche Direktwahlnummern (DID) den SIP-Stamm verwenden, und analysieren Sie die Anzahl der Anrufe, die in New York an andere Bereiche als Redmond (425) vorgenommen werden. Sie können für die Verzweigungs Website am zentralen Standort beendet haben. So kann beispielsweise auf der zentralen Website von Redmond die Nummer für die Niederlassung in der New York Branch-Website gehostet werden. Wenn die Kosten für die Implementierung eines verteilten SIP-Trunks kleiner als die Kosten dieser Anrufe sind, sollten Sie einen SIP-Trunk an der New York Branch-Website implementieren. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Weitere SIP-Trunkanforderungen für Zweigniederlassungen

Die Entscheidung, ob anstelle eines Gateways ein SIP-Trunk bereitgestellt werden sollte, hängt von der Kostendifferenz bei Ferngesprächen der einzelnen Optionen ab. Wenn Sie eine Verzweigungs Website SIP-Trunk bereitstellen, müssen Sie auch ihre Stabilitäts-und Bandbreitenanforderungen ermitteln. Wenn der Link zwischen Ihrer Zweigstelle und dem zentralen Standort widerstandsfähig ist und über genügend Bandbreite verfügt, können Sie einen SIP-Trunk oder ein Gateway bereitstellen. Sie müssen keine Survivable Branch-Appliance an der Zweigstelle bereitstellen. Wenn der Link zwischen Ihrer Verzweigungs Website und dem zentralen Standort nicht belastbar ist, stellen Sie eine Survivable Branch-Appliance bereit, oder stellen Sie einen überlebensfähigen Verzweigungs Server mit einem Gateway oder SIP-Trunk an der Zweigstelle bereit. 
  

