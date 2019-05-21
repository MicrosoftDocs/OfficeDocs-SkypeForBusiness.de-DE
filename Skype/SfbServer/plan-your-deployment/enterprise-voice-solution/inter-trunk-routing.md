---
title: Zwischen trunk-Routing in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276831"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="3f2e7-103">Zwischen trunk-Routing in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f2e7-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="3f2e7-104">Erfahren Sie, wie Skype for Business Server Enterprise-VoIP das Routing zwischen Trunks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="3f2e7-105">Skype for Business Server bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="3f2e7-106">Auf diese Weise kann Skype for Business Server Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="3f2e7-107">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="3f2e7-108">Ebenso kann Skype for Business Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="3f2e7-109">Die folgende Abbildung zeigt die Verbindung zwischen einem PSTN-Gateway und einer IP-Telefonanlage mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="3f2e7-111">Die nächste Abbildung zeigt den Skype for Business-Server, der zwei IP-PBX-Systeme verbindet.</span><span class="sxs-lookup"><span data-stu-id="3f2e7-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

