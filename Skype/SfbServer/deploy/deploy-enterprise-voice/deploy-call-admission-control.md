---
title: Bereitstellen der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern.
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767668"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="27b36-103">Bereitstellen der Anrufsteuerung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="27b36-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="27b36-104">Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="27b36-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="27b36-105">Weitere Informationen finden Sie unter [Planen der Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="27b36-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="27b36-106">Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="27b36-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="27b36-107">Sammeln Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie, wie in [Beispiel: Erfassen der Anforderungen für die Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b36-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="27b36-108">Falls noch nicht geschehen, müssen Sie Netzwerkregionen und Standorten definieren und Subnetzen zu Netzwerkstandorten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="27b36-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="27b36-109">Ausführliche Informationen finden Sie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="27b36-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="27b36-110">Erstellen von Bandbreitenrichtlinien Profilen, wie in [Erstellen von Bandbreitenrichtlinien Profilen in Skype for Business Server](create-bandwidth-policy-profiles.md) beschrieben</span><span class="sxs-lookup"><span data-stu-id="27b36-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="27b36-111">Erstellen Sie Netzwerk Regions Verknüpfungen, wie unter [Erstellen von Netzwerk Regions Verknüpfungen in Skype for Business Server](create-network-region-links.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b36-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="27b36-112">Erstellen Sie netzwerkübergreifende Routen, wie unter Erstellen von [Netzwerk interregionalen Routen in Skype for Business Server](create-network-interregional-routes.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b36-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="27b36-113">Erstellen Sie netzwerkübergreifende Richtlinien, wie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in Skype for Business Server](create-network-intersite-policies.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b36-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="27b36-114">Aktivieren Sie die Anrufsteuerung, wie unter [Aktivieren der Anrufsteuerung in Skype for Business Server](enable-call-admission-control.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27b36-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="27b36-115">Prüfen Sie ein paar abschließende Einstellungen, um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="27b36-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="27b36-116">Ausführliche Informationen finden Sie unter [Bereitstellung von Anrufsteuerung: endgültige Checkliste für Skype for Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="27b36-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

