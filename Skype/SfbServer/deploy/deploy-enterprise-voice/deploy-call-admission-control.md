---
title: Bereitstellen der Anrufsteuerung in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Die anrufsteuerung (CAC)-Steuerelement eine Lösung ist, die bestimmt, ob eine in Echtzeit-Sitzung hergestellt werden kann basierend auf der verfügbaren Bandbreite, um zu verhindern, dass schlechten Qualität von Audio/Video für Benutzer auf überlastete Netzwerke. Weitere Informationen finden Sie unter Plan für die anrufsteuerung in Skype für Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="ab431-104">Bereitstellen der Anrufsteuerung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab431-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ab431-105">Die anrufsteuerung (CAC)-Steuerelement eine Lösung ist, die bestimmt, ob eine in Echtzeit-Sitzung hergestellt werden kann basierend auf der verfügbaren Bandbreite, um zu verhindern, dass schlechten Qualität von Audio/Video für Benutzer auf überlastete Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="ab431-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="ab431-106">Weitere Informationen finden Sie unter [Planen für die anrufsteuerung in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="ab431-107">Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="ab431-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="ab431-108">Sammeln Sie alle erforderlichen Informationen für die Enterprise-Netzwerktopologie gemäß [Beispiel: Sammeln von Anforderungen für die anrufsteuerung in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="ab431-109">Falls noch nicht geschehen, müssen Sie Netzwerkregionen und Standorten definieren und Subnetzen zu Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ab431-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="ab431-110">Weitere Informationen hierzu finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Business 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="ab431-111">Erstellen von Bandbreite Richtlinienprofilen, wie in [Erstellen von bandbreitenrichtlinienprofilen in Skype für Business Server 2015](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ab431-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="ab431-112">Erstellen Sie netzwerkregionenverbindungen, wie in [Erstellen von netzwerkregionenverbindungen in Skype für Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="ab431-113">Kommunikation zwischen netzwerkregionsrouten, wie in [Erstellen regionenübergreifende Netzwerkrouten in Skype für Business Server 2015](create-network-interregional-routes.md)zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab431-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="ab431-114">Erstellen von standortübergreifenden Netzwerkrichtlinien, wie in [Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype für Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="ab431-115">Aktivieren Sie die anrufsteuerung als [Aktivieren der anrufsteuerung in Skype für Business Server 2015](enable-call-admission-control.md)ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab431-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="ab431-116">Prüfen Sie ein paar abschließende Einstellungen, um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ab431-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="ab431-117">Weitere Informationen hierzu finden Sie unter [rufen Sie die Bereitstellung der anrufsteuerung: endgültige Checkliste für Skype für Business Server 2015](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="ab431-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

