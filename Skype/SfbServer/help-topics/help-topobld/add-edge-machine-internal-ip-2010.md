---
title: Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) des Edgeservers angeben.
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219377"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="54543-103">Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010</span><span class="sxs-lookup"><span data-stu-id="54543-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="54543-104">Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) des Edgeservers angeben.</span><span class="sxs-lookup"><span data-stu-id="54543-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="54543-105">Geben Sie unter **interne IPv4-Adresse**die IP-Adresse des Edgeserver ein, den Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="54543-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="54543-106">Geben Sie unter **Interner FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver ein, den Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="54543-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="54543-107">Der angegebene FQDN muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="54543-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="54543-108">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="54543-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="54543-109">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="54543-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="54543-110">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="54543-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="54543-111">Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span><span class="sxs-lookup"><span data-stu-id="54543-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


