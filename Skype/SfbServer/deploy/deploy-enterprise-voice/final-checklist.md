---
title: Anruf Admission Control endgültigen Prüfliste zur Bereitstellung von Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Endgültige Checkliste für die Bereitstellung von Call Admission Control (CAC) in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: e5791aa6f3b32e423f36021314bec930fa7f74e5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025674"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="30dc5-103">Rufen Sie die Bereitstellung der anrufsteuerung: endgültige Checkliste für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="30dc5-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="30dc5-104">Endgültige Checkliste für die Bereitstellung von Call Admission Control (CAC) in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="30dc5-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="30dc5-105">Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="30dc5-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="30dc5-106">Wenn eine oder mehrere Edgeserver bereitgestellt werden, muss jede externe IP-Adresse der Subnetliste in den netzwerkkonfigurationseinstellungen, denen eine Bitmaske 32 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="30dc5-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="30dc5-107">Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="30dc5-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30dc5-108">Edge-Server sind zum Implementieren der Anrufsteuerung nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30dc5-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="30dc5-109">Stellen Sie sicher, dass die Anrufsteuerung aktiviert ist, als der angegebene in [Aktivieren der anrufsteuerung in Skype für Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="30dc5-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="30dc5-110">Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="30dc5-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="30dc5-111">Dies kann über den Topologie-Generator erfolgen.</span><span class="sxs-lookup"><span data-stu-id="30dc5-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="30dc5-112">Wenn eine Warnung generiert wird, wenn Sie veröffentlichen, ignoriert *jedoch nicht* .</span><span class="sxs-lookup"><span data-stu-id="30dc5-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="30dc5-113">Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="30dc5-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="30dc5-114">Es ist außerdem wichtig, dass jedes Subnetz einem Netzwerkstandort zugeordnet werden soll, wie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](deploy-network.md)erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="30dc5-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="30dc5-115">Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="30dc5-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

