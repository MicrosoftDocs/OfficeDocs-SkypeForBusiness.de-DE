---
title: Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Mithilfe dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) für den Edge-Server angeben.
ms.openlocfilehash: 1ec24b1c85b429cf5308eb7e521c7ca4d7d295dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886522"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="0c9b1-103">Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010</span><span class="sxs-lookup"><span data-stu-id="0c9b1-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="0c9b1-104">Mithilfe dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) für den Edge-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="0c9b1-105">Geben Sie im Feld **interne IPv4-Adresse**die IP-Adresse des Edgeservers, den Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="0c9b1-106">Geben Sie Sie in **Interner FQDN**den vollqualifizierten Domänennamen (FQDN) des Edgeservers, den Sie dem Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="0c9b1-107">Der FQDN, die Sie angeben, muss mit den Namen des Computers identisch sein, die auf dem Server konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="0c9b1-108">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="0c9b1-109">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="0c9b1-110">Daher müssen Sie ein Suffix Domain Name System (DNS) konfigurieren, auf den Namen des Computers, der als ein Edge-Server bereitgestellt werden, die nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="0c9b1-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0c9b1-111">Weitere Informationen zum Hinzufügen einer DNS-Suffix an einen Computernamen finden Sie unter [Konfigurieren von DNS für die Edgeunterstützung](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c9b1-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


