---
title: Hinzufügen der Edgeserveroptionen für Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Sie definieren einen neuen Edgeserver oder Edge-Pool und bieten die Möglichkeit, Features für den neuen Server oder Pool zu definieren. Die Optionen, die Sie auswählen können, sind:'
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820987"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="09fe7-104">Hinzufügen der Edgeserveroptionen für Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="09fe7-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="09fe7-105">Sie definieren einen neuen Edgeserver oder Edge-Pool und bieten die Möglichkeit, Features für den neuen Server oder Pool zu definieren.</span><span class="sxs-lookup"><span data-stu-id="09fe7-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="09fe7-106">Die Optionen, die Sie auswählen können, sind:</span><span class="sxs-lookup"><span data-stu-id="09fe7-106">The options that you can choose are:</span></span>

- <span data-ttu-id="09fe7-107">**Verwenden eines einzelnen FQDN und einer IP-Adresse**: Aktivieren Sie das Kontrollkästchen, um ein einzelnes IPv4 oder IPv6 zu verwenden (wenn Sie sowohl IPv4 als auch IPv6 verwenden, müssen Sie einen der einzelnen IP-Adresstypen) und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die Schnittstellen für externe Edge definieren.</span><span class="sxs-lookup"><span data-stu-id="09fe7-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="09fe7-108">Wenn Sie diese Option auswählen, verwenden Sie nur eine IP-Adresse oder eine IPv4-und eine IPv6-Adresse, aber Sie müssen jeder Edge-Schnittstelle unterschiedliche Portnummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="09fe7-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="09fe7-109">**Föderation aktivieren (Port 5061)**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie mit anderen SIP-Föderationen, Anbietern oder gehosteten angeboten zusammen kommen, die das Session Initiation Protocol (SIP) verwenden.</span><span class="sxs-lookup"><span data-stu-id="09fe7-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="09fe7-110">**Die externe IP-Adresse dieses Edge-Pools wird von NAT übersetzt**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie private IP-Adressen für die externen Edge-Schnittstellen verwenden und ein NAT-Gerät (Network Address Translation) bereitstellen, um den Edgeserver oder den Edge-Pool logisch dahinter zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="09fe7-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="09fe7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09fe7-111">See also</span></span>

[<span data-ttu-id="09fe7-112">Planen des Zugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="09fe7-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="09fe7-113">Bereitstellen des Zugriffs externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="09fe7-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
