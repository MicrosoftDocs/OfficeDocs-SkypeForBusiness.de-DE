---
title: Bereitstellen von Edgeserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Edgeserver oder einen Edge-Pool in Ihrer Skype for Business Server-Umgebung bereitstellen.'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306951"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="ede7d-103">Bereitstellen von Edgeserver in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="ede7d-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Edgeserver oder einen Edge-Pool in Ihrer Skype for Business Server-Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ede7d-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="ede7d-105">Gründe für die Bereitstellungeines Edge-Servers oder eines Edge-Pools in Ihrer Skype for Business Server-Umgebung</span><span class="sxs-lookup"><span data-stu-id="ede7d-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="ede7d-106">Dies ist notwendig, wenn externe Benutzer, die nicht in Ihrem firmeninternen Netzwerk angemeldet sind, mit internen Benutzern interagieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ede7d-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="ede7d-107">Zu externen Benutzern gehören authentifizierte und anonyme Remotebenutzer, Verbundpartner oder andere mobile Kunden.</span><span class="sxs-lookup"><span data-stu-id="ede7d-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="ede7d-108">Checkliste für die Bereitstellung von Edge für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="ede7d-109">Wie bereits erwähnt, geht viel in eine Edge-Server-Bereitstellung für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ede7d-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="ede7d-110">Diese Checkliste gibt Ihnen einen Überblick über die Aufgaben, die Sie erledigen müssen, sowie Links zu weiteren detaillierten Schritten.</span><span class="sxs-lookup"><span data-stu-id="ede7d-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="ede7d-111">Wir hoffen, dass Sie im Abschnitt [Planen von Edgeserver-Bereitstellungen in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="ede7d-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="ede7d-112">Wenn dies nicht der Fall ist, werden viele der Dinge, auf die wir verweisen, dort detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ede7d-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="ede7d-113">Der Bereitstellungs Abschnitt enthält nur Prozeduren, wenn Sie also wissen möchten, welche Gründe hinter diesen Schritten liegen, sollten Sie mit der Planung beginnen.</span><span class="sxs-lookup"><span data-stu-id="ede7d-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="ede7d-114">In dieser Dokumentation wird auch davon ausgegangen, dass Sie auch die grundlegende Bereitstellung von Skype for Business Server durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ede7d-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="ede7d-115">Möglicherweise führen Sie die Bereitstellung nebeneinander mit dem Edge aus, doch müssen Sie zuerst diese Schritte ausführen, und dann können Sie die Topologie-Änderungen für den hier dokumentierten Rand vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ede7d-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="ede7d-116">Hier finden Sie die allgemeinen Schritte, die Sie befolgen müssen, und Angaben darüber, wo Sie die entsprechenden Schritte finden:</span><span class="sxs-lookup"><span data-stu-id="ede7d-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="ede7d-117">Systemanforderungen für Edge-Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="ede7d-118">Umgebungsanforderungen des Edge-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="ede7d-119">Erstellen Ihrer Edge-Topologie für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="ede7d-120">Bereitstellen von Edgeserver in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="ede7d-121">Überprüfen Ihrer Edge-Bereitstellung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede7d-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

