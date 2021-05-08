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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers Microsoft Teams Server Skype for Business.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117723"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Proxyserver für Skype for Business Online und Microsoft Teams

Dieser Artikel enthält Anleitungen zur Verwendung eines Proxyservers Teams Server Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

Wenn es um Teams oder Skype for Business Über Proxys geht, empfiehlt Microsoft, Proxys zu umgehen. Durch Proxys wird die Sicherheit der Teams oder Skype for Business, da der Datenverkehr bereits verschlüsselt ist.
  
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