---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Ein Director ist ein Server, auf dem die Skype for Business Server 2015-Kommunikationssoftware ausgeführt wird, die Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten aufweist.
ms.openlocfilehash: 48b691262dc638faf6f0aa9910a5adac3c1f0e46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684248"
---
# <a name="director-planning-tool"></a><span data-ttu-id="da54a-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="da54a-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="da54a-104">Ein Director ist ein Server, auf dem die Skype for Business Server 2015-Kommunikationssoftware ausgeführt wird, die Benutzeranforderungen authentifizieren kann, aber keine Benutzerkonten aufweist.</span><span class="sxs-lookup"><span data-stu-id="da54a-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="da54a-105">Diese Rolle ist optional, wenn Sie einen Director in den beiden folgenden Szenarien bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="da54a-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="da54a-106">Wenn Sie den Zugriff von externen Benutzern durch die Bereitstellung von Edge-Servern aktivieren, sollten Sie auch einen Director bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="da54a-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="da54a-107">In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann den Datenverkehr an interne Server.</span><span class="sxs-lookup"><span data-stu-id="da54a-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="da54a-108">Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet es Front-End-Pool Server vor dem mehr Aufwand bei der Authentifizierung dieser Benutzer.</span><span class="sxs-lookup"><span data-stu-id="da54a-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="da54a-109">Darüber hinaus können Sie interne Front-End-Pools vor böswilligem Datenverkehr wie Denial-of-Service-Angriffen isolieren.</span><span class="sxs-lookup"><span data-stu-id="da54a-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="da54a-110">Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.</span><span class="sxs-lookup"><span data-stu-id="da54a-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="da54a-111">Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, indem Sie dieser Website einen Director hinzufügen, können Sie Authentifizierungsanforderungen rationalisieren und die Leistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="da54a-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="da54a-112">In diesem Szenario gehen alle Anforderungen zuerst an den Director, der Sie dann an den richtigen Front-End-Pool weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="da54a-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

