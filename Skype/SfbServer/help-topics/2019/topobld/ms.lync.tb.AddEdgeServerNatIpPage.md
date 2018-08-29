---
title: Hinzufügen von Edge-Server-NAT-IP-
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: Die öffentliche IP-Adresse ist die IP-Adresse, die von der Netzwerkadressübersetzung (NAT) verwendet wird. Die IP-Adresse muss öffentlich routingfähig sein. Dies ist erforderlich, da Sie die externe IP-Adresse für diese Kante ausgewählt haben, den Pool von NAT-Option auf der Seite Select Features dieses Assistenten übersetzt wird.
ms.openlocfilehash: 94146cf7d6b8f77a79ae5c7f4cacbf3fb03677dc
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23254172"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="dd182-105">Hinzufügen von Edge-Server-NAT-IP-</span><span class="sxs-lookup"><span data-stu-id="dd182-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="dd182-106">Die öffentliche IP-Adresse ist die IP-Adresse, die von der Netzwerkadressübersetzung (NAT) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dd182-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="dd182-107">Die IP-Adresse muss öffentlich routingfähig sein.</span><span class="sxs-lookup"><span data-stu-id="dd182-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="dd182-108">Dies ist erforderlich, da Sie **die externe IP-Adresse für diesen edgepool wird von NAT übersetzt** Option auf der Seite **Features auswählen** des Assistenten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="dd182-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="dd182-109">Netzwerkadressübersetzung (NAT) ermöglicht es Clients oder Server in einem privaten Netzwerk (beispielsweise die 192.168.0.0 Bereich) über das öffentliche Internet-Netzwerke mit Systemen in remote-Netzwerken kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="dd182-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="dd182-110">NAT funktioniert, indem Sie eine einzelne öffentliche IP-Adresse für eine externe Schnittstelle verwenden und eine öffentliche IP-Adresse interne IP-Adressen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dd182-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="dd182-111">NAT-Zuordnung ordnet eine interne Adresse die externe öffentliche IP-Adresse zu.</span><span class="sxs-lookup"><span data-stu-id="dd182-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="dd182-112">Das Remotesystem erhält nur die öffentliche Adresse der Quelle.</span><span class="sxs-lookup"><span data-stu-id="dd182-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="dd182-113">Das Remotesystem reagiert auf die Datenquelle, und die Datenquelle bezieht sich auf die NAT-Zuordnung zu bestimmen, welche interne IP-Adresse, der die Antwort an zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd182-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="dd182-114">Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd182-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="dd182-115">Ausführliche Informationen zum Hinzufügen von Edge-Servern zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in der Dokumentation zur Bereitstellung der Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="dd182-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


