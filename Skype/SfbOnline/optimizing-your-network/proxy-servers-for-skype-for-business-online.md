---
title: Proxyserver für Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.
ms.openlocfilehash: a4369208ab277e0eb5490a637421de605235a0cd
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Proxyserver für Skype for Business Online

Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Es wird empfohlen, keinen Proxyserver zu verwenden

In Bezug auf Skype for Business-Datenverkehr über Proxys empfiehlt Microsoft, Proxys zu umgehen. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer.
  
Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zur Beeinträchtigung der Benutzerfreundlichkeit in Skype for Business-Szenarien mit Audio und Video, in denen Echtzeitstreams unerlässlich sind.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Wenn Sie einen Proxyserver verwenden müssen

In manchen Organisationen ist die Umgehung eines Proxys für Skype for Business-Datenverkehr nicht möglich. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu.
    
- Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien:
    
  - [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>Proxyanbieter mit integrierter Skype for Business-Unterstützung oder entsprechenden Konfigurationsoptionen

Dieser Abschnitt enthält Informationen zu Proxyanbietern, die Produkte oder Dienste bereitstellen, die nachweislich erfolgreich für Skype for Business-Datenverkehr verwendet werden können.
  
Für Organisationen, die **Bluecoat-Proxylösungen** verwenden, wurde eine neue Firmware veröffentlicht, die verschiedene Probleme im Zusammenhang mit folgenden Aspekten behebt:
    
  - Abfangen von Daten über SSL
    
  - OCSP-/SRL-Überprüfungen
    
  - SIP über TLS
    
  - Unterstützung für TURN
    
Die systemeigene Unterstützung von Bluecoat für Skype for Business kann leicht aktiviert werden, sodass relevanter Datenverkehr identifiziert und entsprechend verwaltet werden kann. Dies gewährleistet optimale Authentifizierung und Signalisierung sowie einen optimalen Fluss des Mediendatenverkehrs, damit Sie hohe Benutzerfreundlichkeit ohne Sicherheitsbedenken bereitstellen können.
    
Finden Sie in den folgenden Link Bluecoat Proxy eines Teils der Topologie des Netzwerks ist:https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>See Also

[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 