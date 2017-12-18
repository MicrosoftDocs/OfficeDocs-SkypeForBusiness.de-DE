---
title: "Proxyserver für Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht."
---

# Proxyserver für Skype for Business Online

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](7acaf2c2-35fa-490f-84cd-822e446e0fc7.md#MT_Footer).  
  
Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.
  
## Es wird empfohlen, keinen Proxyserver zu verwenden

In Bezug auf Skype for Business-Datenverkehr über Proxys empfiehlt Microsoft, Proxys zu umgehen. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer.
  
Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zur Beeinträchtigung der Benutzerfreundlichkeit in Skype for Business-Szenarien mit Audio und Video, in denen Echtzeitstreams unerlässlich sind.
  
## Wenn Sie einen Proxyserver verwenden müssen

Einige Organisationen haben keine Option, um einen Proxy für Skype für Business Datenverkehr umgehen. Ist das der Fall ist, müssen die Probleme weiter oben erwähnten Punkte aufbewahrt werden.
  
Microsoft empfiehlt außerdem dringend Folgendes:
  
- Verwenden Sie externe DNS-Auflösung.
    
- Verwenden Sie direktes UDP-basiertes Routing.
    
- Lassen Sie UDP-Datenverkehr zu. 
    
- Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien:
    
  - [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.
  
## Proxyanbieter mit integrierter Skype for Business-Unterstützung oder entsprechenden Konfigurationsoptionen

Dieser Abschnitt enthält Informationen zu Proxyanbietern, die Produkte oder Dienste bereitstellen, die nachweislich erfolgreich für Skype for Business-Datenverkehr verwendet werden können.
  
- Für Organisationen, die **Bluecoat-Proxylösungen** verwenden, wurde eine neue Firmware veröffentlicht, die verschiedene Probleme im Zusammenhang mit folgenden Aspekten behebt:
    
  - Abfangen von Daten über SSL
    
  - OCSP-/SRL-Überprüfungen
    
  - SIP über TLS
    
  - Unterstützung für TURN
    
    Die systemeigene Unterstützung von Bluecoat für Skype for Business kann leicht aktiviert werden, sodass relevanter Datenverkehr identifiziert und entsprechend verwaltet werden kann. Dies gewährleistet optimale Authentifizierung und Signalisierung sowie einen optimalen Fluss des Mediendatenverkehrs, damit Sie hohe Benutzerfreundlichkeit ohne Sicherheitsbedenken bereitstellen können.
    
    Lizenzinformationen finden Sie den folgenden Link Bluecoat Proxy ist Bestandteil der Suchtopologie Netzwerk
    
- https://support.Symantec.com/en_US/article.DOC9757.HTML
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

