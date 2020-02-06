---
title: Hinzufügen der IP-Adresse des Edgeservers – Optionen
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
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Mit Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für den Edge-Server und den Edge-Pool konfigurieren. Gehen Sie dazu wie folgt vor:'
ms.openlocfilehash: 7dd3766bf88dee6e59fb890925cd9f73c23ceab6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821027"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="b712c-104">Hinzufügen der IP-Adresse des Edgeservers – Optionen</span><span class="sxs-lookup"><span data-stu-id="b712c-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="b712c-105">Mit Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für den Edge-Server und den Edge-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b712c-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="b712c-106">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b712c-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="b712c-107">**Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b712c-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="b712c-108">**Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b712c-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="b712c-109">**Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b712c-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="b712c-110">**Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b712c-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="b712c-111">Sie können auch den Edgeserver oder den Edge-Pool so konfigurieren, dass für die externen IP-Adressen eine Adresse für die Netzwerkadressübersetzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b712c-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="b712c-112">Aktivieren Sie dazu das Kontrollkästchen, um **die externe IP-Adresse dieses Edge-Pools von NAT zu übersetzen**.</span><span class="sxs-lookup"><span data-stu-id="b712c-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="b712c-113">NAT-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="b712c-113">NAT support.</span></span> <span data-ttu-id="b712c-114">Netzwerkadressübersetzung (Network Address Translation, NAT) wird nicht unterstützt, wenn Sie den Hardwarelastenausgleich verwenden, wählen Sie daher die Option NAT nicht aus, wenn Sie einen Edgeserver-Pool mit Hardwarelastenausgleich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b712c-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

