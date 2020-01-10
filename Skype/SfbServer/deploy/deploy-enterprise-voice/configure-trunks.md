---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen trunk zwischen einem Vermittlungs Server und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 9bd285f1364d54940afd827858248656a6bb9f00
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001235"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="01b6d-103">Konfigurieren von Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="01b6d-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="01b6d-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen trunk zwischen einem Vermittlungs Server und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01b6d-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="01b6d-105">Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="01b6d-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="01b6d-106">SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="01b6d-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="01b6d-107">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="01b6d-107">PSTN gateway</span></span>
    
- <span data-ttu-id="01b6d-108">Nebenstellenanlage (Private Branch Exchange, PBX)</span><span class="sxs-lookup"><span data-stu-id="01b6d-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="01b6d-109">Weitere Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="01b6d-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="01b6d-110">Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="01b6d-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="01b6d-111">Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt.</span><span class="sxs-lookup"><span data-stu-id="01b6d-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="01b6d-112">Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="01b6d-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="01b6d-113">Um einen trunk in Skype for Business Server zuzuweisen oder zu entfernen, müssen Sie zuerst einen trunk in Topology Builder definieren.</span><span class="sxs-lookup"><span data-stu-id="01b6d-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="01b6d-114">Ein trunk besteht aus der folgenden Zuordnung: vollständig qualifizierter Domänenname (Fully Qualified Domain Name, FQDN), Mediation Server-Abhör Port, Gateway-FQDN und Gateway-Abhör Port.</span><span class="sxs-lookup"><span data-stu-id="01b6d-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="01b6d-115">Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungs Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="01b6d-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="01b6d-116">Dies bietet zusätzliche Widerstandsfähigkeit für die Enterprise-VoIP-Infrastruktur, die besonders in interoperational-Szenarien (Private Branch Exchange) verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="01b6d-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="01b6d-117">Beim Definieren eines Trunks muss er einer Route zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="01b6d-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="01b6d-118">Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="01b6d-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="01b6d-119">Dieser einfache Name wird als trunk-Name in der Skype for Business Server-Systemsteuerung verwendet, in der Trunks mit Routen verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="01b6d-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="01b6d-120">Der einfache trunk-Name wird als Gateway-Name aus der Skype for Business Server-Verwaltungsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="01b6d-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="01b6d-121">Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungs Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="01b6d-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="01b6d-122">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugehörigen Vermittlungs Server, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="01b6d-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="01b6d-123">Geben Sie das Standardgateway für den Vermittlungs Server an.</span><span class="sxs-lookup"><span data-stu-id="01b6d-123">Specify the default gateway for the Mediation Server.</span></span> 
  

