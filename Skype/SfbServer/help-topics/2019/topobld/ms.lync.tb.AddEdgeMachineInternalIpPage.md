---
title: Hinzufügen der internen IP-Adresse zum Edgecomputer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Edgeserver angeben.
ms.openlocfilehash: fba327a08d8998056c42a39190fd8b3bf44ff08b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798242"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="7fd15-103">Hinzufügen der internen IP-Adresse zum Edgecomputer</span><span class="sxs-lookup"><span data-stu-id="7fd15-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="7fd15-104">Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Edgeserver angeben.</span><span class="sxs-lookup"><span data-stu-id="7fd15-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="7fd15-105">Der von Ihnen angegebene FQDN muss mit dem auf dem Server konfigurierten Computernamen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7fd15-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="7fd15-106">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="7fd15-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7fd15-107">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="7fd15-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7fd15-108">Daher müssen Sie ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll, der nicht zu einer Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="7fd15-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7fd15-109">Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter [Konfigurieren von DNS für Edge-Unterstützung](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7fd15-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


