---
title: Proxyserver für Teams oder Skype für Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers mit Teams oder Skype für Unternehmen.
ms.openlocfilehash: 1b25d0554ec8c5dca113be0842149dae11850b7e
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "29972210"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Proxyserver für Teams oder Skype für Business Online

Dieser Artikel enthält Hinweise zur Verwendung eines Proxyservers mit Teams oder Skype für Unternehmen.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

Wenn es um Teams oder Skype für Business-Datenverkehr über Proxys geht, empfiehlt es sich Proxys umgangen. Proxys machen nicht Teams oder Skype für Unternehmen sicherer, da der Datenverkehr bereits verschlüsselt ist.
  
Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Probleme wie diese führt eine negative Erfahrung in solche Teams oder Skype für Geschäftsszenarien als audio und video, wobei in Echtzeit Datenströme wichtig sind.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Wenn Sie einen Proxyserver verwenden müssen

Einige Organisationen haben keine Möglichkeit, einen Proxy für Teams oder Skype für Business-Datenverkehr zu umgehen. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu.
    
- Folgen die anderen Empfehlungen in unsere Netzwerken Richtlinien:
    
  - [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## <a name="related-topics"></a>Verwandte Themen

[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 