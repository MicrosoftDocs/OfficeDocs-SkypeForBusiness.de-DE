---
title: PSTN-Konnektivitätskomponenten in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype für Business Server.
ms.openlocfilehash: 69b010d7f4e444214581ebc1b84babadbf14e68f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998518"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="d5ad4-103">PSTN-Konnektivitätskomponenten in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d5ad4-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="d5ad4-104">Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d5ad4-105">Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="d5ad4-106">Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="d5ad4-107">Aus Sicht des Benutzers sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz wie jede andere SIP-Sitzung scheint.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="d5ad4-108">Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway bereitstellen – mit Nebenstellenanlage (was auch als direkte SIP-Verbindung bezeichnet wird) oder ohne Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="d5ad4-109">SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="d5ad4-109">SIP Trunking</span></span>

<span data-ttu-id="d5ad4-110">Als Alternative zur Verwendung von PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking an das Telefonfestnetz verbinden.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="d5ad4-111">Mit SIP-Trunking sind folgende Szenarien möglich:</span><span class="sxs-lookup"><span data-stu-id="d5ad4-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="d5ad4-112">Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="d5ad4-113">Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="d5ad4-114">Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="d5ad4-115">PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="d5ad4-115">PSTN gateways</span></span>

<span data-ttu-id="d5ad4-116">PSTN-Gateways sind Drittanbieter-Geräte, die übersetzen Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und einem PSTN oder einer Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="d5ad4-117">PSTN-Gateways arbeiten mit der Vermittlungsserver einen PSTN oder PBX-Anruf an einen Enterprise-VoIP-Client durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="d5ad4-118">Der Vermittlungsserver übergibt außerdem Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway für die Weiterleitung an das PSTN oder PBX-Ressource.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="d5ad4-119">Eine Liste der Partner, die mit Microsoft-Geräte bereitstellen, die Arbeit mit Skype für Business Server arbeiten, finden Sie unter [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d5ad4-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="d5ad4-120">Nebenstellenanlagen</span><span class="sxs-lookup"><span data-stu-id="d5ad4-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="d5ad4-121">Wenn Sie eine vorhandene VoIP-Infrastruktur, die eine private Branch Exchange, Nebenstellenanlage (PBX) verwendet haben, können Sie Ihre Nebenstellenanlage mit Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="d5ad4-122">Die unterstützten Enterprise Voice-PBX-Integrationsszenarien sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d5ad4-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="d5ad4-123">IP-Nebenstellenanlage, die die medienumgehung mit einem Vermittlungsserver unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="d5ad4-124">IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="d5ad4-125">TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5ad4-126">Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d5ad4-127">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5ad4-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d5ad4-128">Die medienumgehung wird nur mit Produkten unterstützt und Versionen am aufgeführten [Unified Communications Open Interoperability Program – Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="d5ad4-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="d5ad4-129">Ausführliche Informationen zu Partnern, die Enterprise-VoIP-Lösungen anbieten, finden Sie in der [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d5ad4-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="d5ad4-130">Ausführliche Informationen zu Partnern, die Enterprise-VoIP-hardwarelösungen, einschließlich PSTN-Gateways anbieten finden Sie in der [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="d5ad4-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

