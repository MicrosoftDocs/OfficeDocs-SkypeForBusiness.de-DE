---
title: Bereitstellung von Skype Room System-Exchange- und -Skype-Konten
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
description: Lesen Sie diese Themen und erfahren Sie, wie Sie Exchange- und Skype-Konten für Skype Room System bereitstellen.
ms.openlocfilehash: 584b4582f68510302af81afa32b47672220304f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988430"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="d21b9-103">Bereitstellung von Skype Room System-Exchange- und -Skype-Konten</span><span class="sxs-lookup"><span data-stu-id="d21b9-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="d21b9-104">Lesen Sie diese Themen und erfahren Sie, wie Sie Exchange- und Skype-Konten für Skype Room System bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d21b9-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="d21b9-105">Skype-Chatroom-Systemen v2 ist ein anderes Produkt mit verschiedenen Abhängigkeiten und Bereitstellungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="d21b9-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="d21b9-106">Informationen zu Skype Raum Systemen v2 finden Sie unter Skype Raum Systemen v2 [Übersicht über die Bereitstellung](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d21b9-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d21b9-107">Skype Raum System-Konten, hängt vom Typ der Topologie Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="d21b9-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="d21b9-108">Weitere Informationen zu Active Directory-Topologien finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d21b9-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="d21b9-109">Bereitstellung von Skype Raum System Exchange &amp; Skype für Kunden</span><span class="sxs-lookup"><span data-stu-id="d21b9-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="d21b9-110">In den folgenden Themen wird beschrieben, wie Exchange- und Skype for Business-Konten für Skype Room System bereitgestellt und verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="d21b9-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="d21b9-111">Lokale Bereitstellungen mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="d21b9-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="d21b9-112">Lokale Bereitstellungen mit mehreren Gesamtstrukturen</span><span class="sxs-lookup"><span data-stu-id="d21b9-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="d21b9-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="d21b9-113">Office 365</span></span>
    
- <span data-ttu-id="d21b9-114">Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="d21b9-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="d21b9-115">Skype Room System- und Skype for Business-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="d21b9-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="d21b9-116">Verwalten von Skype Room System-Konten</span><span class="sxs-lookup"><span data-stu-id="d21b9-116">Manage Skype Room System accounts</span></span>
    

