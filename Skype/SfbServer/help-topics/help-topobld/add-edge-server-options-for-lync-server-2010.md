---
title: Hinzufügen der Edgeserveroptionen für Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definieren Sie einen neuen Edge-Server oder einen Edge-Pool und die Möglichkeit, Features für den neuen Server oder Pool definieren angezeigt werden. Die Optionen, die Sie auswählen können, sind:'
ms.openlocfilehash: 57c3916b1a43812c1f647f425fc9df65f99cff35
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897458"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="f37b8-104">Hinzufügen der Edgeserveroptionen für Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f37b8-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="f37b8-105">Definieren Sie einen neuen Edge-Server oder einen Edge-Pool und die Möglichkeit, Features für den neuen Server oder Pool definieren angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f37b8-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="f37b8-106">Die Optionen, die Sie auswählen können, sind:</span><span class="sxs-lookup"><span data-stu-id="f37b8-106">The options that you can choose are:</span></span>

- <span data-ttu-id="f37b8-107">**Verwenden Sie eine einzelne FQDN und IP-Adresse**: Aktivieren Sie das Kontrollkästchen mit einer einzelnen IPv4 oder IPv6 (Wenn Sie sowohl IPv4 als auch IPv6 verwenden können, müssen Sie über die einzelnen IP-Adresse definieren) Adresse und den vollqualifizierten Domänennamen (FQDN) für die externe Edge-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="f37b8-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f37b8-108">Wenn Sie diese Option auswählen, verwenden Sie nur eine IP-Adresse oder eine IPv4- und IPv6 eine, jedoch müssen Sie jede edgeschnittstelle unterschiedliche Portnummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f37b8-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="f37b8-109">**Partnerverbund aktivieren (Port 5061)**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie einen Partnerverbund mit anderen SIP partnerverbunden, Anbietern oder gehosteten angeboten, die das Session Initiation Protocol (SIP) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f37b8-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="f37b8-110">**Die externe IP-Adresse für diesen edgepool wird von NAT übersetzt**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie private IP-Adressen für die externen edgeschnittstellen verwenden und werden ein Gerät Network Address Translation (NAT), zum Platzieren der Edge-Server oder logisch Edge-Pool bereitstellen hinter.</span><span class="sxs-lookup"><span data-stu-id="f37b8-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="f37b8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f37b8-111">See also</span></span>

[<span data-ttu-id="f37b8-112">Planen des Zugriffs externer Benutzer</span><span class="sxs-lookup"><span data-stu-id="f37b8-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="f37b8-113">Bereitstellen von Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="f37b8-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
