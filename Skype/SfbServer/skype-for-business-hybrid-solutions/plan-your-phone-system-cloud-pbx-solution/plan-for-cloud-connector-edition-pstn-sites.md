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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector Edition-PSTN-Standorte planen, um eine effiziente und kostengünstige Anrufweiterleitung sicherzustellen.
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358801"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planen von PSTN-Standorten der Cloud Connector Edition

> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector Edition-PSTN-Standorte planen, um eine effiziente und kostengünstige Anrufweiterleitung sicherzustellen.
  
In diesem Thema wird beschrieben, was Sie über Cloud Connector Edition und Anrufweiterleitung wissen müssen, damit Sie Ihre Cloud Connector-PSTN-Standorte planen können. Ein PSTN-Standort ist eine Kombination von Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit gemeinsamen PSTN-Gateways verbunden sind. In diesem Thema wird erläutert, wie Sie Ihre Cloud Connector-Standorttopologie einrichten, um sicherzustellen, dass Ihre Cloud Connector-Standorte sowohl ein eingehendes als auch ein ausgehendes Routing für alle Benutzer, die einem Standort zugewiesen sind, auf möglichst kostengünstigste und effektive Weise verarbeiten können. Weitere Informationen zu Cloud Connector und den Vorteilen von PSTN-Standorten finden Sie unter [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Cloud Connector-PSTN-Standorte und Anrufweiterleitung

Bei Cloud Connector-PSTN-Standorten handelt es sich um eine Topologie-Konstruktion, die unnötige fern-und Länder Tarife verhindert und sicherstellt, dass ausgehende Notruf Anrufe an den entsprechenden trunk weitergeleitet werden. Um eine kostengünstige und effiziente Weiterleitung von Anrufen zu gewährleisten, einschließlich der Anrufe an Notfalldienste, müssen Sie Ihre PSTN-Standorte sorgfältig planen und wie Benutzer jedem Standort zugewiesen sind. 
  
Im Rahmen ihrer Planung für Cloud Connector ist es wichtig, dass Sie mit ihren Netzbetreibern darüber sprechen, wo sich ihre Niederlassungen und Benutzer befinden und wo die PSTN-Trunks vom Carrier beendet werden. Sie müssen mit ihren Netzbetreibern zusammenarbeiten, um zu ermitteln, wie Notrufe geroutet werden können, und diese Informationen dann zum Definieren von Cloud Connector-PSTN-Standorten und zum Zuweisen von Benutzern zu den entsprechenden Websites verwenden. Beispielsweise sollten Sie sicherstellen, dass die Trunks, die in einem Rechenzentrum, in dem der PSTN-Standort gedehnt wird, beendet werden, um eingehende und ausgehende Routing für alle Nummern zu verarbeiten, die den Benutzern an diesem Standort zugewiesen sind. 
  
Jede Cloud Connector-Appliance kann mit mehreren IP-Gateways, IP-Nebenstellenanlagen oder Session Border Controllern (SBCS) verbunden werden. Da die Gateways und PBX-Anlagen mit Telco-Trunks (PRI-oder SIP-Trunks) verbunden sind, sind Cloud Connector-Appliances für eingehende und ausgehende Anrufe logisch mit PSTN-Trunks verbunden. Mit Cloud Connector und lokaler PSTN-Konnektivität erhalten Sie den trunk und die dazugehörigen Telefonnummern von Ihrem lokalen Carrier. Wenn Ihr Unternehmen ein großes Unternehmen ist, verfügen Sie möglicherweise über mehr als einen Anbieter, insbesondere wenn sich Ihr Unternehmen über mehr als eine Stadt, einen Bundesstaat oder ein Land erstreckt. Da Ihr Carrier die Telefonnummer besitzt, ist der Carrier für die Handhabung von Notrufen verantwortlich.
  
Skype for Business Online behandelt alle Cloud Connector-Appliances an einem Standort gleichermaßen und leitet ausgehende Anrufe auf rotierender Basis an Cloud Connector-Appliances am gleichen Standort weiter. Jeder Cloud-Connector an einem Standort ist übergreifend mit derselben Gruppe von PSTN-Trunks (vollständig vernetzt) verbunden. Da jeder Benutzer einem Cloud Connector-PSTN-Standort zugeordnet ist, werden alle ausgehenden Anrufe von diesem Benutzer (normal oder Notfall) einer der Cloud Connector-Appliances am PSTN-Standort zugewiesen, dem der Benutzer zugeordnet ist. 
  
Cloud Connector führt statisches Anrufrouting zu seinen angeschlossenen IP-Gateways, IP-Nebenstellenanlagen, SBCS oder direkten PSTN-Trunks durch. Cloud Connector ist noch nicht zur dynamischen Weiterleitung an einen trunk basierend auf dem Ziel (für das Least Cost Routing) oder basierend auf dem Ursprung (statischer oder dynamischer Notruf) fähig. Eingehende Anrufe stellen kein Problem dar, da der Anruf nur von einem Trunk stammen kann, der der Nummer zugeordnet ist. Ausgehende Anrufe können jedoch an eine beliebige Cloud Connector-Appliance an einem Standort (und durch Erweiterung der an diese Cloud Connector-Appliance angeschlossenen PSTN-Trunks) gehen, was zu unerwünschten Ferngesprächen führen kann. Außerdem werden Notrufe nicht durchlaufen, wenn der Cloud Connector-PSTN-Standort über Rechenzentren mit unterschiedlichen Ortsvorwahl oder Netzbetreibern gestreckt wird.
  
## <a name="an-example"></a>Ein Beispiel

Im folgenden Beispiel wird das Gruppieren von Trunks zu PSTN-Standorten und das Zuweisen von Benutzern zu den Websites veranschaulicht. Für Contoso Company wird Folgendes vorausgesetzt:
  
- Es gibt vier Benutzer: 
    
  - Benutzer A in Redmond WA (USA)
    
  - Benutzer B in Bellevue WA (USA)
    
  - Benutzer C in Centralia WA (USA)
    
  - Benutzer D in Portland oder (USA)
    
- Carrier A stellt Telefonnummern und Trunks zur Verfügung:
    
  - Redmond (Ortskennzahl 425)
    
  - Bellevue (Ortsvorwahl 425)
    
  - Centralia (Ortskennzahl 360)
    
- Carrier B bietet Telefonnummern und Trunks in:
    
  -  Portland (Ortskennzahl 503)
    
Da sich Benutzer a in Redmond (Datencenter a) und Benutzer B in Bellevue (Rechenzentrum b) in Vororten nebeneinander und in derselben Vorwahl (425) befinden, sollte Carrier a in der Lage sein, einen Notruf von Benutzer a in Redmond im trunk in Bellevue zu tätigen. 
  
Folglich können sich Benutzer A und B sowie die Cloud-Connector-Trunks für Bellevue und Redmond wahrscheinlich am gleichen Cloud Connector-PSTN-Standort befinden wie im folgenden Diagramm dargestellt. Notrufe von Benutzern in einem Büro können an Trunks im anderen Standort weitergeleitet werden. Sie sollten sich jedoch bei Ihrem Carrier erkundigen, ob dies funktionieren wird.
  
![Einrichten von PSTN-Standorten](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Sehen Sie sich auch die folgenden Beispiele an:
  
- Benutzer C in Centralia, dessen Nummer von Carrier a bereitgestellt wird, ist zwei Stunden mit dem Auto entfernt und in einer anderen Ortskennzahl (360), von einem anderen Carrier ein Benutzer in der Vorwahl Bellevue und Redmond 425. 
    
    Selbst wenn ein Anruf von Carrier a stammt, ist es möglich, dass die Anruf Weiterleitungs Software des Carriers in Centralia Vorwahl 360 möglicherweise einen eingehenden Notruf von Benutzer B in Bellevue Vorwahl 425 ablehnt. In diesem Fall ist es wichtig, dass der Carrier bestätigt, dass Cloud Connector und die dazugehörigen Trunks an den Centralia-PSTN-Standorten Anrufe über Entfernungen und Ortsvorwahl hinweg verarbeiten können.
    
- Benutzer D in Portland verwendet eine Nummer und einen trunk, die von Carrier b bereitgestellt werden, daher ist es höchst unwahrscheinlich, dass Carrier b einen Notruf von einer Telefonnummer abnimmt, die dem Carrier a gehört. Daher müssen sich Benutzer D und die Cloud Connector-Appliance sowie zugehörige Trunks in Portland an einem anderen PSTN-Standort befinden.
    

