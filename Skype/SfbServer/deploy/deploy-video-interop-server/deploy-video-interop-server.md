---
title: Bereitstellen des Video-Interop-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Zusammenfassung: Bereitstellen der VIS-Serverrolle in Skype for Business Server.'
ms.openlocfilehash: 790030e3ef0b88473f6fc1750c054db5cdd74b4a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235586"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="081a4-103">Bereitstellen des Video-Interop-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="081a4-104">**Zusammenfassung:** Bereitstellen der VIS-Serverrolle in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="081a4-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="081a4-105">Skype for Business Server kann jetzt direkt in Cisco Teleconferencing Systems (VTCs) wie Cisco C60 oder Cisco MX300 integriert werden.</span><span class="sxs-lookup"><span data-stu-id="081a4-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="081a4-106">Dies erfordert die Einführung einer neuen Serverrolle, die als Video-Interop-Server (VIS) bezeichnet wird, und die richtige Konfiguration sowohl des VIS als auch des Geräts, mit dem es interagieren soll.</span><span class="sxs-lookup"><span data-stu-id="081a4-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="081a4-107">Ein VTC wird mit einer vorhandenen Cisco-Infrastruktur wie beispielsweise Cisco Unified Communication Manager (CUCM) registriert und ein Video-SIP-Trunk wird zwischen CUCM und dem VIS-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="081a4-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="081a4-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="081a4-108">In this section</span></span>

<span data-ttu-id="081a4-109">Die Konfiguration der Interoperabilität zwischen einem VIS-Server oder -Pool und VTC-Systemen erfordert die Durchführung der folgenden fünf Verfahren:</span><span class="sxs-lookup"><span data-stu-id="081a4-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="081a4-110">Erstellen eines VIS-Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="081a4-111">Bereitstellen der VIS-Serverrolle in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="081a4-112">Konfigurieren des Video-Interop-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="081a4-113">Konfigurieren von CUCM für die Zusammenarbeit mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="081a4-114">Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="081a4-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="081a4-115">Related sections</span></span>

[<span data-ttu-id="081a4-116">Planen des Video-Interop-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="081a4-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

