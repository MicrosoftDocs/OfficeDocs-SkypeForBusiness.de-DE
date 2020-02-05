---
title: Definieren eines Gateways im Topologie-Generator in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.'
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767728"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="1014d-103">Definieren eines Gateways im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1014d-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="1014d-104">**Zusammenfassung:** Erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.</span><span class="sxs-lookup"><span data-stu-id="1014d-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="1014d-105">Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen Peer zu definieren, dem Sie einen Vermittlungs Server zuordnen können, um Verbindungen mit dem öffentlichen Telefonnetz (PSTN) für Benutzer bereitzustellen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1014d-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="1014d-106">Ein Peer-to-Mediation-Server kann ein PSTN-Gateway, eine IP-Telefonanlage oder ein Session Border Controller (SBC) für einen Internet-Telefoniedienstanbieter (ITSP) sein, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1014d-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="1014d-107">So definieren Sie einen Peer für den Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="1014d-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="1014d-108">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="1014d-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1014d-109">Klicken Sie unter Skype for Business Server, ihren Websitenamen, freigegebene Komponenten, mit der rechten Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="1014d-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="1014d-110">Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1014d-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1014d-111">Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben.</span><span class="sxs-lookup"><span data-stu-id="1014d-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="1014d-112">Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateways und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1014d-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="1014d-113">Definieren Sie einen Stammtrunk für das PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="1014d-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="1014d-114">Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem vom Tupel eindeutig identifizierten Gateway.</span><span class="sxs-lookup"><span data-stu-id="1014d-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="1014d-115">{Vermittlungsserver-FQDN, Abhör Port für Mediationsserver (TLS oder TCP): Gateway-IP und-FQDN, Gateway-Überwachungs Port}</span><span class="sxs-lookup"><span data-stu-id="1014d-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="1014d-116">Wenn Sie ein PSTN-Gateway im Topologie-Generator definieren, müssen Sie einen Stamm Stamm definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1014d-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="1014d-117">Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="1014d-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="1014d-118">Geben Sie unter **Abhör Port für IP/PSTN-Gateway**den Abhöranschluss ein, den das Gateway, die Telefonanlage oder SBC für SIP-Nachrichten vom Vermittlungs Server verwenden, die dem Stammverzeichnis des PSTN-Gateways zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1014d-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="1014d-119">(In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1014d-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="1014d-120">Bei einer Survivable Branch-Appliance an einer Zweigstelle sind die Standardanschlüsse 5081 für TCP und 5082 für TLS.)</span><span class="sxs-lookup"><span data-stu-id="1014d-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="1014d-121">Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1014d-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1014d-122">Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="1014d-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="1014d-123">Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses PSTN-Gateways zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1014d-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="1014d-124">Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör Port ein, der vom Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1014d-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1014d-125">Mit mehreren trunk-Unterstützung in Skype for Business Server können Sie mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren.</span><span class="sxs-lookup"><span data-stu-id="1014d-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="1014d-126">Wenn Sie einen trunk definieren, muss sich der **zugeordnete Vermittlungsserver-Port** innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden.</span><span class="sxs-lookup"><span data-stu-id="1014d-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="1014d-127">Dieser Portbereich wird unter Skype for Business Server und Mediation Pools definiert.</span><span class="sxs-lookup"><span data-stu-id="1014d-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="1014d-128">Klicken Sie mit der rechten Maustaste auf den Interessenbereich des Mediation Server-Pools, und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1014d-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="1014d-129">Geben Sie den Portbereich im Feld **Abhör-Ports** an.</span><span class="sxs-lookup"><span data-stu-id="1014d-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="1014d-130">Stellen Sie sicher, dass der Peer, den Sie definiert haben, ausgeführt wird und den angegebenen FQDN oder die angegebene IP-Adresse verwendet.</span><span class="sxs-lookup"><span data-stu-id="1014d-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="1014d-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1014d-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="1014d-132">Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server** und dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="1014d-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

