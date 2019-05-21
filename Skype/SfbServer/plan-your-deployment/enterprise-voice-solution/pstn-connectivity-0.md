---
title: Planen der PSTN-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planen Sie die PSTN-Konnektivität in Enterprise-VoIP in Skype for Business Server.
ms.openlocfilehash: f0b6aa6b43562fea91885b0d55d75fd234ab97de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276497"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="c750f-103">Planen der PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="c750f-104">Planen Sie die PSTN-Konnektivität in Enterprise-VoIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c750f-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="c750f-105">Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="c750f-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="c750f-106">Benutzer, die Anrufe tätigen und empfangen, sollten sich der zugrunde liegenden Technologie nicht bewusst sein: ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN sollte aus Sicht des Benutzers wie nur ein weiterer Telefonanruf aussehen.</span><span class="sxs-lookup"><span data-stu-id="c750f-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="c750f-107">Skype for Business Server bietet zuverlässige, skalierbare PSTN-Konnektivität mithilfe der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="c750f-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="c750f-108">**SIP-Trunks** mit einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP)</span><span class="sxs-lookup"><span data-stu-id="c750f-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="c750f-109">**Direkte SIP-Verbindungen** mit einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="c750f-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="c750f-110">**Direkte SIP-Verbindungen** mit einer Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="c750f-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="c750f-p102">Je nach Größe, geografischer Abdeckung und der vorhandenen Enterprise-VoIP-Infrastruktur kann ein Unternehmen eine, zwei oder sogar alle drei dieser Optionen an verschiedenen Standorten einsetzen.</span><span class="sxs-lookup"><span data-stu-id="c750f-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c750f-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="c750f-113">In this section</span></span>

- [<span data-ttu-id="c750f-114">SIP-Trunking in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="c750f-115">Direkte SIP-Verbindungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="c750f-116">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="c750f-117">Übersetzungsregeln in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="c750f-118">Planen des ausgehenden VoIP-Routings in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c750f-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

