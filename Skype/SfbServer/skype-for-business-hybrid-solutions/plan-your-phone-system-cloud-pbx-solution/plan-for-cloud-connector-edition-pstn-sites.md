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
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre PsTN-Standorte der Cloud Connector Edition planen, um eine effiziente und kostengünstige Anrufweiterleitung sicherzustellen.
ms.openlocfilehash: 51bc6c0b7bf536849ebc9d6b1338faa6db8800fee86c4515db4c5f15bf9115b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339961"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planen von PSTN-Standorten der Cloud Connector Edition

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre PsTN-Standorte der Cloud Connector Edition planen, um eine effiziente und kostengünstige Anrufweiterleitung sicherzustellen.
  
In diesem Thema wird beschrieben, was Sie über Cloud Connector Edition und Anrufrouting wissen müssen, damit Sie Ihre Cloud Connector PSTN-Standorte planen können. Ein PSTN-Standort ist eine Kombination aus Cloud Connector-Appliances, die am gleichen Standort bereitgestellt werden und mit allgemeinen PSTN-Gateways verbunden sind. In diesem Thema wird beschrieben, wie Sie Ihre Cloud Connector-Standorttopologie einrichten, um sicherzustellen, dass Ihre Cloud Connector-Standorte sowohl eingehendes als auch ausgehendes Routing für alle Benutzer, die einem Standort zugewiesen sind, auf die kostengünstigste und effektivste Weise verarbeiten können. Weitere Informationen zu Cloud Connector und den Vorteilen von PSTN-Standorten finden Sie unter [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Cloud Connector PSTN-Standorte und Anrufweiterleitung

Cloud Connector-PSTN-Standorte sind ein Topologiekonstrukt, das erstellt wurde, um unnötige Fern- und Ländergespräche zu verhindern und sicherzustellen, dass ausgehende Notrufe an den entsprechenden Trunk weitergeleitet werden. Um eine kostengünstige und effiziente Weiterleitung von Anrufen zu gewährleisten, einschließlich Notrufe, müssen Sie Ihre PSTN-Standorte sorgfältig planen und angeben, wie den einzelnen Standorten Benutzer zugewiesen werden. 
  
Im Rahmen Ihrer Planung für Cloud Connector ist es wichtig, dass Sie mit Ihren Netzbetreibern darüber sprechen, wo sich Ihre Büros und Benutzer befinden und wo die PSTN-Trunks vom Netzbetreiber beendet werden. Sie müssen mit Ihren Netzbetreibern zusammenarbeiten, um zu bestimmen, wie Notrufe weitergeleitet werden können, und diese Informationen dann verwenden, um Cloud Connector-PSTN-Standorte zu definieren und Benutzern die entsprechenden Standorte zuzuweisen. Sie sollten beispielsweise sicherstellen, dass die Trunks, die an einem Rechenzentrum enden, in dem der PSTN-Standort gestreckt ist, so konfiguriert sind, dass sowohl eingehendes als auch ausgehendes Routing für alle Nummern verarbeitet wird, die den Benutzern an diesem Standort zugewiesen sind. 
  
Jede Cloud Connector-Appliance kann mit mehreren IP-Gateways, IP-Nebenstellenanlagen oder Session Border Controllern (SBCs) verbunden werden. Da die Gateways und Nebenstellenanlagen mit Telco-Trunks (PRI- oder SIP-Trunks) verbunden sind, sind Cloud Connector-Appliances für eingehende und ausgehende Anrufe logisch mit PSTN-Trunks verbunden. Mit Cloud Connector und lokaler FESTNETZ-Anbindung erhalten Sie den Trunk und die zugehörigen Telefonnummern von Ihrem lokalen Netzbetreiber. Wenn Es sich bei Ihrem Unternehmen um ein großes Unternehmen handelt, verfügen Sie möglicherweise über mehr als einen Netzbetreiber – insbesondere, wenn Ihr Unternehmen mehrere Städte, Bundesstaaten oder Länder umfasst. Da Ihr Netzbetreiber die Telefonnummer besitzt, ist der Netzbetreiber für die Behandlung von Notrufen verantwortlich.
  
Skype for Business Online behandelt alle Cloud Connector-Appliances an einem Standort gleich und leitet ausgehende Anrufe rotierend an Cloud Connector-Appliances am selben Standort weiter. Jeder Cloud Connector an einem Standort ist mit dem gleichen Satz von PSTN-Trunks verbunden (vollständig vergittert). Da jeder Benutzer einem Cloud Connector-PSTN-Standort zugeordnet ist, werden alle ausgehenden Anrufe dieses Benutzers (Normal oder Notfall) einer der Cloud Connector-Appliances am PSTN-Standort zugewiesen, dem der Benutzer zugeordnet ist. 
  
Cloud Connector führt statisches Anrufrouting an die angeschlossenen IP-Gateways, IP-Nebenstellenanlagen, SBCs oder direkten PSTN-Trunks durch. Cloud Connector ist noch nicht in der Lage, ein dynamisches Routing zu einem Trunk basierend auf dem Ziel (für das Routing mit den geringsten Kosten) oder basierend auf dem Ursprung (statische oder dynamische Notrufe) durchzuführen. Eingehende Anrufe stellen kein Problem dar, da der Anruf nur von einem Trunk stammen kann, der der Nummer zugeordnet ist. Ausgehende Anrufe können jedoch an eine beliebige Cloud Connector-Appliance an einem Standort (und durch erweiterungsweise die pstn-Trunks, die mit dieser Cloud Connector-Appliance verbunden sind) gehen, was zu unerwünschten Ferngesprächen führen kann. Darüber hinaus werden Notrufe nicht durchgestellt, wenn der Cloud Connector-PSTN-Standort über Rechenzentren mit unterschiedlichen Vorwahlen oder Netzbetreibern gestreckt wird.
  
## <a name="an-example"></a>Ein Beispiel

Das folgende Beispiel zeigt, wie Trunks zu PSTN-Standorten gruppiert werden und wie Den Standorten Benutzer zugewiesen werden. Gehen Sie für contoso-Unternehmen folgendermaßen vor:
  
- Es gibt vier Benutzer: 
    
  - Benutzer A in Redmond WA (USA)
    
  - Benutzer B in Bellevue WA (USA)
    
  - Benutzer C in Centralia WA (USA)
    
  - Benutzer D in Portland OR (USA)
    
- Netzbetreiber A bietet Telefonnummern und Trunks in:
    
  - Redmond (Vorwahl 425)
    
  - Bellevue (Vorwahl 425)
    
  - Centralia (Vorwahl 360)
    
- Netzbetreiber B bietet Telefonnummern und Trunks in:
    
  -  Portland (Vorwahl 503)
    
Da sich Benutzer A in Redmond (Rechenzentrum A) und Benutzer B in Bellevue (Rechenzentrum B) in benachbarten Umgebungen und in derselben Vorwahl (425) befinden, sollte Netzbetreiber A in der Lage sein, einen Notruf von Benutzer A in Redmond auf dem Trunk in Bellevue entgegenzunehmen. 
  
Daher können sich die Benutzer A und B sowie die Cloud Connector-Trunks für Bellevue und Redmond wahrscheinlich am gleichen Cloud Connector-PSTN-Standort befinden, wie im folgenden Diagramm dargestellt. Notrufe von Benutzern in einem Büro können an Trunks im anderen Büro weitergeleitet werden. Sie sollten jedoch bei Ihrem Netzbetreiber überprüfen, ob dies funktioniert.
  
![Einrichten von PSTN-Standorten](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Berücksichtigen Sie auch die folgenden Beispiele:
  
- Benutzer C in Centralia, dessen Nummer von Netzbetreiber A bereitgestellt wird, befindet sich zwei Autostunden entfernt und in einer anderen Vorwahl (360) von anderen Netzbetreiber-A-Benutzern in der Vorwahl Bellevue und Redmond 425. 
    
    Selbst wenn ein Anruf von Netzbetreiber A kommt, ist es daher möglich, dass die Anrufweiterleitungssoftware des Netzbetreibers in der Centralia-Ortsvorwahl 360 einen eingehenden Notruf von Benutzer B in Bellevue Vorwahl 425 ablehnen kann. In diesem Fall ist es wichtig, dass der Netzbetreiber bestätigt, dass Cloud Connector und die zugehörigen Trunks an den PsTN-Standorten von Centralia Anrufe über Entfernungen und Ortsvorwahlen verarbeiten können.
    
- Benutzer D in Portland verwendet eine Nummer und einen Trunk, die von Netzbetreiber B bereitgestellt werden. Daher ist es sehr unwahrscheinlich, dass Netzbetreiber B einen Notruf von einer Telefonnummer entgegennimmt, die im Besitz von Netzbetreiber A ist. Benutzer D und die Cloud Connector-Appliance und zugeordnete Trunks in Portland müssen sich also an einem anderen PSTN-Standort befinden.
