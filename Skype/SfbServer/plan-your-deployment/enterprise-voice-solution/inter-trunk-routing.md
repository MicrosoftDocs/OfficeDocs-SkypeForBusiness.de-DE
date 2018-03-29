---
title: Routing zwischen Trunks in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="45d72-103">Routing zwischen Trunks in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45d72-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45d72-104">Hier erfahren Sie, wie routing zwischen Trunks Skype für Business Server Enterprise-VoIP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45d72-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="45d72-105">Skype für Business Server bietet grundlegende sitzungsverwaltung über die Unterstützung von intertrunk-routing.</span><span class="sxs-lookup"><span data-stu-id="45d72-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="45d72-106">Auf diese Weise können Skype für Business Server downstream Telefoniesystemen Anruf Steuerelement Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="45d72-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="45d72-107">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="45d72-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="45d72-108">In ähnlicher Weise kann Skype für Business Server mindestens zwei IP-PBX-Systemen interconnect, damit Anrufe aus den unterschiedlichen IP-PBX-Systemen PBX-Telefone zwischen und platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="45d72-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="45d72-109">Die folgende Abbildung zeigt Skype für Business Server zunehmende Verbindung untereinander zwischen einem PSTN-Gateway und IP-Nebenstellenanlage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="45d72-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="45d72-111">Die folgende Abbildung veranschaulicht Skype für Business Server zwei IP-PBX-Systeme anschließen.</span><span class="sxs-lookup"><span data-stu-id="45d72-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](../../media/inter_trunk02.jpg)
  

