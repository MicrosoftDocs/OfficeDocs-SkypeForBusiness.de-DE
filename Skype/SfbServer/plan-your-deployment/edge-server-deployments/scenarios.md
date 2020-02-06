---
title: Edge-Server-Szenarien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Überprüfen Sie diese Szenarien, damit Sie Ihre Edge-Server-Topologie in Skype for Business Server planen können.'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803355"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="b820c-103">Edge-Server-Szenarien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b820c-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="b820c-104">**Zusammenfassung:** Überprüfen Sie diese Szenarien, damit Sie Ihre Edge-Server-Topologie in Skype for Business Server planen können.</span><span class="sxs-lookup"><span data-stu-id="b820c-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="b820c-105">Wir haben einige Szenarien-Diagramme, die Ihnen bei der Visualisierung und der Entscheidung helfen, welche Skype for Business Server-Edgeserver-Topologie Sie implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b820c-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="b820c-106">Sobald Sie einen geeigneten Kandidaten ausgewählt haben, können Sie sich über die Umgebungsanforderungen informieren, die Sie erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="b820c-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="b820c-107">Da das Folgende auf alle Szenarien zutrifft, erwähnen wir es zuerst.</span><span class="sxs-lookup"><span data-stu-id="b820c-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="b820c-p102">Diese Abbildungen, die nur zu Beispielzwecken verwendet werden (und als solche Beispiel-IPv4- und Beispiel-IPv6-Daten enthalten), stellen nicht den tatsächlichen Kommunikationsfluss dar, sondern eher eine allgemeine Darstellung Ihres möglichen Datenverkehrs. Portdetails können auch in den untenstehenden Portdiagrammen für jedes Szenario gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b820c-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="b820c-110">In den Diagrammen wird .com für die externe Schnittstelle und .net für die interne angezeigt, welche auch Beispielmaterial ist; natürlich können Ihre eigenen Einträge vollkommen anders sein, wenn Sie Ihren eigenen endgültigen Edgeplan zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="b820c-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="b820c-111">Der Director (eine optionale Komponente) ist in keinem der Diagramme enthalten, aber Sie können darüber separat lesen (er wird in anderen Planungsthemen erwähnt).</span><span class="sxs-lookup"><span data-stu-id="b820c-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="b820c-112">Wie bereits erwähnt, sind Beispiel-IPv6-Daten im Diagramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="b820c-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="b820c-113">Die meisten Dokumentationen in [Plan für Edge-Server-Bereitstellungen in Skype for Business Server](edge-server-deployments.md) beziehen sich auf IPv4, aber Sie werden sicherlich unterstützt, wenn Sie IPv6 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b820c-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="b820c-114">Beachten Sie, dass Sie IPv6-Adressen in Ihrem zugewiesenen Adressraum benötigen und dass diese wie mit IPv4-IPs mit interner und externer Adressierung funktionieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b820c-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="b820c-115">Dank Windows können Sie die Dualstapelfunktion verwenden, die ein separater und unabhängiger Netzwerkstapel für IPv4 und IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="b820c-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="b820c-116">Dadurch können Sie bei Bedarf gleichzeitig IPv4- und IPv6-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b820c-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="b820c-117">Es gibt NAT-Geräte, die NAT64 (IPv6 to IPv4) und NAT66 (IPv6 to IPv6)) ermöglichen, und dies gilt für die Verwendung mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b820c-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b820c-118">Wenn Sie Anrufsteuerung (CAC) verwenden, müssen Sie IPv4 auf der internen Schnittstelle verwenden, damit diese funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="b820c-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="b820c-119">Einzelner konsolidierter Skype for Business-Server-Edgeserver mit privaten IP-Adressen und NAT</span><span class="sxs-lookup"><span data-stu-id="b820c-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="b820c-p104">Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="b820c-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Edge-Szenario für einzelnen konsolidierten Edge mit privater IP-Adresse mithilfe von NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b820c-124">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="b820c-124">Port diagram</span></span>

<span data-ttu-id="b820c-125">Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="b820c-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Netzwerk Perimeter für Edge-Szenario, einzelner konsolidierter Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="b820c-127">Einzelner konsolidierter Skype for Business-Server-Edgeserver mit öffentlichen IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="b820c-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="b820c-p105">Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="b820c-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Edge-Szenario für einzelnen konsolidierten Edge mit öffentlicher IP-Adresse](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b820c-132">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="b820c-132">Port diagram</span></span>

<span data-ttu-id="b820c-133">Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="b820c-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Netzwerk Perimeter für Edge-Szenario, einzelner konsolidierter Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="b820c-135">Skalierter konsolidierter Skype for Business Server-Edge-Pool mit DNS-Lastenausgleich und privaten IP-Adressen und NAT</span><span class="sxs-lookup"><span data-stu-id="b820c-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="b820c-136">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="b820c-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edge-Szenario für skalierten konsolidierten Edge, DNS lb mit privater IP-Adresse mithilfe von NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b820c-138">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="b820c-138">Port diagram</span></span>

<span data-ttu-id="b820c-139">Wir verfügen auch über ein Diagramm für skalierte konsolidierte Edge-Pools mit DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="b820c-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Netzwerk Perimeter für Edge-Szenario, skalierte konsolidierte Kante mithilfe von DNS lb](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="b820c-141">Skalierter konsolidierter Skype for Business Server-Edge-Pool mit DNS-Lastenausgleich und öffentlichen IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="b820c-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="b820c-142">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="b820c-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edge-Szenario für skalierten konsolidierten Edge, DNS lb mit öffentlicher IP-Adresse](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b820c-144">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="b820c-144">Port diagram</span></span>

<span data-ttu-id="b820c-145">Wir verfügen auch über ein Diagramm für skalierte konsolidierte Edge-Pools mit DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="b820c-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Netzwerk Perimeter für Edge-Szenario, skalierte konsolidierte Kante mithilfe von DNS lb](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="b820c-147">Skalierter konsolidierter Skype for Business Server-Edge-Pool mit Hardwarelastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b820c-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="b820c-148">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="b820c-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edge-Szenario für skalierten konsolidierten Edge mit HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
