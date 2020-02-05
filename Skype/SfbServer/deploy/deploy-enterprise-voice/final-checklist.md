---
title: Endgültige Checkliste für Anrufsteuerungen für Skype for Business Server
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Endgültige Checkliste für die Bereitstellung der Anrufannahme Steuerung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767228"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="b16c7-103">Bereitstellung der Anrufsteuerung: endgültige Checkliste für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b16c7-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="b16c7-104">Endgültige Checkliste für die Bereitstellung der Anrufannahme Steuerung in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="b16c7-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b16c7-105">Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="b16c7-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="b16c7-106">Wenn ein oder mehrere Edgeserver bereitgestellt werden, muss jede externe Schnittstellen-IP-Adresse der Subnetliste in den Netzwerkkonfigurationseinstellungen mit einer Bitmaske von 32 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b16c7-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="b16c7-107">Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b16c7-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b16c7-108">Edgeserver müssen keine CAC-Implementierung implementieren.</span><span class="sxs-lookup"><span data-stu-id="b16c7-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="b16c7-109">Stellen Sie sicher, dass die CAC-Funktion aktiviert ist, wie unter [Aktivieren der Anrufsteuerung in Skype for Business Server](enable-call-admission-control.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="b16c7-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="b16c7-110">Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b16c7-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="b16c7-111">Dies kann über den Topologie-Generator erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b16c7-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="b16c7-112">Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie Sie *nicht* .</span><span class="sxs-lookup"><span data-stu-id="b16c7-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="b16c7-113">Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b16c7-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="b16c7-114">Darüber hinaus ist es wichtig, dass jedes Subnetz einer Netzwerk Website zugeordnet ist, wie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](deploy-network.md)erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="b16c7-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="b16c7-115">Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b16c7-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

