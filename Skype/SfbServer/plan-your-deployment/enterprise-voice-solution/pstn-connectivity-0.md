---
title: Planen der PSTN-Konnektivität in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planen von PSTN-Konnektivität in Enterprise-VoIP in Skype für Business Server.
ms.openlocfilehash: 228391049988c2eb886c0cb4e7caccce6f55ff3b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="220d5-103">Planen der PSTN-Konnektivität in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="220d5-104">Planen von PSTN-Konnektivität in Enterprise-VoIP in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="220d5-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="220d5-105">Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="220d5-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="220d5-106">Benutzer, die Anrufe tätigen und empfangen darf nicht die zugrunde liegende Technologie bewusst sein: aus Sicht des Benutzers, ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz scheinbar nur ein weiteres Telefonanruf sollten.</span><span class="sxs-lookup"><span data-stu-id="220d5-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="220d5-107">Skype für Business Server bietet zuverlässige, skalierbare PSTN-Anbindung mithilfe der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="220d5-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="220d5-108">**SIP-Trunks** mit einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP)</span><span class="sxs-lookup"><span data-stu-id="220d5-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="220d5-109">**Direkte SIP-Verbindungen** mit einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="220d5-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="220d5-110">**Direkte SIP-Verbindungen** mit einer Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="220d5-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="220d5-p102">Je nach Größe, geografischer Abdeckung und der vorhandenen Enterprise-VoIP-Infrastruktur kann ein Unternehmen eine, zwei oder sogar alle drei dieser Optionen an verschiedenen Standorten einsetzen.</span><span class="sxs-lookup"><span data-stu-id="220d5-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="220d5-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="220d5-113">In this section</span></span>

- [<span data-ttu-id="220d5-114">SIP-Trunking in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="220d5-115">Direkte SIP-Verbindungen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="220d5-116">M: n-Trunk in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="220d5-117">Übersetzungsregeln in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="220d5-118">Planen der ausgehende VoIP-routing in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220d5-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

