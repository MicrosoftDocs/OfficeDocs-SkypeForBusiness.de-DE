---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Erfahren Sie mehr über Normalisierungsregeln für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
---

# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business
 
Erfahren Sie mehr über Normalisierungsregeln für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbitnummern nicht normalisiert sind. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass Ihre Orbits normalisiert werden, führen Sie das Verfahren unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) aus, um eine neue Normalisierungsregel zu definieren, damit **das Muster für die Übereinstimmung** den Orbitbereich und das **Übersetzungsmuster** **$1** identifiziert. Wenn ihr Orbitbereich für das Parken von Anrufen beispielsweise zwischen 7000 und 7999 liegt, ist das **übereinstimmende Muster** **^(7\d{3})$** und das **Übersetzungsmuster** **$1**.
  
> [!IMPORTANT]
> Stellen Sie sicher, dass die Standardnormalisierungsregel in Ihren Wählplänen nicht **^(\d\*)** enthält. Andernfalls wird die Normalisierungsregel für das Parken von Anrufen nie ausgeführt.
  
## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md)

