---
title: Komponenten für PSTN-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype for Business Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802535"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="d3e64-103">Komponenten für PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3e64-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="d3e64-104">Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d3e64-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d3e64-105">Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="d3e64-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="d3e64-106">Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3e64-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="d3e64-107">Aus Sicht des Benutzers sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN wie nur eine weitere SIP-Sitzung aussehen.</span><span class="sxs-lookup"><span data-stu-id="d3e64-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="d3e64-108">Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway bereitstellen – mit Nebenstellenanlage (was auch als direkte SIP-Verbindung bezeichnet wird) oder ohne Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="d3e64-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="d3e64-109">SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="d3e64-109">SIP Trunking</span></span>

<span data-ttu-id="d3e64-110">Als Alternative zur Verwendung von PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking mit dem PSTN verbinden.</span><span class="sxs-lookup"><span data-stu-id="d3e64-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="d3e64-111">Mit SIP-Trunking sind folgende Szenarien möglich:</span><span class="sxs-lookup"><span data-stu-id="d3e64-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="d3e64-112">Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3e64-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="d3e64-113">Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d3e64-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="d3e64-114">Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3e64-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="d3e64-115">PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="d3e64-115">PSTN gateways</span></span>

<span data-ttu-id="d3e64-116">PSTN-Gateways sind Geräte von Drittanbietern, die Signal-und Medienübertragung zwischen der Enterprise-VoIP-Infrastruktur und einem PSTN oder einer Telefonanlage übersetzen.</span><span class="sxs-lookup"><span data-stu-id="d3e64-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="d3e64-117">PSTN-Gateways arbeiten mit dem Vermittlungs Server zusammen, um einem Enterprise-VoIP-Client einen PSTN-oder PBX-Anruf zu präsentieren.</span><span class="sxs-lookup"><span data-stu-id="d3e64-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="d3e64-118">Der Vermittlungs Server stellt auch Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway zum Weiterleiten an das PSTN oder die Telefonanlage vor.</span><span class="sxs-lookup"><span data-stu-id="d3e64-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="d3e64-119">Eine Liste der Partner, die mit Microsoft zusammenarbeiten, um Geräte zur Verfügung zu stellen, die mit Skype for Business Server funktionieren, finden Sie auf [der Microsoft Unified Communications Partners-Website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d3e64-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="d3e64-120">Nebenstellenanlagen</span><span class="sxs-lookup"><span data-stu-id="d3e64-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="d3e64-121">Wenn Sie über eine vorhandene VoIP-Infrastruktur verfügen, die eine PBX (Private Branch Exchange) verwendet, können Sie Ihre Telefonanlage mit Enterprise-VoIP verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3e64-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="d3e64-122">Die unterstützten Enterprise-VoIP-Integrationsszenarien sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d3e64-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="d3e64-123">IP-Telefonanlage, die die medienumgehung mit einem Vermittlungs Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3e64-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="d3e64-124">IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.</span><span class="sxs-lookup"><span data-stu-id="d3e64-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="d3e64-125">TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="d3e64-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3e64-126">Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs.</span><span class="sxs-lookup"><span data-stu-id="d3e64-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d3e64-127">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d3e64-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d3e64-128">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter [Unified Communications Open Interoperability Program-lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d3e64-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="d3e64-129">Details zu Partnern, die Enterprise-VoIP-Lösungen anbieten, finden Sie auf der [Microsoft Unified Communications Partners-Website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d3e64-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="d3e64-130">Details zu Partnern, die Enterprise-VoIP-Hardwarelösungen anbieten, einschließlich PSTN-Gateways, finden Sie auf der [Microsoft Unified Communications Partners-Website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d3e64-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

