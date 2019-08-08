---
title: Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer im Topologie-Generator in Skype for Business Server definieren.'
ms.openlocfilehash: eeaddf6b5b150298e7a77b819464b3c0ef653b70
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245610"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="154b0-103">Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="154b0-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="154b0-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer im Topologie-Generator in Skype for Business Server definieren.</span><span class="sxs-lookup"><span data-stu-id="154b0-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="154b0-105">Führen Sie die folgenden Schritte aus, um einen zusätzlichen trunk zu definieren, dem Sie einen Peer einem Vermittlungs Server zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="154b0-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="154b0-106">Ein Peer bietet Benutzern, die für Enterprise-VoIP aktiviert sind, Verbindungen mit dem öffentlich geschalteten Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="154b0-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="154b0-107">Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.</span><span class="sxs-lookup"><span data-stu-id="154b0-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="154b0-108">Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem Gateway.</span><span class="sxs-lookup"><span data-stu-id="154b0-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="154b0-109">In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm Stamm mit mindestens einem zusammengefassten oder eigenständigen Vermittlungs Server oder-Pool eingerichtet haben, wie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server](define-a-gateway.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="154b0-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="154b0-110">So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer</span><span class="sxs-lookup"><span data-stu-id="154b0-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="154b0-111">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="154b0-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="154b0-112">Klicken Sie unter Skype for Business Server, Name Ihrer Website, **freigegebene Komponenten**, mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.</span><span class="sxs-lookup"><span data-stu-id="154b0-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="154b0-113">Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="154b0-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="154b0-114">Zwei Trunks mit demselben Namen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="154b0-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="154b0-115">Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben.</span><span class="sxs-lookup"><span data-stu-id="154b0-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="154b0-116">Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="154b0-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="154b0-117">Geben Sie unter **Abhör-Port für PSTN-Gateway**den Abhör-Port ein, mit dem der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten vom Vermittlungs Server empfängt, der diesem trunk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="154b0-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="154b0-118">Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="154b0-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="154b0-119">Die Standardanschlüsse für Survivable Branch-Appliances sind 5081 für TCP und 5082 für TLS.</span><span class="sxs-lookup"><span data-stu-id="154b0-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="154b0-120">Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="154b0-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="154b0-121">Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="154b0-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="154b0-122">Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses Peers zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="154b0-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="154b0-123">Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör-Port ein, auf dem der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.</span><span class="sxs-lookup"><span data-stu-id="154b0-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="154b0-124">Mit mehreren trunk-Unterstützung in Skype for Business Server können zwei Trunks mit unterschiedlichen trunk-Namen nicht mit dem gleichen **zugehörigen Vermittlungs Server-Port** und **Abhör-Port für IP/PSTN-Gateway** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="154b0-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="154b0-125">Mit mehreren trunk-Unterstützung in Skype for Business Server können mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden.</span><span class="sxs-lookup"><span data-stu-id="154b0-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="154b0-126">Wenn Sie einen trunk definieren, muss sich die **zugeordnete Vermittlungsserver-Port** Nummer innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden.</span><span class="sxs-lookup"><span data-stu-id="154b0-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="154b0-127">Dieser Portbereich wird unter Skype for Business Server-und Mediation Server-Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="154b0-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="154b0-128">Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungs Server Pool, und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="154b0-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="154b0-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="154b0-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="154b0-130">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="154b0-130">Click **OK**.</span></span> 
    

