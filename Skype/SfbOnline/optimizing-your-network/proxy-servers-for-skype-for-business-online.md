---
title: Proxyserver für Skype for Business Online und Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers mit Skype for Business.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240414"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Proxyserver für Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Dieser Artikel enthält Anleitungen zur Verwendung eines Proxyservers mit Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

In Bezug auf Skype for Business-Datenverkehr über Proxys empfiehlt Microsoft, Proxys zu umgehen. Durch Proxys wird die Sicherheit Skype for Business, da der Datenverkehr bereits verschlüsselt ist.
  
Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zu einer negativen Benutzererfahrung in Teams- oder Skype for Business-Szenarien wie Audio und Video, in denen Echtzeitstreams unerlässlich sind.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Wenn Sie einen Proxyserver verwenden müssen

In manchen Organisationen ist die Umgehung eines Proxys für Skype for Business-Datenverkehr nicht möglich. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu.
    
- Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien:
    
  - [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](media-quality-and-network-connectivity-performance.md)
    
  - [Optimieren Ihres Netzwerks für Skype for Business Online](optimizing-your-network.md)
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## <a name="related-topics"></a>Verwandte Themen

[Optimieren Ihres Netzwerks für Skype for Business Online](optimizing-your-network.md)
 
