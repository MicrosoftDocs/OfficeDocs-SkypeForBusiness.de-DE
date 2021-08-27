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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers Microsoft Teams Server Skype for Business.
ms.openlocfilehash: 559a42c19aa47a9e72a5c0549e80f45de8d50fdf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582159"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Proxyserver für Skype for Business Online und Microsoft Teams

Dieser Artikel enthält Anleitungen zur Verwendung eines Proxyservers Teams Server Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

Wenn es um Teams oder Skype for Business Über Proxys geht, empfiehlt Microsoft, Proxys zu umgehen. Proxys sorgen nicht dafür, dass Teams oder Skype for Business sicherer sind, da der Datenverkehr bereits verschlüsselt ist.
  
Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zu einer negativen Benutzererfahrung in Teams- oder Skype for Business-Szenarien wie Audio und Video, in denen Echtzeitstreams unerlässlich sind.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Wenn Sie einen Proxyserver verwenden müssen

Einige Organisationen haben keine Möglichkeit, einen Proxy für Teams oder Skype for Business zu umgehen. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu.
    
- Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien: Vorbereiten ihres [Unternehmensnetzwerks für Teams](prepare-network.md)
  
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365- und Office 365-Netzwerkverbindungsprinzipien](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)