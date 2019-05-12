---
title: Hinzufügen des Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Zum Hinzufügen eines neuen Servers zu einem vorhandenen Pool von Servern, eine der folgenden pooltypen:'
ms.openlocfilehash: 4ec03d28f71dffbeaa4b06594bd634e80e522665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897324"
---
# <a name="add-server"></a><span data-ttu-id="4e03a-103">Hinzufügen des Servers</span><span class="sxs-lookup"><span data-stu-id="4e03a-103">Add Server</span></span>
 
<span data-ttu-id="4e03a-104">Zum Hinzufügen eines neuen Servers zu einem vorhandenen Pool von Servern, eine der folgenden pooltypen:</span><span class="sxs-lookup"><span data-stu-id="4e03a-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="4e03a-105">Enterprise Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="4e03a-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="4e03a-106">Director-server</span><span class="sxs-lookup"><span data-stu-id="4e03a-106">Director server</span></span>
    
- <span data-ttu-id="4e03a-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="4e03a-107">Mediation Server</span></span>
    
- <span data-ttu-id="4e03a-108">A/v-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="4e03a-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="4e03a-109">Vertrauenswürdiger Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="4e03a-109">Trusted Application server</span></span>
    
<span data-ttu-id="4e03a-110">Jede der neuen Poolserver verfügt über verschiedene Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4e03a-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="4e03a-111">Legen Sie in den folgenden Abschnitten die Server, auf dem Sie den vorhandenen Pool hinzufügen möchten, und geben Sie die Informationen für jeden Servertyp definierten angefordert.</span><span class="sxs-lookup"><span data-stu-id="4e03a-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="4e03a-112">Sie bieten die angeforderte Informationen, um den neuen Poolserver definieren.</span><span class="sxs-lookup"><span data-stu-id="4e03a-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="4e03a-113">**Enterprise Edition-Front-End-Server**</span><span class="sxs-lookup"><span data-stu-id="4e03a-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="4e03a-114">Vollqualifizierter Domänenname (FQDN) des neuen Servers wie er im Domain Name System (DNS) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4e03a-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="4e03a-115">Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e03a-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="4e03a-116">Alternativ können Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** auswählen und geben Sie eine bestimmte Adresse auf dem neuen Server.</span><span class="sxs-lookup"><span data-stu-id="4e03a-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="4e03a-117">IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.</span><span class="sxs-lookup"><span data-stu-id="4e03a-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="4e03a-118">Definieren Sie eine **PSTN-IP-Adresse** aus, wenn Sie einen Vermittlungsserver auf dem Front-End-Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4e03a-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="4e03a-119">Wählen Sie **IPv6 aktivieren,** um IPv6 für diesen Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e03a-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="4e03a-120">**Director-server**</span><span class="sxs-lookup"><span data-stu-id="4e03a-120">**Director server**</span></span>
  
- <span data-ttu-id="4e03a-121">DNS-der FQDN des neuen Servers gemäß Definition.</span><span class="sxs-lookup"><span data-stu-id="4e03a-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4e03a-122">Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e03a-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="4e03a-123">Alternativ wählen Sie die **Verwendung von Grenzwert ausgewählten IP-Adressen** und geben Sie eine bestimmte IP-Adresse auf dem neuen Server.</span><span class="sxs-lookup"><span data-stu-id="4e03a-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="4e03a-124">IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.</span><span class="sxs-lookup"><span data-stu-id="4e03a-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="4e03a-125">**Vermittlungsserver**</span><span class="sxs-lookup"><span data-stu-id="4e03a-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="4e03a-126">DNS-der FQDN des neuen Servers gemäß Definition.</span><span class="sxs-lookup"><span data-stu-id="4e03a-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4e03a-127">Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e03a-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="4e03a-128">Alternativ wählen Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** und geben eine bestimmte IP-Adresse auf dem neuen Server als primäre IP-Adresse und ein Geben Sie eine IP-Adresse public switched Telephone Network, (PSTN) IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="4e03a-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="4e03a-129">Die IP-Adressen eingegeben werden die einzige IP-Adresse der für die festgelegten Dienste reagieren soll.</span><span class="sxs-lookup"><span data-stu-id="4e03a-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e03a-130">Für den Vermittlungsserver ist die IP-Adresse für die primäre IP-Adresse und die PSTN-IP-Adresse eingegeben standardmäßig identisch.</span><span class="sxs-lookup"><span data-stu-id="4e03a-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="4e03a-131">Die IP-Adressen können separat definiert werden, wenn Sie auf der gleichen Netzwerkschnittstelle dedizierten Netzwerkschnittstellen oder separate IP-Adressen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="4e03a-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="4e03a-132">Wenn Sie zwei Netzwerkschnittstellen, einen für die LAN-Verbindung und einen für die PSTN-Verbindung verfügen, müssen Sie unterschiedliche IP-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4e03a-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="4e03a-133">**A/v-Konferenzserver**</span><span class="sxs-lookup"><span data-stu-id="4e03a-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="4e03a-134">DNS-der FQDN des neuen Servers gemäß Definition.</span><span class="sxs-lookup"><span data-stu-id="4e03a-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="4e03a-135">Wählen Sie **Alle konfigurierte IP-Adressen verwenden**, was bedeutet, dass alle IP-Adressen auf dem Computer definierten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e03a-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="4e03a-136">Alternativ können Sie **Service-Verwendung einschränken ausgewählten IP-Adressen** auswählen und geben Sie eine bestimmte Adresse auf dem neuen Server.</span><span class="sxs-lookup"><span data-stu-id="4e03a-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="4e03a-137">IP-Adresse des ist die einzige IP-Adresse für gehostete Dienste reagieren soll.</span><span class="sxs-lookup"><span data-stu-id="4e03a-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="4e03a-138">**Vertrauenswürdiger Anwendungsserver**</span><span class="sxs-lookup"><span data-stu-id="4e03a-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="4e03a-139">DNS-der FQDN des neuen Servers gemäß Definition.</span><span class="sxs-lookup"><span data-stu-id="4e03a-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

