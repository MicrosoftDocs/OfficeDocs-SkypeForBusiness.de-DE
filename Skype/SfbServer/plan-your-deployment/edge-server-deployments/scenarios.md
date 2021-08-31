---
title: Edgeserverszenarien in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Zusammenfassung: Überprüfen Sie diese Szenarien, um Ihre Edgeservertopologie in Skype for Business Server zu planen.'
ms.openlocfilehash: 4035418426975b79a35be7ec84c6affac3ab92d5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732083"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Edgeserverszenarien in Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie diese Szenarien, um Ihre Edgeservertopologie in Skype for Business Server zu planen.
  
Es gibt einige Szenariendiagramme, die Sie bei der Visualisierung und Entscheidung darüber unterstützen können, welche Skype for Business Server Edgeservertopologie Sie implementieren möchten. Nachdem Sie einen guten Kandidaten ausgewählt haben, können Sie sich über die Umgebungsanforderungen informieren, die Sie erfüllen müssen. Das Folgende gilt für alle Szenarien, daher wird es zuerst erwähnt.
  
Diese Abbildungen, die nur zu Beispielzwecken dargestellt werden (und als solche IPv4- und IPv6-Beispieldaten enthalten), stellen nicht den tatsächlichen Kommunikationsfluss dar, sondern eine allgemeine Übersicht über Ihren möglichen Datenverkehr. Portdetails finden Sie auch in den Portdiagrammen für jedes szenario unten.
  
Die Diagramme zeigen .com für die externe Schnittstelle und .net für die interne Schnittstelle, die auch Beispielmaterial ist. Ihre eigenen Einträge können natürlich ganz anders sein, wenn Sie Ihren eigenen endgültigen Edge-Plan zusammenstellen.
  
Wir schließen den Director (eine optionale Komponente) in keinem der Diagramme ein, aber Sie können dies separat lesen (dies wird in anderen Planungsthemen erwähnt).
  
Wie oben erwähnt, sind beispiel-IPv6-Daten in den Diagrammen enthalten. Der Großteil der Dokumentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) bezieht sich auf IPv4, aber Sie werden sicher unterstützt, wenn Sie IPv6 verwenden möchten. Beachten Sie, dass Sie IPv6-Adressen in Ihrem zugewiesenen Adressraum benötigen und diese mit interner und externer Adressierung wie bei IPv4-IPs arbeiten müssen. Dank Windows können Sie die Dualstapelfunktion verwenden, die ein separater und eindeutiger Netzwerkstapel für IPv4 und IPv6 ist. Auf diese Weise können Sie bei Bedarf IPv4- und IPv6-Adressen gleichzeitig zuweisen.
  
Es gibt NAT-Geräte, die NAT64 (IPv6 zu IPv4) und NAT66 (IPv6 zu IPv6) zulassen. Dies gilt für die Verwendung mit Skype for Business Server.
  
> [!IMPORTANT]
> Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) verwenden, müssen Sie IPv4 auf der internen Schnittstelle verwenden, damit sie funktioniert. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Einzelner konsolidierter Skype for Business Server Edgeserver mit privaten IP-Adressen und NAT

In diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Dies bedeutet, dass Sie weniger für Hardware ausgeben und eine einfachere Bereitstellung haben. Wenn hohe Verfügbarkeit ein Muss ist, sehen Sie sich die unten aufgeführten skalierten konsolidierten Szenarien an.
  
![Edgeszenario für einen einzelnen konsolidierten Edgeserver mit privater IP mit NAT.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerkperimeter für Edgeszenario mit einem einzelnen konsolidierten Edgeserver.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Einzelner konsolidierter Skype for Business Server-Edgeserver mit öffentlichen IP-Adressen

In diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Dies bedeutet, dass Sie weniger für Hardware ausgeben und eine einfachere Bereitstellung haben. Wenn hohe Verfügbarkeit ein Muss ist, sehen Sie sich die unten aufgeführten skalierten konsolidierten Szenarien an.
  
![Edgeszenario für einen einzelnen konsolidierten Edgeserver mit öffentlicher IP.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerkperimeter für Edgeszenario mit einem einzelnen konsolidierten Edgeserver.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skalierter konsolidierter Skype for Business Server Edgepool mit DNS-Lastenausgleich, privaten IP-Adressen und NAT

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, was Ihnen die Vorteile der Skalierbarkeit und Failoverunterstützung bietet.
  
![Edgeszenario für skalierten konsolidierten Edgeserver, DNS LB mit privater IP mit NAT.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Außerdem haben wir ein Diagramm für skalierte konsolidierte Edgepools mit DNS-Lastenausgleich.
  
![Netzwerkperimeter für Edgeszenario skalierter konsolidierter Edgeserver mit DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Skalierter konsolidierter Skype for Business Server Edgepool mit DNS-Lastenausgleich und öffentlichen IP-Adressen

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, was Ihnen die Vorteile der Skalierbarkeit und Failoverunterstützung bietet.
  
![Edgeszenario für skalierten konsolidierten Edgeserver, DNS LB mit öffentlicher IP.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Außerdem haben wir ein Diagramm für skalierte konsolidierte Edgepools mit DNS-Lastenausgleich.
  
![Netzwerkperimeter für Edgeszenario skalierter konsolidierter Edgeserver mit DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Skalierter konsolidierter Skype for Business Server Edgepool mit Hardwarelastenausgleich

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, was Ihnen die Vorteile der Skalierbarkeit und Failoverunterstützung bietet.
  
![Edgeszenario für skalierten konsolidierten Edgeserver mit HLB.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
