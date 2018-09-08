---
title: Edge-Server-Szenarien in Skype für Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Zusammenfassung: Lesen Sie diese Szenarien, die Ihnen bei der Planung Ihrer Edge-Server-Topologie in Skype für Business Server erleichtern.'
ms.openlocfilehash: 6343c69c493992656b17aaadb5e1450baec85560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885180"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="41afb-103">Edge-Server-Szenarien in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="41afb-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="41afb-104">**Zusammenfassung:** Lesen Sie diese Szenarien, die Ihnen bei der Planung Ihrer Edge-Server-Topologie in Skype für Business Server erleichtern.</span><span class="sxs-lookup"><span data-stu-id="41afb-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="41afb-105">Wir haben einige Szenarien Diagramme zur Unterstützung beim visualisieren und entscheiden, auf welche Skype für Business Server Edge-Server-Topologie, die Sie implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="41afb-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="41afb-106">Sobald Sie einen geeigneten Kandidaten ausgewählt haben, können Sie sich über die Umgebungsanforderungen informieren, die Sie erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="41afb-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="41afb-107">Da das Folgende auf alle Szenarien zutrifft, erwähnen wir es zuerst.</span><span class="sxs-lookup"><span data-stu-id="41afb-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="41afb-p102">Diese Abbildungen, die nur zu Beispielzwecken verwendet werden (und als solche Beispiel-IPv4- und Beispiel-IPv6-Daten enthalten), stellen nicht den tatsächlichen Kommunikationsfluss dar, sondern eher eine allgemeine Darstellung Ihres möglichen Datenverkehrs. Portdetails können auch in den untenstehenden Portdiagrammen für jedes Szenario gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="41afb-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="41afb-110">In den Diagrammen wird .com für die externe Schnittstelle und .net für die interne angezeigt, welche auch Beispielmaterial ist; natürlich können Ihre eigenen Einträge vollkommen anders sein, wenn Sie Ihren eigenen endgültigen Edgeplan zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="41afb-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="41afb-111">Wir nicht mit den Director (bei dem es sich um eine optionale Komponente handelt) in den Diagrammen einschließen, aber Sie erhalten Informationen über, die separat (es wird in anderen Themen Planning erwähnten).</span><span class="sxs-lookup"><span data-stu-id="41afb-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="41afb-112">Wie bereits erwähnt, sind Beispiel-IPv6-Daten im Diagramm enthalten.</span><span class="sxs-lookup"><span data-stu-id="41afb-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="41afb-113">Ein Großteil der Dokumentation [Planen für Edge-Server-Bereitstellungen in Skype für Business Server](edge-server-deployments.md) IPv4 bezeichnen, aber Sie werden sicherlich unterstützt, wenn Sie IPv6 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41afb-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="41afb-114">Beachten Sie, dass Sie IPv6-Adressen in Ihrem zugewiesenen Adressraum benötigen und dass diese wie mit IPv4-IPs mit interner und externer Adressierung funktionieren müssen.</span><span class="sxs-lookup"><span data-stu-id="41afb-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="41afb-115">Dank Windows können Sie die Dualstapelfunktion verwenden, die ein separater und unabhängiger Netzwerkstapel für IPv4 und IPv6 ist.</span><span class="sxs-lookup"><span data-stu-id="41afb-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="41afb-116">Dadurch können Sie bei Bedarf gleichzeitig IPv4- und IPv6-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41afb-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="41afb-117">NAT-Geräte, die für NAT64 zulassen vorhanden sind (IPv6 IPv4) und NAT66 (IPv6 in IPv6)), und dies für die Verwendung mit Skype für Business Server gültig ist.</span><span class="sxs-lookup"><span data-stu-id="41afb-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="41afb-118">Wenn Sie Anrufsteuerung (CAC) verwenden, müssen Sie IPv4 auf der internen Schnittstelle verwenden, damit diese funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="41afb-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="41afb-119">Einzelner konsolidierter Skype für Business Server-Edgeserver mit privaten IP-Adressen und Netzwerkadressenübersetzung</span><span class="sxs-lookup"><span data-stu-id="41afb-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="41afb-p104">Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="41afb-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Edgeszenario für einzelnen konsolidierten Edgeserver mit privater IP bei Verwendung von NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="41afb-124">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="41afb-124">Port diagram</span></span>

<span data-ttu-id="41afb-125">Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="41afb-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Umkreisnetzwerk – Edgeszenario für einzelnen konsolidierten Edgeserver](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="41afb-127">Einzelner konsolidierter Skype für Business Server-Edgeserver mit öffentlichen IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="41afb-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="41afb-p105">Bei diesem Szenario gibt es keine Option für hohe Verfügbarkeit. Das bedeutet, dass Sie weniger für Hardware ausgeben und die Bereitstellung einfacher ist. Wenn hohe Verfügbarkeit für Sie ein Muss ist, informieren Sie sich unten über die skalierten konsolidierten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="41afb-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Edgeszenario für einzelnen konsolidierten Edgeserver mit öffentlicher IP](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="41afb-132">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="41afb-132">Port diagram</span></span>

<span data-ttu-id="41afb-133">Wir haben auch ein Diagramm für Ports für einzelne konsolidierte Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="41afb-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Umkreisnetzwerk – Edgeszenario für einzelnen konsolidierten Edgeserver](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="41afb-135">Skalierte konsolidierte Skype für Business Server Edge-Pool mit DNS laden, Lastenausgleich und privaten IP-Adressen und Netzwerkadressenübersetzung</span><span class="sxs-lookup"><span data-stu-id="41afb-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="41afb-136">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="41afb-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edgeszenario für skalierten konsolidierten Edgeserver, DNS-LB mit privater IP bei Verwendung von NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="41afb-138">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="41afb-138">Port diagram</span></span>

<span data-ttu-id="41afb-139">Wir haben auch ein Diagramm für einen skalierten konsolidierten Edge-Pools mit DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="41afb-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Umkreisnetzwerk – Edgeszenario für skalierten konsolidierten Edgeserver mithilfe von DNS-LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="41afb-141">Skalierte konsolidierte Skype für Business Server Edge-Pool mit DNS load Lastenausgleich und öffentliche IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="41afb-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="41afb-142">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="41afb-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edgeszenario für skalierten konsolidierten Edgeserver, DNS-LB mit öffentlicher IP](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="41afb-144">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="41afb-144">Port diagram</span></span>

<span data-ttu-id="41afb-145">Wir haben auch ein Diagramm für einen skalierten konsolidierten Edge-Pools mit DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="41afb-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Umkreisnetzwerk – Edgeszenario für skalierten konsolidierten Edgeserver mithilfe von DNS-LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="41afb-147">Eine skalierte konsolidierte Skype für Business Server Edge-Pool mit Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="41afb-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="41afb-148">Mit diesem Szenario können Sie über hohe Verfügbarkeit in Ihrer Edgebereitstellung verfügen, wodurch Sie die Vorteile von Skalierbarkeit und Failoverunterstützung genießen können.</span><span class="sxs-lookup"><span data-stu-id="41afb-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Edgeszenario für skalierten konsolidierten Edgeserver mit HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="41afb-150">Portdiagramm</span><span class="sxs-lookup"><span data-stu-id="41afb-150">Port diagram</span></span>

<span data-ttu-id="41afb-151">Wir haben auch ein Diagramm für skalierte konsolidierte Edge-Pools mit Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="41afb-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![Ports und Protokolle des Edgeserver-Umkreisnetzwerks](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

