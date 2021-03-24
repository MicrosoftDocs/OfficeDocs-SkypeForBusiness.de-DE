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
description: In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector Edition-PSTN-Standorte planen, um ein effizientes und kostengünstiges Anrufrouting sicherzustellen.
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096229"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planen von PSTN-Standorten der Cloud Connector Edition

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)
 
In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector Edition-PSTN-Standorte planen, um ein effizientes und kostengünstiges Anrufrouting sicherzustellen.
  
In diesem Thema wird beschrieben, was Sie über Cloud Connector Edition und Anrufrouting wissen müssen, damit Sie Ihre Cloud Connector-PSTN-Standorte planen können. Ein PSTN-Standort ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit gemeinsamen PSTN-Gateways verbunden sind. In diesem Thema wird beschrieben, wie Sie Ihre Cloud Connector-Standorttopologie einrichten, um sicherzustellen, dass Ihre Cloud Connector-Websites sowohl ein- als auch ausgehendes Routing für alle Benutzer verarbeiten können, die einem Standort zugewiesen sind, möglichst kostengünstig und effektiv. Weitere Informationen zu Cloud Connector und den Vorteilen von PSTN-Websites finden Sie unter [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Cloud Connector PSTN-Standorte und Anrufrouting

Cloud Connector PSTN-Standorte sind ein Topologiekonstrukt, das erstellt wurde, um unnötige Ferngespräche und länderübergreifende Tarife zu verhindern und um sicherzustellen, dass ausgehende Notrufe an den entsprechenden Trunk geroutet werden. Um ein kosteneffektives und effizientes Routing von Anrufen, einschließlich Notrufen, sicherzustellen, müssen Sie Ihre PSTN-Standorte sorgfältig planen und die Benutzer den einzelnen Standorten zugewiesen werden. 
  
Im Rahmen Ihrer Planung für Cloud Connector ist es wichtig, dass Sie mit Ihren Netzbetreibern darüber sprechen, wo sich Ihre Büros und Benutzer befinden und wo die PSTN-Trunks vom Netzbetreiber beendet werden. Sie müssen mit Ihren Netzbetreibern zusammenarbeiten, um zu bestimmen, wie Notrufe geroutet werden können, und diese Informationen dann verwenden, um Cloud Connector-PSTN-Standorte zu definieren und Benutzern die entsprechenden Standorte zuzuordnen. Sie sollten z. B. sicherstellen, dass die Trunks, die in einem Rechenzentrum beendet werden, in dem der PSTN-Standort gestreckt ist, so konfiguriert sind, dass sowohl ein- als auch ausgehendes Routing für alle Den Benutzern an diesem Standort zugewiesenen Nummern verwendet werden. 
  
Jede Cloud Connector-Appliance kann mit mehreren IP-Gateways, IP-Nebenstellenanlagen oder Session Border Controllers (SBCs) verbunden werden. Da gateways und PBXs mit Telekommunikations trunks (PRI- oder SIP-Trunks) verbunden sind, sind Cloud Connector-Appliances logisch mit PSTN-Trunks für eingehende und ausgehende Anrufe verbunden. Mit Cloud Connector und lokaler PSTN-Konnektivität erhalten Sie den Trunk und die zugehörigen Telefonnummern von Ihrem lokalen Netzbetreiber. Wenn Es sich bei Ihrem Unternehmen um ein großes Unternehmen handelt, haben Sie möglicherweise mehr als einen Netzbetreiber, insbesondere wenn sich Ihr Unternehmen über mehrere Städte, Bundesstaaten oder Länder erstreckt. Da Ihr Netzbetreiber die Telefonnummer besitzt, ist der Netzbetreiber für die Behandlung von Notrufen verantwortlich.
  
Skype for Business Online behandelt alle Cloud Connector-Appliances an einem Standort gleich und führt ausgehende Anrufe drehend an Cloud Connector-Appliances am gleichen Standort weiter. Jeder CloudConnector an einem Standort ist mit demselben Satz von PSTN-Trunks (vollständig vergittert) verbunden. Da jeder Benutzer einem Cloud Connector-PSTN-Standort zugeordnet ist, wird jeder ausgehende Anruf von diesem Benutzer (normal oder notfalls) einer der Cloud Connector-Appliances am PSTN-Standort zugewiesen, dem der Benutzer zugeordnet ist. 
  
Cloud Connector führt statisches Anrufrouting an angeschlossene IP-Gateways, IP-PBXs, SBCs oder direkte PSTN-Trunks durch. Cloud Connector ist noch nicht in der Lage, dynamisches Routing zu einem Trunk basierend auf dem Ziel (für kostengünstigstes Routing) oder basierend auf dem Ursprung (statische oder dynamische Notrufe) zu erstellen. Eingehende Anrufe sind kein Problem, da der Anruf nur von einem Trunk stammen kann, der der Nummer zugeordnet ist. Ausgehende Anrufe können jedoch an jede Cloud Connector-Appliance an einem Standort (und durch Erweiterung die an diese Cloud Connector-Appliance angefügten PSTN-Trunks) gehen, die unerwünschte Ferngespräche verursachen können. Darüber hinaus werden Notrufe nicht durchgehen, wenn der Cloud Connector PSTN-Standort über Rechenzentren mit unterschiedlichen Bereichscodes oder Netzbetreibern gestreckt wird.
  
## <a name="an-example"></a>Ein Beispiel

Im folgenden Beispiel wird gezeigt, wie Trunks zu PSTN-Standorten gruppieren und benutzer den Websites zugewiesen werden. Gehen Sie für das Unternehmen Contoso wie folgt vor:
  
- Es gibt vier Benutzer: 
    
  - Benutzer A in Redmond WA (USA)
    
  - Benutzer B in Bellevue WA (USA)
    
  - Benutzer C in Centralia WA (USA)
    
  - Benutzer D in Portland OR (USA)
    
- Netzbetreiber A bietet Telefonnummern und Trunks in:
    
  - Redmond (Vorwahl 425)
    
  - Bellevue (Vorwahl 425)
    
  - Zentralia (Vorwahl 360)
    
- Netzbetreiber B bietet Telefonnummern und Trunks in:
    
  -  Portland (Vorwahl 503)
    
Da sich Benutzer A in Redmond (Rechenzentrum A) und Benutzer B in Bellevue (Data Center B) in Vororten nebeneinander und in derselben Vorwahl (425) befinden, sollte Netzbetreiber A in der Lage sein, einen Notruf von Benutzer A in Redmond im Trunk in Bellevue zu nehmen. 
  
Daher können sich die Benutzer A und B und die Cloud Connector-Trunks für Bellevue und Redmond wahrscheinlich am gleichen Cloud Connector-PSTN-Standort wie im folgenden Diagramm gezeigt. Notrufe von Benutzern in einem Büro können an Trunks in der anderen geroutet werden. Sie sollten jedoch bei Ihrem Netzbetreiber überprüfen, ob dies funktioniert.
  
![Einrichten von PSTN-Websites](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Berücksichtigen Sie auch die folgenden Beispiele:
  
- Benutzer C in centralia, dessen Nummer vom Netzbetreiber A bereitgestellt wird, ist eine zweistündige Fahrt entfernt und in einer anderen Vorwahl (360) als andere Carrier A-Benutzer in der Vorwahl Bellevue und Redmond 425. 
    
    Daher ist es möglich, dass die Anrufroutingsoftware des Netzbetreibers in der Centralia-Vorwahl 360 einen eingehenden Notruf vom Benutzer B in der Vorwahl 425 bellevue ablehnen kann, selbst wenn ein Anruf vom Netzbetreiber A kommt. In diesem Fall ist es wichtig, dass der Netzbetreiber bestätigt, dass Cloud Connector und die zugehörigen Trunks in den Centralia PSTN-Standorten Anrufe über Entfernungen und Ortscodes hinweg verarbeiten können.
    
- Benutzer D in Portland verwendet eine Nummer und einen Trunk, die vom Netzbetreiber B bereitgestellt werden. Es ist daher sehr unwahrscheinlich, dass Carrier B einen Notruf von einer Telefonnummer nimmt, die sich im Besitz von Carrier A befindet. Daher müssen sich Benutzer D und die Cloud Connector-Appliance und die zugehörigen Trunks in Portland an einem anderen PSTN-Standort befinden.
