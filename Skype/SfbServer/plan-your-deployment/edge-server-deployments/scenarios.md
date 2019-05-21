---
title: Edge-Server-Szenarien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Zusammenfassung: Überprüfen Sie diese Szenarien, damit Sie Ihre Edge-Server-Topologie in Skype for Business Server planen können.'
ms.openlocfilehash: f978d3ac5da0611808b09c7556302f52478d95ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277153"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Edge-Server-Szenarien in Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie diese Szenarien, damit Sie Ihre Edge-Server-Topologie in Skype for Business Server planen können.
  
Wir haben einige Szenarien-Diagramme, die Ihnen bei der Visualisierung und der Entscheidung helfen, welche Skype for Business Server-Edgeserver-Topologie Sie implementieren möchten. Sobald Sie einen geeigneten Kandidaten ausgewählt haben, können Sie sich über die Umgebungsanforderungen informieren, die Sie erfüllen müssen. Da das Folgende auf alle Szenarien zutrifft, erwähnen wir es zuerst.
  
Diese Abbildungen, die nur zu Beispielzwecken verwendet werden (und als solche Beispiel-IPv4- und Beispiel-IPv6-Daten enthalten), stellen nicht den tatsächlichen Kommunikationsfluss dar, sondern eher eine allgemeine Darstellung Ihres möglichen Datenverkehrs. Portdetails können auch in den untenstehenden Portdiagrammen für jedes Szenario gefunden werden.
  
In den Diagrammen wird .com für die externe Schnittstelle und .net für die interne angezeigt, welche auch Beispielmaterial ist; natürlich können Ihre eigenen Einträge vollkommen anders sein, wenn Sie Ihren eigenen endgültigen Edgeplan zusammenstellen.
  
Der Director (eine optionale Komponente) ist in keinem der Diagramme enthalten, aber Sie können darüber separat lesen (er wird in anderen Planungsthemen erwähnt).
  
Wie bereits erwähnt, sind Beispiel-IPv6-Daten im Diagramm enthalten. Die meisten Dokumentationen in [Plan für Edge-Server-Bereitstellungen in Skype for Business Server](edge-server-deployments.md) beziehen sich auf IPv4, aber Sie werden sicherlich unterstützt, wenn Sie IPv6 verwenden möchten. Beachten Sie, dass Sie IPv6-Adressen in Ihrem zugewiesenen Adressraum benötigen und dass diese wie mit IPv4-IPs mit interner und externer Adressierung funktionieren müssen. Dank Windows können Sie die Dualstapelfunktion verwenden, die ein separater und unabhängiger Netzwerkstapel für IPv4 und IPv6 ist. Dadurch können Sie bei Bedarf gleichzeitig IPv4- und IPv6-Adressen zuweisen.
  
Es gibt NAT-Geräte, die NAT64 (IPv6 to IPv4) und NAT66 (IPv6 to IPv6)) ermöglichen, und dies gilt für die Verwendung mit Skype for Business Server.
  
> [!IMPORTANT]
> Wenn Sie Anrufsteuerung (CAC) verwenden, müssen Sie IPv4 auf der internen Schnittstelle verwenden, damit diese funktionieren kann. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Einzelner konsolidierter Skype for Business-Server-Edgeserver mit privaten IP-Adressen und NAT

Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.
  
![Edge-Szenario für einzelnen konsolidierten Edge mit privater IP-Adresse mithilfe von NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerk Perimeter für Edge-Szenario, einzelner konsolidierter Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Einzelner konsolidierter Skype for Business-Server-Edgeserver mit öffentlichen IP-Adressen

Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.
  
![Edge-Szenario für einzelnen konsolidierten Edge mit öffentlicher IP-Adresse](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerk Perimeter für Edge-Szenario, einzelner konsolidierter Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skalierter konsolidierter Skype for Business Server-Edge-Pool mit DNS-Lastenausgleich und privaten IP-Adressen und NAT

Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.
  
![Edge-Szenario für skalierten konsolidierten Edge, DNS lb mit privater IP-Adresse mithilfe von NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir verfügen auch über ein Diagramm für skalierte konsolidierte Edge-Pools mit DNS-Lastenausgleich.
  
![Netzwerk Perimeter für Edge-Szenario, skalierte konsolidierte Kante mithilfe von DNS lb](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Skalierter konsolidierter Skype for Business Server-Edge-Pool mit DNS-Lastenausgleich und öffentlichen IP-Adressen

Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.
  
![Edge-Szenario für skalierten konsolidierten Edge, DNS lb mit öffentlicher IP-Adresse](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir verfügen auch über ein Diagramm für skalierte konsolidierte Edge-Pools mit DNS-Lastenausgleich.
  
![Netzwerk Perimeter für Edge-Szenario, skalierte konsolidierte Kante mithilfe von DNS lb](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Skalierter konsolidierter Skype for Business Server-Edge-Pool mit Hardwarelastenausgleich

Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.
  
![Edge-Szenario für skalierten konsolidierten Edge mit HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für skalierte konsolidierte Edge-Pools mit Hardwarelastenausgleich
  
![Edge-Server-Umkreisnetzwerk-Ports und-Protokolle](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

