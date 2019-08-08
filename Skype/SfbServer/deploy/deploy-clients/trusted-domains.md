---
title: Skype Room System – Vertrauenswürdige Domänen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235014"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Room System – Vertrauenswürdige Domänen
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
  
## <a name="trusted-domains"></a>Vertrauenswürdige Domänen

Der Skype for Business-Client zeigt ein Dialogfeld an, in dem Benutzer das Zertifikat über den Skype for Business-Server akzeptieren können, wenn sich die SIP-Domäne des Benutzerkontos von dem Namen unterscheidet, der in dem Betreff oder dem Betreff-Alternativnamen des Zertifikats angezeigt wird. Wenn das für Skype for Business Server in Ihrer Organisation konfigurierte Zertifikat nicht über den SIP-Domänennamen des Skype Room-System Kontos in Betreff oder Betreff alt ist, müssen Sie die auf dem Zertifikat angezeigten Domänen unter den vertrauenswürdigen Domänen konfigurieren. Registrierungsschlüssel auf dem Skype Room System Console-Computer. In Ihrem Skype Room System-Administrator Handbuch wird erläutert, wie und wo vertrauenswürdige Domänen im Skype for Business-Client hinzugefügt werden. 
  
Nehmen wir beispielsweise an, dass die in Skype for Business Server konfigurierten Zertifikate einen Betreff/Betreff-Alternativnamen von "Contoso" aufweisen. LOCAL "und eine der SIP-Domänen, die einem Benutzer für die Anmeldeadresse des Skype-Chatrooms zugewiesen sind, lautet" confrm1@contoso.net ". Da contoso.net nicht im Zertifikat vorhanden ist, müssen Sie "contoso. local" auf dem Skype Room-System Computer als vertrauenswürdige Domäne in der Registrierung konfigurieren, wie dies in Ihrem Skype Room System-Administrator Handbuch erläutert wird. 
  

