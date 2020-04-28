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
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers mit Microsoft Teams oder Skype for Business.
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905677"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Proxyserver für Skype for Business Online und Microsoft Teams

Dieser Artikel enthält Anleitungen zur Verwendung eines Proxyservers mit Teams oder Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

Wenn es um Teams oder Skype for Business-Datenverkehr über Proxies geht, empfiehlt Microsoft, Proxys zu umgehen. Proxys machen Teams oder Skype for Business nicht sicherer, da der Datenverkehr bereits verschlüsselt ist.
  
Und ein Proxy kann Probleme verursachen. Leistungsbezogene Probleme können durch Latenz und Paketverlust in die Umgebung eingeführt werden. Probleme wie diese führen zu einer negativen Erfahrung in solchen Teams oder Skype for Business-Szenarien als Audio-und Videodaten, bei denen echt Zeitströme wichtig sind.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Wenn Sie einen Proxyserver verwenden müssen

Einige Organisationen haben keine Möglichkeit, einen Proxy für Teams oder Skype for Business-Datenverkehr zu umgehen. Wenn dies für Sie der Fall ist, müssen die oben genannten Probleme berücksichtigt werden.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu.
    
- Befolgen Sie die anderen Empfehlungen in unseren Netzwerkrichtlinien: [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)
  
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## <a name="related-topics"></a>Verwandte Themen

[Prinzipien von Office 365-Netzwerkverbindungen](https://aka.ms/pnc)

[Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)
