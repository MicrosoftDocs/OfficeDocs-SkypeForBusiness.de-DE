---
title: Vertrauenswürdige Domänen von Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: In diesem Thema erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834115"
---
# <a name="skype-room-system-trusted-domains"></a>Vertrauenswürdige Domänen von Skype Room System
 
In diesem Thema erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
  
## <a name="trusted-domains"></a>Vertrauenswürdige Domänen

Der Skype for Business-Client zeigt ein Dialogfeld an, in dem Benutzer das Zertifikat von Skype for Business Server akzeptieren können, wenn sich die SIP-Domäne des Benutzerkontos von dem Namen im Betreff- oder Alternativnamen des Zertifikats abhing. Wenn das für Skype for Business Server in Ihrer Organisation konfigurierte Zertifikat nicht den Sip-Domänennamen des Skype Room System-Kontos unter "Subject" oder "Subject Alt Name" hat, müssen Sie diese Domänen konfigurieren, die auf dem Zertifikat unter dem Registrierungsschlüssel "Vertrauenswürdige Domänen" auf dem Skype Room System-Konsolencomputer angezeigt werden. Das vom Skype Room System vom Hersteller bereitgestellte Skype Room System Administratorhandbuch erläutert, wie und wo vertrauenswürdige Domänen im Skype for Business-Client hinzugefügt werden können. 
  
Nehmen wir beispielsweise an, dass die in Skype for Business Server konfigurierten Zertifikate den Alternativnamen "Betreff/Betreff" "CONTOSO" haben. LOCAL" und eine der SIP-Domänen, die einem Benutzer für die Skype Room System-Anmeldeadresse zugewiesen sind, ist "confrm1@contoso.net". Da contoso.net sich nicht im Zertifikat befindet, müssen Sie auf dem Computer mit Skype Room System "contoso.local" als vertrauenswürdige Domäne in der Registrierung konfigurieren, wie im vom Skype Room System vom Hersteller bereitgestellten Skype Room System Administrator's Guide erläutert. 
  

