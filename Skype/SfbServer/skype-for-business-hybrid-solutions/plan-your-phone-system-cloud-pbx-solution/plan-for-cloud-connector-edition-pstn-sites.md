---
title: Planen von PSTN-Standorten der Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lesen Sie dieses Thema, um Informationen zum Planen Ihrer Websites Cloud Connector Edition PSTN um effizient und Anrufrouting sicherzustellen.
ms.openlocfilehash: fa224bd4fa3dc1d0be5db8104e414f9a78d01b30
ms.sourcegitcommit: 58934985891818fa505ae742b1e750edccadd870
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "25576519"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planen von PSTN-Standorten der Cloud Connector Edition
 
Lesen Sie dieses Thema, um Informationen zum Planen Ihrer Websites Cloud Connector Edition PSTN um effizient und Anrufrouting sicherzustellen.
  
In diesem Thema wird beschrieben, um Cloud Connector Edition kennen und Anrufrouting, damit die Cloud Connector PSTN-Websites planen zu können, benötigen Sie. Eine PSTN-Website ist eine Kombination von Cloud-Connector Appliances und am selben Speicherort und zu allgemeinen PSTN-Gateways für diese Verbindung bereitgestellt. In diesem Thema konzentriert sich auf Ihre Cloud-Connector Standorttopologie einrichten, um sicherzustellen, dass Ihre Websites Cloud Connector verarbeitet werden können, eingehende und ausgehende routing für alle Benutzer auf die meisten Kosten effiziente und effektive Weise möglich, eine Website zugewiesen. Weitere Informationen zu Cloud-Connector und den Vorteilen von PSTN-Websites unbedingt lesen [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>PSTN-Standorte für Cloud Connector und Anrufweiterleitung

Cloud-Connector PSTN-Websites sind eine Topologie Konstrukt erstellt unnötige Ferngespräche und Konfigurationsrichtlinien Land Tarife verhindert, und stellen Sie sicher, dass ausgehende Notrufe an den entsprechenden Trunk weitergeleitet werden. Um ein kosteneffektives und effizientes Weiterleiten von Anrufen sicherzustellen – darunter Anrufe bei Notrufdiensten, müssen die PSTN-Standorte und die Zuweisung von Benutzern zu jedem Standort sorgfältig geplant werden. 
  
Im Rahmen der Planung von Cloud-Connector ist es wichtig, dass Sie sprechen Sie mit Ihrem Netzbetreiber zu, wo Ihre Büros und Benutzer befinden und die PSTN-Trunks, in dem von der Netzbetreiber zu beenden. Sie müssen entwickelt Ihrer Netzbetreibern, um zu bestimmen, wie Emergency aufruft weitergeleitet werden können, und klicken Sie dann diese Informationen verwenden, um Cloud Connector PSTN-Websites zu definieren und Zuweisen von Benutzern zu den entsprechenden Standorten. Beispielsweise sollten Sie sicherstellen, dass die Trunks, die an ein Datencenter zu beenden, in dem die PSTN-Website gestreckt konfiguriert sind, so behandeln Sie eingehende und ausgehende routing für alle Zahlen, die Benutzern an diesem Standort zugewiesen sind. 
  
Jede Appliance Cloud Connector kann mehrere IP-Gateways, IP-PBX-Anlagen oder Session Border Controller (SBCs) verbunden sein. Da die Gateways und Nebenstellenanlagen Telekommunikation Trunks (PRI oder SIP-Trunks) verbunden sind, werden Cloud Connector Appliances logisch mit PSTN-Trunks für eingehende und ausgehende Anrufe verbunden. Mit Cloud Connector und PSTN-Konnektivität vor Ort erhalten Sie den Trunk und die zugeordneten Telefonnummern von Ihrem Anbieter vor Ort. Im Falle eines großen Unternehmens nutzen Sie vielleicht mehrere Anbieter – insbesondere, wenn sich Ihr Geschäft über mehrere Städte, Bundesländer oder Länder/Regionen erstreckt. Da Ihr Anbieter Eigentümer der Telefonnummer ist, ist der Anbieter für die Handhabung von Notrufen verantwortlich.
  
Skype für Business Online alle Cloud Connector Einheiten in einer Website gleichmäßig behandelt und ausgehende Anrufe auf Basis rotierenden Cloud Connector Appliances am gleichen Standort weitergeleitet. Jeder Cloud Connector an einem Standort ist kreuzweise mit derselben Gruppe von PSTN-Trunks verbunden (vollvermascht). Da jeder Benutzer mit einer Cloud-Connector PSTN-Website verknüpft ist, werden alle ausgehenden Anrufs über diesen Benutzer (normale oder Notfall) eine Cloud-Connector Appliance in der PSTN-Website zugewiesen werden, die der Benutzer zugeordnet ist. 
  
Cloud-Connector wird statische Anrufrouting einer seiner angefügte IP-Gateways, IP-Nebenstellenanlagen, SBCs oder direkte PSTN-Trunks. Cloud-Connector ist noch nicht dynamische Weiterleitung an einen Trunk basierend auf dem Ziel (für das routing zu minimalen Kosten) oder basierend auf Ursprung (statische oder dynamische notrufdienste) werden können. Eingehende Anrufe sind kein Problem, da der Anruf einen Trunk mit der Nummer verbundenen nur stammen kann. Ausgehende Anrufe können jedoch Cloud Connector-Einheiten in einer Website (und durch die PSTN-Trunks mit dieser Cloud Connector Einheit verbundenen Erweiterung) wechseln was unerwünschte Ferngespräche führen kann. Darüber hinaus werden Notrufe nicht durchlaufen, wenn die Cloud Connector PSTN-Website in Rechenzentren mit verschiedenen Vorwahlen oder Netzbetreibern gestreckt wird.
  
## <a name="an-example"></a>Ein Beispiel

Das folgende Beispiel zeigt, wie Trunks mit PSTN-Websites zu gruppieren und wie Sie die Websites Benutzer zuweisen. Nehmen wir für das Unternehmen Contoso Folgendes an:
  
- Es gibt vier Benutzer:   
    
  - Benutzer A in Redmond WA (USA)
    
  - Benutzer B in Bellevue WA (USA)
    
  - Benutzer C in Centralia WA (USA)
    
  - Benutzer D in Portland OR (USA)
    
- Netzbetreiber A bietet Telefonnummern und -Trunks in:
    
  - Redmond (Vorwahl 425)
    
  - Bellevue (Vorwahl 425)
    
  - Centralia (Vorwahl 360)
    
- Netzbetreiber B bietet Telefonnummern und -Trunks in:
    
  -  Portland (Vorwahl 503)
    
Da Benutzer A in Redmond (-Rechenzentrum A) und Benutzer B in Bellevue (Data Center B) sind in Vororte nebeneinander und in der gleichen Ortskennzahl (425), sollten Netzbetreiber A eine Notrufnummer von Benutzer A in Redmond für den Trunk in Bellevue übernehmen können. 
  
Daher können Benutzer A und B und die Cloud Connector Trunks für Bellevue und Redmond, wahrscheinlich am gleichen Standort Cloud Connector PSTN werden wie in der folgenden Abbildung dargestellt. Notrufe von Benutzern in einem Büro kann an Trunks im anderen Büro weitergeleitet werden. Sie sollten jedoch mit Ihrem Netzbetreiber überprüfen, die dies funktioniert.
  
![Einrichten von PSTN-Standorten](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Beachten Sie auch die folgenden Beispiele:
  
- Benutzer C in Centralia, dessen Nummer von Anbieter A bereitgestellt wird, befindet sich zwei Stunden Autofahrt entfernt und in einem anderen Vorwahlbereich (360) als andere Benutzer von Anbieter A im Vorwahlbereich 425 von Bellevue und Redmond.  
    
    Aus diesem Grund, auch wenn Sie ein Anruf von Netzbetreiber A stammt, ist es möglich, dass der Netzbetreiber, dass routing-Software Centralia Ortskennzahl 360 Notfall eingehende Ablehnung Aufruf von Benutzer B Bellevue Ortskennzahl 425 stammen. In diesem Fall ist es wichtig, dass der Netzbetreiber bestätigen Sie, dass Cloud Connector und dessen zugehörige Trunks auf den Websites Centralia PSTN Anrufe über Abstände und Ortskennzahlen verarbeitet werden können.
    
- Benutzer D in Portland verwendet eine Reihe und Trunk bereitgestellt von Netzbetreiber B, daher ist es unwahrscheinlich, dass Netzbetreiber B einem Notruf Telefonnummer eines dauern wird gehört Netzbetreiber A. Damit Benutzer D und die Cloud Connector Appliance und zugehörige Trunks in Portland hat in einem anderen PSTN-Standort befinden.
    

