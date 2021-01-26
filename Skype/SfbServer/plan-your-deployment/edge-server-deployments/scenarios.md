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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Zusammenfassung: Überprüfen Sie diese Szenarien, um Ihre Edgeservertopologie in Skype for Business Server zu planen.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813791"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Edgeserverszenarien in Skype for Business Server
 
**Zusammenfassung:** Überprüfen Sie diese Szenarien, um Ihre Edgeservertopologie in Skype for Business Server zu planen.
  
Wir haben einige Szenariendiagramme, die Sie bei der Visualisierung und Entscheidung für die Skype for Business Server Edge Server-Topologie unterstützen, die Sie implementieren möchten. Nachdem Sie einen guten Kandidaten ausgewählt haben, können Sie die Anforderungen an die Umgebung lesen, die Sie erfüllen müssen. Das Folgende gilt für jedes der Szenarien, daher erwähnen wir es zuerst.
  
Diese Abbildungen, die nur zu Beispielzwecken dargestellt werden (und als solche IPv4- und IPv6-Beispieldaten enthalten), stellen nicht den tatsächlichen Kommunikationsfluss dar, sondern eine hochrangige Ansicht des möglichen Datenverkehrs. Portdetails sind auch in den Portdiagrammen für jedes szenario unten zu sehen.
  
Die Diagramme zeigen .com für die externe Schnittstelle und .net für die interne, die auch Beispielmaterial ist; Ihre eigenen Einträge können natürlich ganz anders sein, wenn Sie Ihren eigenen endgültigen Edgeplan zusammenbringen.
  
Der Director (bei dem es sich um eine optionale Komponente handelt) wird in keines der Diagramme verwendet, sie können dies jedoch separat lesen (er wird in anderen Planungsthemen erwähnt).
  
Wie oben erwähnt, sind in den Diagrammen Beispiel-IPv6-Daten enthalten. Der Großteil der Dokumentation in "Planen von Edgeserverbereitstellungen [in Skype for Business Server"](edge-server-deployments.md) bezieht sich auf IPv4, sie werden jedoch mit Sicherheit unterstützt, wenn Sie IPv6 verwenden möchten. Beachten Sie, dass Sie in Ihrem zugewiesenen Adressraum IPv6-Adressen benötigen und wie bei IPv4-IPs mit interner und externer Adressierung arbeiten müssen. Dank Windows können Sie das Dualstapelfeature verwenden, bei dem es sich um einen separaten und unterschiedlichen Netzwerkstapel für IPv4 und IPv6 handelt. Auf diese Weise können Sie bei Bedarf IPv4- und IPv6-Adressen gleichzeitig zuweisen.
  
Es gibt NAT-Geräte, die NAT64 (IPv6 zu IPv4) und NAT66 (IPv6 zu IPv6)) zulassen, und dies gilt für die Verwendung mit Skype for Business Server.
  
> [!IMPORTANT]
> Wenn Sie die Anrufsteuerung verwenden, müssen Sie IPv4 auf der internen Schnittstelle verwenden, damit es funktioniert. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Einzelner konsolidierter Skype for Business Server-Edgeserver mit privaten IP-Adressen und NAT

In diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Dies bedeutet, dass Sie weniger für Hardware ausgeben und eine einfachere Bereitstellung haben. Wenn hohe Verfügbarkeit ein Muss ist, sehen Sie sich die folgenden skalierten konsolidierten Szenarien an.
  
![Edgeszenario für einen einzelnen konsolidierten Edge edge with Private IP using NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerkperimeter für Edgeszenario mit einem einzelnen konsolidierten Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Einzelner konsolidierter Skype for Business Server-Edgeserver mit öffentlichen IP-Adressen

In diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Dies bedeutet, dass Sie weniger für Hardware ausgeben und eine einfachere Bereitstellung haben. Wenn hohe Verfügbarkeit ein Muss ist, sehen Sie sich die folgenden skalierten konsolidierten Szenarien an.
  
![Edgeszenario für einen einzelnen konsolidierten Edge edge mit öffentlicher IP](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.
  
![Netzwerkperimeter für Edgeszenario mit einem einzelnen konsolidierten Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skalierter konsolidierter Skype for Business Server-Edgepool mit DNS-Lastenausgleich, privaten IP-Adressen und NAT

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, wodurch Sie die Vorteile der Skalierbarkeit und der Failoverunterstützung nutzen können.
  
![Edgeszenario für skalierten konsolidierten Edge, DNS-LB mit privater IP unter Verwendung von NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Es gibt auch ein Diagramm für skalierte konsolidierte Edgepools mit DNS-Lastenausgleich.
  
![Netzwerkperimeter für Edgeszenario skalierter konsolidierter Edge mit DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Skalierter konsolidierter Skype for Business Server-Edgepool mit DNS-Lastenausgleich und öffentlichen IP-Adressen

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, wodurch Sie die Vorteile der Skalierbarkeit und der Failoverunterstützung nutzen können.
  
![Edgeszenario für skalierten konsolidierten Edge, DNS-LB mit öffentlicher IP](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Portdiagramm

Es gibt auch ein Diagramm für skalierte konsolidierte Edgepools mit DNS-Lastenausgleich.
  
![Netzwerkperimeter für Edgeszenario skalierter konsolidierter Edge mit DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Skalierter konsolidierter Skype for Business Server-Edgepool mit Hardwarelastenausgleich

In diesem Szenario können Sie eine hohe Verfügbarkeit in Ihrer Edgebereitstellung haben, wodurch Sie die Vorteile der Skalierbarkeit und der Failoverunterstützung nutzen können.
  
![Edgeszenario für skalierten konsolidierten Edge mit HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
