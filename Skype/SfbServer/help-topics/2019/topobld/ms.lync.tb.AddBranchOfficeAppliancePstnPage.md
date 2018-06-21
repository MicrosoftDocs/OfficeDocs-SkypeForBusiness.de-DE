---
title: Hinzufügen eines Survivable Branch-Anwendungs-PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Um das Gateway public switched Telephone Network, (PSTN) für eine Survivable Branch Appliance am Zweigstellenstandort definieren, geben Sie Folgendes ein:'
ms.openlocfilehash: 7357beacc93e9fbfede068802c5e849416096a0e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19996884"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="181f5-103">Hinzufügen eines Survivable Branch-Anwendungs-PSTN</span><span class="sxs-lookup"><span data-stu-id="181f5-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="181f5-104">Um das Gateway public switched Telephone Network, (PSTN) für eine Survivable Branch Appliance am Zweigstellenstandort definieren, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="181f5-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="181f5-105">PSTN-Anrufe einen vollqualifizierten Domänennamen (FQDN) oder die IP-Adresse für den gatewaypeer, dass die Survivable Branch Appliance oder einen Survivable Branch Server für das routing von eingehenden und ausgehenden zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="181f5-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="181f5-106">Wenn Sie eine Survivable Branch Appliance definieren, ist dies das Gateway, mit dem der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Anbindung verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="181f5-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="181f5-p101">Der Überwachungsport für SIP-Nachrichten (Session Initiation Protocol). Die Standardports für ein Gateway, eine Nebenstellenanlage oder einen SBC (Session Border Controller) lauten 5066 für Transmission Control Protocol (TCP) und 5067 für TLS (Transport Layer Security). Bei einer Survivable Branch-Anwendung an einer Zweigstelle lauten die Standardports 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="181f5-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="181f5-110">Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen.</span><span class="sxs-lookup"><span data-stu-id="181f5-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="181f5-111">Wenn Sie eine Survivable Branch Appliance definieren, finden Sie in der Herstellerdokumentation Survivable Branch Appliance, um sicherzustellen, dass Ihre Survivable Branch Appliance das TLS-Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="181f5-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="181f5-112">Aus Sicherheitsgründen wird dringend empfohlen, ein Gateway mit Unterstützung für TLS bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="181f5-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="181f5-113">Wenn Sie ein PSTN-Gateway hinzufügen möchten, können Sie dieses zu einem späteren Zeitpunkt einrichten. Die Funktionalität ist jedoch eingeschränkt, bis das PSTN-Gateway definiert und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="181f5-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

