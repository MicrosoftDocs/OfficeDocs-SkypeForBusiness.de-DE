---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 6f27daca3ef3f1bcdc4c70f04b92ccaa29a569a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892265"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype für Unternehmen
 
Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
  
Parken Orbits müssen nicht normalisiert werden. Überprüfen Sie Ihren Wählplänen, um sicherzustellen, dass Ihre orbitnummern nicht normalisiert werden. Wenn Sie eine zusätzliche Normalisierungsregel aus, um zu verhindern, dass Ihre Orbits normalisierende erstellen müssen, führen Sie das Verfahren in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md) so definieren Sie eine neue Normalisierungsregel also dieses **Muster abgleichen** identifiziert den orbitbereich und **übersetzungsmuster** **$1**ist. Angenommen, Ihr orbitbereich zum Parken von Anrufen 7000-7999, das **Vergleichsmuster** ist **^(7\d{3})$** und **übersetzungsmuster** **$1**ist.
  
> [!IMPORTANT]
> Achten Sie darauf, dass die Standard-Normalisierungsregel in Ihren Wählplänen keine enthält **^(\d\*)**. Andernfalls wird die Normalisierungsregel Parken niemals ausgeführt.
  
## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md)

