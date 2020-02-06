---
title: Planen der PSTN-Konnektivität in Skype for Business Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planen Sie die PSTN-Konnektivität in Enterprise-VoIP in Skype for Business Server.
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802545"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="2ff08-103">Planen der PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="2ff08-104">Planen Sie die PSTN-Konnektivität in Enterprise-VoIP in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ff08-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="2ff08-105">Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="2ff08-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="2ff08-106">Benutzer, die Anrufe tätigen und empfangen, sollten sich der zugrunde liegenden Technologie nicht bewusst sein: ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN sollte aus Sicht des Benutzers wie nur ein weiterer Telefonanruf aussehen.</span><span class="sxs-lookup"><span data-stu-id="2ff08-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="2ff08-107">Skype for Business Server bietet zuverlässige, skalierbare PSTN-Konnektivität mithilfe der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="2ff08-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="2ff08-108">**SIP-Trunks** mit einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP)</span><span class="sxs-lookup"><span data-stu-id="2ff08-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="2ff08-109">**Direkte SIP-Verbindungen** mit einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="2ff08-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="2ff08-110">**Direkte SIP-Verbindungen** mit einer Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="2ff08-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="2ff08-p102">Je nach Größe, geografischer Abdeckung und der vorhandenen Enterprise-VoIP-Infrastruktur kann ein Unternehmen eine, zwei oder sogar alle drei dieser Optionen an verschiedenen Standorten einsetzen.</span><span class="sxs-lookup"><span data-stu-id="2ff08-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2ff08-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="2ff08-113">In this section</span></span>

- [<span data-ttu-id="2ff08-114">SIP-Trunking in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="2ff08-115">Direkte SIP-Verbindungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="2ff08-116">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="2ff08-117">Übersetzungsregeln in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="2ff08-118">Planen des ausgehenden VoIP-Routings in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ff08-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

