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
- NOCSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:'
ms.openlocfilehash: d4f4afc0d4a7cb6fafe47de95c648aa1769027e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820647"
---
# <a name="add-server"></a><span data-ttu-id="d74f6-103">Hinzufügen des Servers</span><span class="sxs-lookup"><span data-stu-id="d74f6-103">Add Server</span></span>
 
<span data-ttu-id="d74f6-104">So fügen Sie einen neuen Server zu einem vorhandenen Pool von Servern hinzu, wobei es sich um einen der folgenden Pools handelt:</span><span class="sxs-lookup"><span data-stu-id="d74f6-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="d74f6-105">Enterprise Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="d74f6-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="d74f6-106">Director-Server</span><span class="sxs-lookup"><span data-stu-id="d74f6-106">Director server</span></span>
    
- <span data-ttu-id="d74f6-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="d74f6-107">Mediation Server</span></span>
    
- <span data-ttu-id="d74f6-108">Audio/Video Konferenz Server</span><span class="sxs-lookup"><span data-stu-id="d74f6-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="d74f6-109">Vertrauenswürdiger Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="d74f6-109">Trusted Application server</span></span>
    
<span data-ttu-id="d74f6-110">Jeder der neuen Pool Server hat andere Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d74f6-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="d74f6-111">Suchen Sie in den folgenden Abschnitten nach dem Typ des Servers, den Sie dem vorhandenen Pool hinzufügen, und geben Sie die angeforderten Informationen an, wie Sie für die einzelnen Servertypen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d74f6-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="d74f6-112">Sie geben die angeforderten Informationen an, um den neuen Pool Server zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d74f6-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="d74f6-113">**Enterprise Edition-Front-End-Server**</span><span class="sxs-lookup"><span data-stu-id="d74f6-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="d74f6-114">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Servers, wie er im DNS (Domain Name System) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d74f6-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="d74f6-115">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d74f6-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d74f6-116">Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="d74f6-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d74f6-117">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="d74f6-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="d74f6-118">Definieren Sie eine **PSTN-IP-Adresse** , wenn sich ein Vermittlungsserver auf dem Front-End-Server befindet.</span><span class="sxs-lookup"><span data-stu-id="d74f6-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="d74f6-119">Wählen Sie **IPv6 aktivieren** aus, um IPv6 für diesen Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d74f6-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="d74f6-120">**Director-Server**</span><span class="sxs-lookup"><span data-stu-id="d74f6-120">**Director server**</span></span>
  
- <span data-ttu-id="d74f6-121">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d74f6-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d74f6-122">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d74f6-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="d74f6-123">Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="d74f6-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="d74f6-124">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="d74f6-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="d74f6-125">**Vermittlungsserver**</span><span class="sxs-lookup"><span data-stu-id="d74f6-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="d74f6-126">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d74f6-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d74f6-127">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d74f6-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d74f6-128">Sie können auch die Option **Dienstnutzung auf ausgewählte IP-Adressen einschränken** und eine bestimmte IP-Adresse auf dem neuen Server als primäre IP-Adresse eingeben und eine IP-Adresse für die IP-Adresse des öffentlich geschalteten Telefonnetzwerks (PSTN) eingeben.</span><span class="sxs-lookup"><span data-stu-id="d74f6-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="d74f6-129">Die eingegebenen IP-Adressen sind die einzige IP-Adresse, die auf die angegebenen Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="d74f6-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d74f6-130">Für den Vermittlungs Server ist die IP-Adresse, die für die primäre IP-Adresse und die PSTN-IP-Adresse eingegeben wurde, standardmäßig identisch.</span><span class="sxs-lookup"><span data-stu-id="d74f6-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="d74f6-131">Die IP-Adressen können separat definiert werden, wenn Sie dedizierte Netzwerkschnittstellen oder getrennte IP-Adressen auf derselben Netzwerkschnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="d74f6-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="d74f6-132">Wenn Sie über zwei Netzwerkschnittstellen verfügen, eine für die lokale Netzwerkverbindung und eine für die PSTN-Verbindung, müssen Sie unterschiedliche IP-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d74f6-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="d74f6-133">**Audio/Video Konferenz Server**</span><span class="sxs-lookup"><span data-stu-id="d74f6-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="d74f6-134">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d74f6-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d74f6-135">Wählen Sie **alle konfigurierten IP-Adressen verwenden**aus, was bedeutet, dass jede auf dem Computer definierte IP-Adresse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d74f6-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d74f6-136">Alternativ können Sie die Option **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** auswählen und eine bestimmte Adresse auf dem neuen Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="d74f6-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d74f6-137">Die eingegebene IP-Adresse ist die einzige IP-Adresse, die auf die gehosteten Dienste reagiert.</span><span class="sxs-lookup"><span data-stu-id="d74f6-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="d74f6-138">**Vertrauenswürdiger Anwendungsserver**</span><span class="sxs-lookup"><span data-stu-id="d74f6-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="d74f6-139">Der FQDN des neuen Servers, wie er in DNS definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d74f6-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

