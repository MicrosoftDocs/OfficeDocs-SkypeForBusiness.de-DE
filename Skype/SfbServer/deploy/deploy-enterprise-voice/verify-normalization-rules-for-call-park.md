---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business 2015
 
Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
  
Parken Orbits müssen nicht normalisiert werden. Überprüfen Sie Ihren Wählplänen, um sicherzustellen, dass Ihre orbitnummern nicht normalisiert werden. Wenn Sie eine zusätzliche Normalisierungsregel aus, um zu verhindern, dass Ihre Orbits normalisierende erstellen müssen, führen Sie das Verfahren in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015](dial-plans.md) so definieren Sie eine neue Normalisierungsregel also dieses **Muster abgleichen** identifiziert den orbitbereich und **übersetzungsmuster** **$1**ist. Angenommen, Ihr orbitbereich zum Parken von Anrufen 7000-7999, das **Vergleichsmuster** ist **^ (7\d {3}) $** und **übersetzungsmuster** **$1**ist.
  
> [!IMPORTANT]
> Achten Sie darauf, dass die Standard-Normalisierungsregel in Ihren Wählplänen keine enthält **^(\d\*)**. Andernfalls wird die Normalisierungsregel Parken niemals ausgeführt.
  
## <a name="see-also"></a>Siehe auch

#### 

[Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015](dial-plans.md)

