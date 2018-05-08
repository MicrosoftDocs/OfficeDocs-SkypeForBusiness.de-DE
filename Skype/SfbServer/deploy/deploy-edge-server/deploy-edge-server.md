---
title: Bereitstellen von Edgeserver in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Zusammenfassung: Erfahren Sie, wie ein Edge-Server oder einem edgepool in Ihrer Skype für Business Server 2015 Umgebung bereitstellen.'
ms.openlocfilehash: 571d8001b70f8b4f03d96042683da1bfae7fdd2d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-edge-server-in-skype-for-business-server-2015"></a><span data-ttu-id="bfa2b-103">Bereitstellen von Edgeserver in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-103">Deploy Edge Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bfa2b-104">**Zusammenfassung:** Erfahren Sie, wie ein Edge-Server oder einem edgepool in Ihrer Skype für Business Server 2015 Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment.</span></span>
  
<span data-ttu-id="bfa2b-105">Gründe für die Bereitstellung eines Edgeservers oder einem edgepool in Ihrer Skype für Business Server 2015 Umgebung?</span><span class="sxs-lookup"><span data-stu-id="bfa2b-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment?</span></span> <span data-ttu-id="bfa2b-106">Dies ist notwendig, wenn externe Benutzer, die nicht in Ihrem firmeninternen Netzwerk angemeldet sind, mit internen Benutzern interagieren müssen.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="bfa2b-107">Zu externen Benutzern gehören authentifizierte und anonyme Remotebenutzer, Verbundpartner oder andere mobile Kunden.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server-2015"></a><span data-ttu-id="bfa2b-108">Prüfliste zur Bereitstellung für den Edge für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-108">Deployment checklist for the Edge, for Skype for Business Server 2015</span></span>

<span data-ttu-id="bfa2b-109">Wie bereits erwähnt, geht viel in einer Edge-Server-Bereitstellung für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server 2015.</span></span> <span data-ttu-id="bfa2b-110">Diese Prüfliste enthält eine Übersicht über die Aufgaben, die Sie erforderlichen Schritte sowie Links zu ausführlichere Schritte.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="bfa2b-111">Wir hoffen, dass Sie im Abschnitt [Planen von Edge-Server-Bereitstellungen in Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="bfa2b-112">Wenn dies nicht der Fall ist, werden viele der Dinge, denen wir verweisen auf es beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="bfa2b-113">Im Abschnitt Bereitstellung enthält nur Prozeduren, damit begründungen zu diesen Schritten planen den Ausgangspunkt ist, wenn Sie wissen möchten.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="bfa2b-114">In dieser Dokumentation wird davon ausgegangen, dass Sie auch die grundlegende Bereitstellung Skype für Business Server 2015 durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="bfa2b-115">Sie werden diese Bereitstellung Side-by-Side am Rand, durchführen, aber Sie müssen diese Schritte zuerst und tätigen Topologie für den Rand, die hier beschriebenen klicken Sie dann vermutlich.</span><span class="sxs-lookup"><span data-stu-id="bfa2b-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="bfa2b-116">Hier finden Sie die allgemeinen Schritte, die Sie befolgen müssen, und Angaben darüber, wo Sie die entsprechenden Schritte finden:</span><span class="sxs-lookup"><span data-stu-id="bfa2b-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="bfa2b-117">Edge-Server System Requirements for Business Server 2015 in Skype</span><span class="sxs-lookup"><span data-stu-id="bfa2b-117">Edge Server system requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="bfa2b-118">Edge-Server-umgebungsanforderungen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-118">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="bfa2b-119">Erstellen Sie eine Edge-Topologie für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-119">Create your Edge topology for Skype for Business Server 2015</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="bfa2b-120">Stellen Sie Edgeserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-120">Deploy Edge Servers in Skype for Business Server 2015</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="bfa2b-121">Überprüfen Sie Ihre edgebereitstellung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bfa2b-121">Validate your Edge deployment in Skype for Business Server 2015</span></span>](validate-edge-deployment.md)
    

