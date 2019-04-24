---
title: Routing zwischen Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing. '
ms.openlocfilehash: 9f73899d59e79d8fc93e768f0e870449baaeb7fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214800"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="bdd98-103">Routing zwischen Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="bdd98-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="bdd98-104">Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing.</span><span class="sxs-lookup"><span data-stu-id="bdd98-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="bdd98-105">Diese Funktion ermöglicht Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bdd98-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="bdd98-106">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="bdd98-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="bdd98-107">In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="bdd98-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="bdd98-108">Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bdd98-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="bdd98-110">Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.</span><span class="sxs-lookup"><span data-stu-id="bdd98-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype für Business Server zwei IP-PGX Systeme](../../media/two-ip-pbx-systems.jpg)

