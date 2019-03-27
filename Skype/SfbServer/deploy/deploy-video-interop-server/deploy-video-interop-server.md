---
title: Bereitstellen eines Video Interop-Servers in Skype für Business Server
ms.reviewer: ''
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
ms.openlocfilehash: 3f3c48279ba08ca124f11ac0fb90c457ae69ac9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884557"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="946ea-103">Bereitstellen eines Video Interop-Servers in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="946ea-104">**Zusammenfassung:** Stellen Sie die Serverrolle gegenüber in Skype für Business Server bereit.</span><span class="sxs-lookup"><span data-stu-id="946ea-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="946ea-105">Skype für Business Server kann jetzt direkt in Cisco Telekonferenzen Systeme (VTCs) wie die Cisco C60 oder Cisco MX300 integriert.</span><span class="sxs-lookup"><span data-stu-id="946ea-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="946ea-106">Dies erfordert eine neue Serverrolle Namens die Video Interop Server (Zoll) und die ordnungsgemäße Konfiguration der gegenüber und Geräte wird die Interaktion mit die Einführung.</span><span class="sxs-lookup"><span data-stu-id="946ea-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="946ea-107">Ein VTC wird mit einer vorhandenen Cisco-Infrastruktur wie beispielsweise Cisco Unified Communication Manager (CUCM) registriert und ein Video-SIP-Trunk wird zwischen CUCM und dem VIS-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="946ea-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="946ea-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="946ea-108">In this section</span></span>

<span data-ttu-id="946ea-109">Die Konfiguration der Interoperabilität zwischen einem VIS-Server oder -Pool und VTC-Systemen erfordert die Durchführung der folgenden fünf Verfahren:</span><span class="sxs-lookup"><span data-stu-id="946ea-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="946ea-110">Erstellen eines Pools gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="946ea-111">Bereitstellen der Serverrolle gegenüber in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="946ea-112">Konfigurieren der Interop-Videoserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="946ea-113">Konfigurieren von CUCM für die Interoperation mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="946ea-114">Konfigurieren einer VTC für die Interoperation mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="946ea-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="946ea-115">Related sections</span></span>

[<span data-ttu-id="946ea-116">Planen der Interop-Videoserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="946ea-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

