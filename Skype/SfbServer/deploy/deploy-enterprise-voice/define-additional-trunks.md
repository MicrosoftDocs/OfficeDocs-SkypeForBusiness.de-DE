---
title: Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server
ms.reviewer: ''
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server definieren.'
ms.openlocfilehash: 874d32053f4c3d91f16818bd34dc11806de8692c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881960"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="9c083-103">Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="9c083-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="9c083-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server definieren.</span><span class="sxs-lookup"><span data-stu-id="9c083-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="9c083-105">Befolgen Sie diese Schritte, um einen zusätzlichen Trunk definieren, den einen Peer einen Vermittlungsserver zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="9c083-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="9c083-106">Ein Peer bietet Benutzern, die mit der Konnektivität zu im Public Switched Telephone Network, (PSTN) für Enterprise Voice aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c083-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9c083-107">Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.</span><span class="sxs-lookup"><span data-stu-id="9c083-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="9c083-108">Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway.</span><span class="sxs-lookup"><span data-stu-id="9c083-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c083-109">In diesem Thema wird davon ausgegangen, dass Sie Setup ein PSTN-Gateway und stammtrunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder-Pool verfügen, wie in der Dokumentation zur Bereitstellung definieren [eines Gateways im Topologie-Generator in Skype für Business Server](define-a-gateway.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c083-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="9c083-110">So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer</span><span class="sxs-lookup"><span data-stu-id="9c083-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="9c083-111">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="9c083-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="9c083-112">Klicken Sie unter Skype für Business Server, Ihr Sitename, **Freigegebene Komponenten**, mit der rechten Maustaste in des Knotens **Trunks** , und klicken Sie dann auf **Neuer Trunk**.</span><span class="sxs-lookup"><span data-stu-id="9c083-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="9c083-113">Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9c083-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="9c083-114">Zwei Trunks mit demselben Namen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9c083-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="9c083-115">Wenn Sie Transport Layer Security (TLS) als Transportprotokoll angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers für den Vermittlungsserver angeben.</span><span class="sxs-lookup"><span data-stu-id="9c083-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="9c083-116">Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c083-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="9c083-117">Geben Sie unter **Überwachungsport für PSTN-Gateway**, den Überwachungsport ein, dass der Peer (PSTN-Gateways, IP-Nebenstellenanlage oder SBC) vom Vermittlungsserver SIP-Nachrichten erhalten, die mit diesem Trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c083-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="9c083-118">Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9c083-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="9c083-119">Die Survivable Branch Appliance Standardports sind 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="9c083-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="9c083-120">Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="9c083-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9c083-121">Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9c083-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="9c083-122">Wählen Sie unter **Zugeordneter Vermittlungsserver**zu dem stammtrunk dieses Peers zugeordnet Pools für den Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="9c083-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="9c083-123">Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungsport, dass der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.</span><span class="sxs-lookup"><span data-stu-id="9c083-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9c083-124">Zwei Trunks mit unterschiedlichen trunknamen können nicht mit Unterstützung mehrerer Trunks in Skype für Business Server mit dem gleichen **zugeordneter Vermittlungsserver Port** und **Überwachungsport für IP/PSTN-Gateway** konfiguriert werden</span><span class="sxs-lookup"><span data-stu-id="9c083-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="9c083-125">Mit Unterstützung mehrerer Trunks in Skype für Business Server kann mehrere SIP-Signalisierung Ports auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c083-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="9c083-126">Wenn Sie einen Trunk zu definieren, muss die Portnummer **Zugeordneter Vermittlungsserver** innerhalb des Bereichs von die Überwachungsports für das jeweilige Protokoll vom Vermittlungsserver zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="9c083-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="9c083-127">Dieser Portbereich ist unter Skype für Business Server und Vermittlungsserver Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="9c083-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="9c083-128">Mit der rechten Maustaste in des entsprechenden Vermittlungsserver Pools, und wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9c083-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="9c083-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="9c083-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="9c083-130">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c083-130">Click **OK**.</span></span> 
    

