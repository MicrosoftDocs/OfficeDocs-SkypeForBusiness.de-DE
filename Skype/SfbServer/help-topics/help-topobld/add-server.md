---
title: Hinzufügen des Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'So fügen Sie einem vorhandenen Serverpool der folgenden Pooltypen einen neuen Server hinzu:'
ms.openlocfilehash: 5e6d1772b1cb18fe8c392e3ad9fa4f131415e522
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216406"
---
# <a name="add-server"></a><span data-ttu-id="4349c-103">Hinzufügen des Servers</span><span class="sxs-lookup"><span data-stu-id="4349c-103">Add Server</span></span>
 
<span data-ttu-id="4349c-104">So fügen Sie einem vorhandenen Serverpool der folgenden Pooltypen einen neuen Server hinzu:</span><span class="sxs-lookup"><span data-stu-id="4349c-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="4349c-105">Front-End-Server der Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="4349c-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="4349c-106">Director-Server</span><span class="sxs-lookup"><span data-stu-id="4349c-106">Director server</span></span>
    
- <span data-ttu-id="4349c-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="4349c-107">Mediation Server</span></span>
    
- <span data-ttu-id="4349c-108">Audio-Video-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="4349c-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="4349c-109">Vertrauenswürdiger Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="4349c-109">Trusted Application server</span></span>
    
<span data-ttu-id="4349c-p101">Jeder der neuen Poolserver hat unterschiedliche Anforderungen. Bestimmen Sie in den folgenden Abschnitten den Servertyp, den Sie dem vorhandenen Pool hinzufügen, und geben Sie die angeforderten Informationen zum jeweiligen Servertyp an. Die bereitgestellten Informationen werden zum Definieren des neuen Poolservers verwendet.</span><span class="sxs-lookup"><span data-stu-id="4349c-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="4349c-113">**Front-End-Server der Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="4349c-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="4349c-114">Vollqualifizierter Domänenname des neuen Servers gemäß der DNS-Definition (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="4349c-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="4349c-p102">Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.</span><span class="sxs-lookup"><span data-stu-id="4349c-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="4349c-118">Geben Sie eine **PSTN-IP-Adresse** an, wenn auf dem Front-End-Server ein Vermittlungsserver verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4349c-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="4349c-119">Wählen Sie die Option **IPv6 aktivieren**, um IPv6 für diesen Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4349c-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="4349c-120">**Director-Server**</span><span class="sxs-lookup"><span data-stu-id="4349c-120">**Director server**</span></span>
  
- <span data-ttu-id="4349c-121">Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.</span><span class="sxs-lookup"><span data-stu-id="4349c-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4349c-p103">Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte IP-Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.</span><span class="sxs-lookup"><span data-stu-id="4349c-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="4349c-125">**Vermittlungsserver**</span><span class="sxs-lookup"><span data-stu-id="4349c-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="4349c-126">Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.</span><span class="sxs-lookup"><span data-stu-id="4349c-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4349c-p104">Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Alternativ können Sie **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und eine bestimmte IP-Adresse für den neuen Server als primäre IP-Adresse sowie eine IP-Adresse für das PSTN (Public Switched Telephone Network, Telefonfestnetz) eingeben. Die eingegebene IP-Adressen sind die einzigen, die für die vorgesehenen Dienste antworten.</span><span class="sxs-lookup"><span data-stu-id="4349c-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4349c-p105">Beim Vermittlungsserver sind die als primäre IP-Adresse und PSTN-IP-Adresse eingegebenen IP-Adressen identisch. Die IP-Adressen können gesondert definiert werden, wenn Sie dedizierte Netzwerkschnittstellen oder separate IP-Adressen für dieselbe Netzwerkschnittstellen verwenden. Wenn Sie über zwei Netzwerkschnittstellen verfügen (eine für die lokale Netzwerkverbindung und eine für die PSTN-Verbindung), müssen Sie zwei unterschiedliche IP-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4349c-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="4349c-133">**Audio/Video-Konferenzserver**</span><span class="sxs-lookup"><span data-stu-id="4349c-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="4349c-134">Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.</span><span class="sxs-lookup"><span data-stu-id="4349c-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4349c-p106">Wählen Sie **Alle konfigurierten IP-Adressen verwenden** aus, was bedeutet, dass Sie beliebige auf dem Computer definierte IP-Adressen verwenden können. Sie können auch **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** auswählen und für den neuen Server eine bestimmte Adresse eingeben. Die eingegebene IP-Adresse ist die einzige, die für die gehosteten Dienste antwortet.</span><span class="sxs-lookup"><span data-stu-id="4349c-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="4349c-138">**Vertrauenswürdiger Anwendungsserver**</span><span class="sxs-lookup"><span data-stu-id="4349c-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="4349c-139">Der vollqualifizierte Domänenname des neuen Servers gemäß der DNS-Definition.</span><span class="sxs-lookup"><span data-stu-id="4349c-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

