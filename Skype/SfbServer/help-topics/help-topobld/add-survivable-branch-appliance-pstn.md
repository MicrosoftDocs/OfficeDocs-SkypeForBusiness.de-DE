---
title: Hinzufügen eines Survivable Branch Appliance-PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Zum Definieren des PSTN-Gateways (Public Switched Telephone Network) für eine Survivable Branch Appliance am Zweigstellenstandort muss Folgendes angegeben werden:'
ms.openlocfilehash: 477aa014d6b4450dae3422e6893e7f7f0a48c703
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217076"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="cb9bb-103">Hinzufügen eines Survivable Branch Appliance-PSTN</span><span class="sxs-lookup"><span data-stu-id="cb9bb-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="cb9bb-104">Zum Definieren des PSTN-Gateways (Public Switched Telephone Network) für eine Survivable Branch Appliance am Zweigstellenstandort muss Folgendes angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="cb9bb-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="cb9bb-105">Ein vollqualifizierter Domänenname (FQDN) oder eine IP-Adresse des Gatewaypeers, dem die Survivable Branch Appliance oder der Survivable Branch Server für das Routing ein- und ausgehender PSTN-Anrufe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cb9bb-106">Beim Definieren einer Survivable Branch Appliance ist dies das Gateway, mit dem sich der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Verbindungen verbindet.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="cb9bb-p101">Der Überwachungsport für SIP-Nachrichten (Session Initiation Protocol). Die Standardports für ein Gateway, eine Nebenstellenanlage oder einen SBC (Session Border Controller) lauten 5066 für Transmission Control Protocol (TCP) und 5067 für TLS (Transport Layer Security). Bei einer Survivable Branch Appliance an einem Zweigstellenstandort lauten die Standardports 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="cb9bb-p102">Aus Sicherheitsgründen wird der Einsatz von TLS ausdrücklich empfohlen. Konsultieren Sie beim Definieren einer Survivable Branch Appliance die Dokumentation des Herstellers, um sicherzustellen, dass die Survivable Branch Appliance das TLS-Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cb9bb-112">Aus Sicherheitsgründen wird dringend empfohlen, ein Gateway mit Unterstützung für TLS bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb9bb-113">Wenn Sie ein PSTN-Gateway hinzufügen möchten, können Sie dieses zu einem späteren Zeitpunkt einrichten. Die Funktionalität ist jedoch eingeschränkt, bis das PSTN-Gateway definiert und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cb9bb-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

