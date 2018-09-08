---
title: Definieren eines Gateways im Topologie-Generator in Skype für Business Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Erfahren Sie, wie ein PSTN-Gateway im Topologie-Generator in Skype für Business Server definieren.'
ms.openlocfilehash: 50c5dca09608f6b0ef9046109e434f3ccbbba0d3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886796"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="f73fe-103">Definieren eines Gateways im Topologie-Generator in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="f73fe-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="f73fe-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype für Business Server definieren.</span><span class="sxs-lookup"><span data-stu-id="f73fe-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="f73fe-105">Befolgen Sie diese Schritte, um die Topologie-Generator verwenden, um einen Peer zu definieren, mit dem Sie einen Vermittlungsserver zum Bereitstellen der Verbindung mit dem öffentlichen Telefonfestnetz (PSTN) für Benutzer für Enterprise Voice aktiviert zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="f73fe-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="f73fe-106">Ein Peer für den Vermittlungsserver kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein Session Border Controller (SBC) für einen Internet Telefonie Service Provider (ITSP), die durch konfigurieren einen SIP-Trunk verbunden.</span><span class="sxs-lookup"><span data-stu-id="f73fe-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="f73fe-107">So definieren Sie einen Peer für den Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="f73fe-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="f73fe-108">Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="f73fe-109">Klicken Sie unter Skype für Business Server, Ihr Sitename, freigegebene Komponenten, Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="f73fe-110">Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f73fe-111">Wenn Sie Transport Layer Security (TLS) als Transportprotokoll angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers für den Vermittlungsserver angeben.</span><span class="sxs-lookup"><span data-stu-id="f73fe-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="f73fe-112">Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateways und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="f73fe-113">Definieren Sie einen Stammtrunk für das PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="f73fe-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="f73fe-114">Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway durch Folgendes Tupel eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f73fe-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="f73fe-115">{Mediation Server-FQDN, Vermittlungsserver Überwachungsport (TLS oder TCP): Gateway-IP und FQDN, gatewayüberwachungsport}</span><span class="sxs-lookup"><span data-stu-id="f73fe-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="f73fe-116">Wenn Sie ein PSTN-Gateway im Topologie-Generator zu definieren, müssen Sie einen stammtrunk, um das PSTN-Gateway zu einer Topologie erfolgreich hinzuzufügen definieren.</span><span class="sxs-lookup"><span data-stu-id="f73fe-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="f73fe-117">Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="f73fe-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="f73fe-118">Geben Sie unter **Überwachungsport für IP/PSTN-Gateway**den Überwachungsport, den das Gateway, der Nebenstellenanlage oder der SBC für SIP-Nachrichten vom Vermittlungsserver verwendet, der dem stammtrunk das PSTN-Gateway zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f73fe-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="f73fe-119">(In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f73fe-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="f73fe-120">Survivable Branch Appliance am Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)</span><span class="sxs-lookup"><span data-stu-id="f73fe-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="f73fe-121">Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f73fe-122">Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="f73fe-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="f73fe-123">Wählen Sie unter **Zugeordneter Vermittlungsserver**den vermittlungsserverpool, die dem stammtrunk dieses PSTN-Gateway zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f73fe-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="f73fe-124">Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungsport, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f73fe-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f73fe-125">Mit Unterstützung mehrerer Trunks in Skype für Business Server können Sie mehrere SIP-Signalisierung Ports auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren.</span><span class="sxs-lookup"><span data-stu-id="f73fe-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="f73fe-126">Wenn Sie einen Trunk zu definieren, muss der **zugeordneter Vermittlungsserver Port** innerhalb des Bereichs von die Überwachungsports für das jeweilige Protokoll vom Vermittlungsserver zulässig sein.</span><span class="sxs-lookup"><span data-stu-id="f73fe-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="f73fe-127">Dieser Portbereich ist unter Skype für Business Server und Vermittlungspools definiert.</span><span class="sxs-lookup"><span data-stu-id="f73fe-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="f73fe-128">Mit der rechten Maustaste vermittlungsserverpool von Interesse, und wählen Sie **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="f73fe-129">Geben Sie den Portbereich im Feld **Überwachungsports** ein.</span><span class="sxs-lookup"><span data-stu-id="f73fe-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="f73fe-p105">Stellen Sie sicher, dass der Peer, den Sie definiert haben, ausgeführt wird und den angegebenen FQDN oder die angegebene IP-Adresse verwendet. Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="f73fe-132">Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server** und dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="f73fe-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

