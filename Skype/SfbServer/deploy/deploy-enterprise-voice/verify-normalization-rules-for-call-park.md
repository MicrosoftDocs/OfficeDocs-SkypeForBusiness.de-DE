---
title: Überprüfen von Normalisierungsregeln für den Parken von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informieren Sie sich über Normalisierungsregeln für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300937"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Überprüfen von Normalisierungsregeln für den Parken von Anrufen in Skype for Business
 
Informieren Sie sich über Normalisierungsregeln für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
  
Orbits für das Parken von anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbit-Nummern nicht normalisiert sind. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass ihre Umlaufbahnen normalisiert werden, führen Sie die Schritte unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) aus, um eine neue Normalisierungsregel zu definieren, damit das **Muster übereinstimmt** identifiziert den Umlaufbahn Bereich und das **Übersetzungsmuster** ist **$1**. Wenn beispielsweise der Orbit-Bereich Ihres Anruf Parks 7000-7999 ist, ist das **Muster, das übereinstimmen** soll, **^ (7 \ d{3}) $** , und das **Übersetzungsmuster** ist **$1**.
  
> [!IMPORTANT]
> Stellen Sie sicher, dass die Standard Normalisierungsregel in ihren Wählplänen **^ (\d\*)** nicht enthält. Andernfalls wird Ihre Normalisierungsregel für den Anruf Park nie ausgeführt.
  
## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md)

