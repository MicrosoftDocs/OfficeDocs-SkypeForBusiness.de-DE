---
title: Bereitstellen Sie die anrufsteuerung in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Die anrufsteuerung (CAC)-Steuerelement eine Lösung ist, die bestimmt, ob eine in Echtzeit-Sitzung hergestellt werden kann basierend auf der verfügbaren Bandbreite, um zu verhindern, dass schlechten Qualität von Audio/Video für Benutzer auf überlastete Netzwerke.
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892864"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="fe704-103">Bereitstellen Sie die anrufsteuerung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="fe704-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="fe704-104">Die anrufsteuerung (CAC)-Steuerelement eine Lösung ist, die bestimmt, ob eine in Echtzeit-Sitzung hergestellt werden kann basierend auf der verfügbaren Bandbreite, um zu verhindern, dass schlechten Qualität von Audio/Video für Benutzer auf überlastete Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="fe704-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="fe704-105">Weitere Informationen finden Sie unter [Planen für die anrufsteuerung in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="fe704-106">Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="fe704-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="fe704-107">Sammeln Sie alle erforderlichen Informationen für die Enterprise-Netzwerktopologie gemäß [Beispiel: Sammeln von Anforderungen für die anrufsteuerung in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="fe704-108">Falls noch nicht geschehen, müssen Sie Netzwerkregionen und Standorten definieren und Subnetzen zu Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="fe704-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="fe704-109">Weitere Informationen hierzu finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="fe704-110">Erstellen von Bandbreite Richtlinienprofilen, wie in [Erstellen von bandbreitenrichtlinienprofilen in Skype für Business Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fe704-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="fe704-111">Erstellen Sie netzwerkregionenverbindungen, wie in [Erstellen von netzwerkregionenverbindungen in Skype für Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="fe704-112">Erstellen Sie Kommunikation zwischen netzwerkregionsrouten, wie in [Erstellen regionenübergreifende Netzwerkrouten in Skype für Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="fe704-113">Erstellen von standortübergreifenden Netzwerkrichtlinien, wie in [Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype für Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="fe704-114">Aktivieren Sie die anrufsteuerung, wie in der [anrufsteuerung in Skype für Business Server aktivieren](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="fe704-115">Prüfen Sie ein paar abschließende Einstellungen, um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="fe704-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="fe704-116">Weitere Informationen hierzu finden Sie unter [rufen Sie die Bereitstellung der anrufsteuerung: endgültige Checkliste für Skype für Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="fe704-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

