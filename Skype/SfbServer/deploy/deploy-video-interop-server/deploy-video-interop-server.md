---
title: Bereitstellen eines Video Interop-Servers in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Zusammenfassung: Stellen Sie die Serverrolle gegenüber in Skype für Business Server bereit.'
ms.openlocfilehash: 8bb21d667774b50fd7a7caddabfbd02e8125a4a2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967572"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="82e80-103">Bereitstellen eines Video Interop-Servers in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="82e80-104">**Zusammenfassung:** Stellen Sie die Serverrolle gegenüber in Skype für Business Server bereit.</span><span class="sxs-lookup"><span data-stu-id="82e80-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="82e80-105">Skype für Business Server kann jetzt direkt in Cisco Telekonferenzen Systeme (VTCs) wie die Cisco C60 oder Cisco MX300 integriert.</span><span class="sxs-lookup"><span data-stu-id="82e80-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="82e80-106">Dies erfordert eine neue Serverrolle Namens die Video Interop Server (Zoll) und die ordnungsgemäße Konfiguration der gegenüber und Geräte wird die Interaktion mit die Einführung.</span><span class="sxs-lookup"><span data-stu-id="82e80-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="82e80-107">Ein VTC wird mit einer vorhandenen Cisco-Infrastruktur wie beispielsweise Cisco Unified Communication Manager (CUCM) registriert und ein Video-SIP-Trunk wird zwischen CUCM und dem VIS-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="82e80-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="82e80-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="82e80-108">In this section</span></span>

<span data-ttu-id="82e80-109">Die Konfiguration der Interoperabilität zwischen einem VIS-Server oder -Pool und VTC-Systemen erfordert die Durchführung der folgenden fünf Verfahren:</span><span class="sxs-lookup"><span data-stu-id="82e80-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="82e80-110">Erstellen eines Pools gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="82e80-111">Bereitstellen der Serverrolle gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="82e80-112">Konfigurieren der Interop-Videoserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="82e80-113">Konfigurieren von CUCM für die Interoperation mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="82e80-114">Konfigurieren einer VTC für die Interoperation mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="82e80-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="82e80-115">Related sections</span></span>

[<span data-ttu-id="82e80-116">Planen der Interop-Videoserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82e80-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

