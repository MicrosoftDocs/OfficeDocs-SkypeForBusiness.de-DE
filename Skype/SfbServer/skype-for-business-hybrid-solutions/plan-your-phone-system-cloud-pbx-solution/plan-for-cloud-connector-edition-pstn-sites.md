---
title: Planen von PSTN-Standorten der Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector Edition-PSTN-Websites planen, um effizientes und kostengünstiges Anrufrouting zu gewährleisten.
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287034"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planen von PSTN-Standorten der Cloud Connector Edition
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector Edition-PSTN-Websites planen, um effizientes und kostengünstiges Anrufrouting zu gewährleisten.
  
In diesem Thema wird beschrieben, was Sie über Cloud Connector Edition und Anrufweiterleitung wissen müssen, damit Sie Ihre PSTN-Websites für Cloud Connectors planen können. Eine PSTN-Website ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden, und mit gemeinsamen PSTN-Gateways, die mit Ihnen verbunden sind. In diesem Thema wird erläutert, wie Sie Ihre Cloud Connector-Standorttopologie einrichten, um sicherzustellen, dass Ihre Cloud Connector-Websites sowohl ein-als auch ein ausgehendes Routing für alle Benutzer behandeln können, die einer Website auf die kostengünstigste und effektivste Weise zugewiesen sind. Weitere Informationen zu Cloud Connector und den Vorteilen von PSTN-Websites finden Sie unter [Plan für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>PSTN-Standorte für Cloud Connector und Anrufweiterleitung

Die PSTN-Standorte von Cloud Connector sind ein Topologie-Konstrukt, das zur Vermeidung unnötiger fern-und Auslandstarife sowie zur Sicherstellung, dass ausgehende Notrufe an den entsprechenden trunk weitergeleitet werden, erstellt wird. Um eine kostengünstige und effiziente Weiterleitung von Anrufen zu gewährleisten, einschließlich Anrufen an Notfalldienste, müssen Sie Ihre PSTN-Websites sorgfältig planen und feststellen, wie Benutzer den einzelnen Websites zugewiesen werden. 
  
Im Rahmen ihrer Planung für Cloud Connector ist es wichtig, dass Sie sich mit ihren Netzbetreibern unterhalten, wo sich ihre Büros und Benutzer befinden und wo die PSTN-Stämme vom Netzbetreiber beendet werden. Sie müssen mit ihren Netzbetreibern zusammenarbeiten, um festzustellen, wie Notrufe weitergeleitet werden können, und dann mithilfe dieser Informationen die PSTN-Websites von Cloud Connector definieren und Benutzern die entsprechenden Websites zuweisen. Beispielsweise sollten Sie sicherstellen, dass die Trunks, die in einem Rechenzentrum, in dem die PSTN-Website gestreckt wird, beendet werden, so konfiguriert sind, dass Sie ein-und ausgehendes Routing für alle Nummern behandeln, die den Benutzern an diesem Standort zugewiesen sind. 
  
Jede Cloud Connector-Appliance kann mit verschiedenen IP-Gateways, IP-PBX-Anlagen oder SBCS (Session Border Controllers) verbunden werden. Da die Gateways und PBX-Anlagen mit Telco-Stämmen (PRI-oder SIP-Stämme) verbunden sind, sind Cloud Connector-Appliances logisch mit PSTN-Stämmen für ein-und ausgehende Anrufe verbunden. Mit Cloud Connector und lokaler PSTN-Konnektivität erhalten Sie den trunk und die zugehörigen Telefonnummern von Ihrem lokalen Netzbetreiber. Im Fall eines großen Unternehmens nutzen Sie vielleicht mehrere Netzbetreiber – insbesondere, wenn sich Ihr Geschäft über mehrere Städte, Bundesländer oder Länder/Regionen erstreckt. Da Ihr Netzbetreiber Eigentümer der Telefonnummer ist, ist er für die Handhabung von Notrufen verantwortlich.
  
Skype for Business Online behandelt alle Cloud Connector-Appliances auf einer Website gleichermaßen und leitet ausgehende Anrufe auf rotierender Basis an Cloud Connector-Appliances am gleichen Standort weiter. Jeder Cloud-Connector in einer Website ist mit demselben Satz von PSTN-Stämmen verbunden (vollständig vernetzt). Da jeder Benutzer einer PSTN-Site des Cloud Connectors zugeordnet ist, werden alle ausgehenden Anrufe dieses Benutzers (normal oder Notfall) einer der Cloud Connector-Appliances in der PSTN-Website zugewiesen, der der Benutzer zugeordnet ist. 
  
Cloud Connector führt ein statisches Anrufrouting an die angeschlossenen IP-Gateways, IP-PBX-Anlagen, SBCS oder direkte PSTN-Stämme durch. Cloud Connector ist noch nicht in der Lage, das dynamische Routing zu einem Trunk auf der Grundlage des Ziels (für Least Cost Routing) oder basierend auf dem Ursprungszustand (statische oder dynamische Notrufe) zu durchlaufen. Eingehende Anrufe stellen kein Problem dar, da der Anruf nur von einem Trunk abgerechnet werden kann, der der Nummer zugeordnet ist. Ausgehende Anrufe können jedoch zu einer beliebigen Cloud Connector-Appliance an einer Website (und durch Erweiterung der an diese Cloud Connector-Appliance angeschlossenen PSTN-Stämme) geführt werden, die zu unerwünschten Ferngesprächen führen können. Darüber hinaus werden Notrufe nicht durchlaufen, wenn die PSTN-Website des Cloud Connectors über Rechenzentren mit unterschiedlichen Ortsnetzen oder Netzbetreibern gestreckt wird.
  
## <a name="an-example"></a>Ein Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie Trunks zu PSTN-Websites gruppieren und wie Benutzer den Websites zugewiesen werden. Nehmen wir für das Unternehmen Contoso Folgendes an:
  
- Es gibt vier Benutzer:  
    
  - Benutzer A in Redmond WA (USA)
    
  - Benutzer B in Bellevue WA (USA)
    
  - Benutzer C in Centralia WA (USA)
    
  - Benutzer D in Portland oder (USA)
    
- Carrier A bietet Telefonnummern und Trunks in:
    
  - Redmond (Vorwahl 425)
    
  - Bellevue (Vorwahl 425)
    
  - Centralia (Vorwahl 360)
    
- Carrier B bietet Telefonnummern und Trunks in:
    
  -  Portland (Vorwahl 503)
    
Da sich Benutzer a in Redmond (Rechenzentrum a) und Benutzer B in Bellevue (Rechenzentrum b) in Vororten nebeneinander und in der gleichen Vorwahl (425) befinden, sollte Carrier a in der Lage sein, einen Notruf vom Benutzer a in Redmond auf dem Stamm in Bellevue zu führen. 
  
Infolgedessen können Benutzer A und B sowie die Cloud-Connector-Stämme für Bellevue und Redmond wahrscheinlich auf der gleichen PSTN-Website wie in der folgenden Abbildung gezeigt werden. Notrufe von Benutzern in einem Büro können an Trunks im anderen Büro weitergeleitet werden. Sie sollten sich jedoch bei Ihrem Netzbetreiber erkundigen, ob dies funktionieren wird.
  
![Einrichten von PSTN-Standorten](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Beachten Sie auch die folgenden Beispiele:
  
- Benutzer C in Centralia, dessen Nummer von Anbieter A bereitgestellt wird, befindet sich zwei Stunden Autofahrt entfernt und in einem anderen Vorwahlbereich (360) als andere Benutzer von Anbieter A im Vorwahlbereich 425 von Bellevue und Redmond.  
    
    Auch wenn ein Anruf vom Netzbetreiber a kommt, ist es möglich, dass die Anruf Weiterleitungs Software des Netzbetreibers in Centralia-Vorwahl 360 einen eingehenden Notruf von Benutzer B in Bellevue-Vorwahl 425 ablehnen kann. In diesem Fall ist es wichtig, dass der Netzbetreiber bestätigt, dass der Cloud Connector und die dazugehörigen Stämme in den Centralia-PSTN-Websites Anrufe über Distanzen und Ortsvorwahl abwickeln können.
    
- Benutzer D in Portland verwendet eine Zahl und einen trunk, die von Carrier b bereitgestellt werden, daher ist es höchst unwahrscheinlich, dass Carrier b einen Notruf von einer Telefonnummer unternimmt, die dem Carrier a gehört. Daher müssen sich Benutzer D und die Cloud Connector-Appliance und zugehörige Trunks in Portland an einer anderen PSTN-Website befinden.
    

