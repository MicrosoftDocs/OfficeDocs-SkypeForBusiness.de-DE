---
title: Hinzufügen der NAT-IP-Adresse des Edgeservers
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
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: Die öffentliche IP-Adresse ist die IP-Adresse, die von NAT (Netzwerkadressübersetzung) verwendet wird. Die IP-Adresse muss öffentlich geroutet werden. Dies ist erforderlich, da Sie auf der Seite "Features auswählen" des Assistenten die Option "externe IP-Adresse dieses Edge-Pools wird durch NAT übersetzt" ausgewählt haben.
ms.openlocfilehash: 11eb5bc16b4fd162dac15eede978cbbf940d9d42
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821007"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="5663e-105">Hinzufügen der NAT-IP-Adresse des Edgeservers</span><span class="sxs-lookup"><span data-stu-id="5663e-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="5663e-106">Die öffentliche IP-Adresse ist die IP-Adresse, die von NAT (Netzwerkadressübersetzung) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5663e-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="5663e-107">Die IP-Adresse muss öffentlich geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="5663e-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="5663e-108">Dies ist erforderlich, da Sie auf der Seite **"Features auswählen** " des Assistenten die Option " **externe IP-Adresse dieses Edge-Pools wird durch NAT übersetzt** " ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="5663e-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="5663e-109">Netzwerkadressübersetzung (Network Address Translation, NAT) ermöglicht Clients oder Servern in einem privaten Netzwerk (beispielsweise dem 192.168.0.0-Bereich), mit Systemen in Remotenetzwerken über die öffentlichen Internet Netzwerke zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="5663e-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="5663e-110">NAT funktioniert mithilfe einer einzelnen öffentlichen IP-Adresse auf einer externen Schnittstelle und dem zuordnen interner IP-Adressen zu einer öffentlichen IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5663e-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="5663e-111">Bei der NAT-Zuordnung wird der externen öffentlichen IP-Adresse eine interne Adresse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5663e-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="5663e-112">Das Remote System sieht nur die öffentliche Adresse der Quelle.</span><span class="sxs-lookup"><span data-stu-id="5663e-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="5663e-113">Das Remote System reagiert auf die Quelle, und die Quelle verweist auf die NAT-Zuordnung, um zu ermitteln, an welche interne IP-Adresse die Antwort zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5663e-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="5663e-p104">Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern zu einer vorhandenen Topologie finden Sie in der Edgeserver-Bereitstellungsdokumentation unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="5663e-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


