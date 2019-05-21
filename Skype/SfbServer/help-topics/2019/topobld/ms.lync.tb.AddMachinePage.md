---
title: Hinzufügen des Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:'
ms.openlocfilehash: 005c2e2e63668b7c17ee04d49de88811649fe914
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297737"
---
# <a name="add-server"></a><span data-ttu-id="59bc2-103">Hinzufügen des Servers</span><span class="sxs-lookup"><span data-stu-id="59bc2-103">Add Server</span></span>
 
<span data-ttu-id="59bc2-104">So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:</span><span class="sxs-lookup"><span data-stu-id="59bc2-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="59bc2-105">Enterprise Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="59bc2-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="59bc2-106">Director-Server</span><span class="sxs-lookup"><span data-stu-id="59bc2-106">Director server</span></span>
    
- <span data-ttu-id="59bc2-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="59bc2-107">Mediation Server</span></span>
    
- <span data-ttu-id="59bc2-108">Audio/Video Konferenz Server</span><span class="sxs-lookup"><span data-stu-id="59bc2-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="59bc2-109">Vertrauenswürdiger Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="59bc2-109">Trusted Application server</span></span>
    
<span data-ttu-id="59bc2-110">Jeder der neuen Pool Server hat andere Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="59bc2-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="59bc2-111">Suchen Sie in den folgenden Abschnitten nach dem Typ des Servers, den Sie dem vorhandenen Pool hinzufügen, und geben Sie die angeforderten Informationen an, wie Sie für die einzelnen Servertypen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="59bc2-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="59bc2-112">Sie geben die angeforderten Informationen an, um den neuen Pool Server zu definieren.</span><span class="sxs-lookup"><span data-stu-id="59bc2-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="59bc2-113">**Enterprise Edition-Front-End-Server**</span><span class="sxs-lookup"><span data-stu-id="59bc2-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="59bc2-114">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Servers, wie er im DNS (Domain Name System) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59bc2-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="59bc2-115">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59bc2-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="59bc2-116">Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="59bc2-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="59bc2-117">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="59bc2-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="59bc2-118">Definieren Sie eine **PSTN-IP-Adresse** , wenn sich ein Vermittlungsserver auf dem Front-End-Server befindet.</span><span class="sxs-lookup"><span data-stu-id="59bc2-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="59bc2-119">Wählen Sie **IPv6 aktivieren** aus, um IPv6 für diesen Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="59bc2-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="59bc2-120">**Director-Server**</span><span class="sxs-lookup"><span data-stu-id="59bc2-120">**Director server**</span></span>
  
- <span data-ttu-id="59bc2-121">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59bc2-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="59bc2-122">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59bc2-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="59bc2-123">Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="59bc2-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="59bc2-124">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="59bc2-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="59bc2-125">**Vermittlungsserver**</span><span class="sxs-lookup"><span data-stu-id="59bc2-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="59bc2-126">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59bc2-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="59bc2-127">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59bc2-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="59bc2-128">Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server als primäre IP-Adresse eingeben und eine IP-Adresse für die IP-Adresse des öffentlich geschalteten Telefonnetzwerks (PSTN) eingeben.</span><span class="sxs-lookup"><span data-stu-id="59bc2-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="59bc2-129">Die eingegebenen IP-Adressen sind die einzige IP-Adresse, die auf die angegebenen Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="59bc2-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59bc2-130">Für den Vermittlungs Server ist die IP-Adresse, die für die primäre IP-Adresse und die PSTN-IP-Adresse eingegeben wurde, standardmäßig identisch.</span><span class="sxs-lookup"><span data-stu-id="59bc2-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="59bc2-131">Die IP-Adressen können separat definiert werden, wenn Sie dedizierte Netzwerkschnittstellen oder getrennte IP-Adressen auf derselben Netzwerkschnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="59bc2-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="59bc2-132">Wenn Sie über zwei Netzwerkschnittstellen verfügen, eine für die lokale Netzwerkverbindung und eine für die PSTN-Verbindung, müssen Sie unterschiedliche IP-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="59bc2-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="59bc2-133">**Audio/Video Konferenz Server**</span><span class="sxs-lookup"><span data-stu-id="59bc2-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="59bc2-134">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59bc2-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="59bc2-135">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59bc2-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="59bc2-136">Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="59bc2-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="59bc2-137">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="59bc2-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="59bc2-138">**Vertrauenswürdiger Anwendungsserver**</span><span class="sxs-lookup"><span data-stu-id="59bc2-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="59bc2-139">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59bc2-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

