---
title: Zwischen trunk-Routing in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816965"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="75228-103">Zwischen trunk-Routing in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="75228-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="75228-104">Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing.</span><span class="sxs-lookup"><span data-stu-id="75228-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="75228-105">Diese Funktion ermöglicht Skype for Business Server die Bereitstellung von Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme.</span><span class="sxs-lookup"><span data-stu-id="75228-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="75228-106">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="75228-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="75228-107">Ebenso kann Skype for Business Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="75228-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="75228-108">Die folgende Abbildung zeigt die Verbindung zwischen einem PSTN-Gateway und einer IP-Telefonanlage mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="75228-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interkonnektivität zwischen einem PSTN-Gateway und einer IP-Telefonanlage](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="75228-110">Die nächste Abbildung zeigt den Skype for Business-Server, der zwei IP-PBX-Systeme verbindet.</span><span class="sxs-lookup"><span data-stu-id="75228-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype for Business-Server, der zwei IP-PGX-Systeme verbindet](../../media/two-ip-pbx-systems.jpg)

