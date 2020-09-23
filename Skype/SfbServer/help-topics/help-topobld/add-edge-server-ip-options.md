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
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für die Edgeserver und Edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219790"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="c9b36-104">Hinzufügen der IP-Adresse des Edgeservers – Optionen</span><span class="sxs-lookup"><span data-stu-id="c9b36-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="c9b36-105">Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für die Edgeserver und Edgepool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9b36-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="c9b36-106">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c9b36-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="c9b36-107">**IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9b36-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="c9b36-108">**IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9b36-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="c9b36-109">**IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9b36-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="c9b36-110">**IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c9b36-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="c9b36-111">Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9b36-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="c9b36-112">Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.</span><span class="sxs-lookup"><span data-stu-id="c9b36-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="c9b36-113">NAT-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="c9b36-113">NAT support.</span></span> <span data-ttu-id="c9b36-114">Die Netzwerkadressübersetzung (Network Address Translation, NAT) wird nicht unterstützt, wenn Sie einen Hardwarelastenausgleich verwenden, wählen Sie daher die Option NAT nicht aus, wenn Sie einen Edgeserver Pool mit Hardwarelastenausgleich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c9b36-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

