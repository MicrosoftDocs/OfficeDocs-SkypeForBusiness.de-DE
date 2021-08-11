---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Erfahren Sie mehr über Normalisierungsregeln für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298615"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business
 
Erfahren Sie mehr über Normalisierungsregeln für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbitnummern nicht normalisiert sind. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass Ihre Orbits normalisiert werden, führen Sie das Verfahren unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) aus, um eine neue Normalisierungsregel zu definieren, damit das Muster zum **Abgleichen** den Orbitbereich und das **Übersetzungsmuster** **$1** identifiziert. Wenn der Orbitbereich für das Parken von Anrufen beispielsweise 7000 bis 7999 ist, lautet das **musterbezogene Muster** **^(7\d {3} )$** und das **Übersetzungsmuster** **$1.**
  
> [!IMPORTANT]
> Stellen Sie sicher, dass die Standardnormalisierungsregel in Ihren Wählplänen nicht **^(\d \* )** enthält. Andernfalls wird die Normalisierungsregel für das Parken von Anrufen nie ausgeführt.
  
## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md)

