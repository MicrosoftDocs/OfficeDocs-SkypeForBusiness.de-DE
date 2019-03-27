---
title: Routing zwischen Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892660"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="8e097-103">Routing zwischen Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8e097-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="8e097-104">Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8e097-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="8e097-105">Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing.</span><span class="sxs-lookup"><span data-stu-id="8e097-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="8e097-106">Auf diese Weise können Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8e097-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="8e097-107">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="8e097-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="8e097-108">In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="8e097-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="8e097-109">Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8e097-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="8e097-111">Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.</span><span class="sxs-lookup"><span data-stu-id="8e097-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

