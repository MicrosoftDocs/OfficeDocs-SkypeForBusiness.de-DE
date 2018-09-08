---
title: Konfigurieren von Trunks in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Erfahren Sie, wie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype für Business Server zu konfigurieren.'
ms.openlocfilehash: 02ace749e62b7e6edd3f514fa81b55eb30c87094
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887976"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="68338-103">Konfigurieren von Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="68338-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="68338-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype für Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68338-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="68338-105">Im Rahmen der Bereitstellung von Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und mindestens eine der folgenden Peers zum öffentlichen Telefonnetz (PSTN) Netzwerkkonnektivität für Enterprise-VoIP-Clients und Geräte in Ihrer Organisation bereitstellen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="68338-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="68338-106">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="68338-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="68338-107">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="68338-107">PSTN gateway</span></span>
    
- <span data-ttu-id="68338-108">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="68338-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="68338-109">Weitere Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="68338-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="68338-110">Skype-Funktionen, Business Server unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="68338-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="68338-111">Diese Zuordnungen werden geändert, indem ein Trunk eine logische Zuordnung zwischen einem vermittlungsserverpool und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN), Session Border Controller (SBC) oder IP-PBX ist zu definieren.</span><span class="sxs-lookup"><span data-stu-id="68338-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="68338-112">Verwenden Sie den Topologie-Generator Vermittlungsserver (d. h., Trunks) Gateways zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68338-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="68338-113">Zum Zuweisen oder Entfernen eines Trunks in Skype für Business Server, müssen Sie zuerst einen Trunk im Topologie-Generator definieren.</span><span class="sxs-lookup"><span data-stu-id="68338-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="68338-114">Ein Trunk umfasst die folgenden Zuordnung: Vermittlungsserver vollqualifizierter Domänenname (FQDN), den Vermittlungsserver Überwachungsport, FQDN des Gateways und den Überwachungsport des Gateways.</span><span class="sxs-lookup"><span data-stu-id="68338-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="68338-115">Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungsserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="68338-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="68338-116">Dadurch wird die zusätzliche Flexibilität mit der Enterprise-VoIP-Infrastruktur in private Branch Exchange, (Nebenstellenanlage PBX) interoperational Szenarien besonders nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="68338-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="68338-117">Beim Definieren eines Trunks muss er einer Route zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="68338-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="68338-118">Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für die Trunks im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="68338-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="68338-119">Diese einfache Name wird als den trunknamen in der Skype Business Server-Systemsteuerung verwendet, in dem Trunks Routen zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="68338-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="68338-120">Der einfachen trunknamen dient als Gateway-Namen aus der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="68338-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="68338-121">Der Administrator muss einen Standard-Trunk zugeordnet eines Vermittlungsservers auswählen.</span><span class="sxs-lookup"><span data-stu-id="68338-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="68338-122">Topologie-Generator mit der rechten Maustaste zugeordneter Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="68338-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="68338-123">Geben Sie den Standard-Gateway für den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="68338-123">Specify the default gateway for the Mediation Server.</span></span> 
  

