---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Ein Director ist ein Server mit Skype für Business Server Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten.
ms.openlocfilehash: 9ba73f88ba58abd25cdbd11b2efa5129b0322cfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889500"
---
# <a name="director-planning-tool"></a><span data-ttu-id="b8375-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="b8375-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="b8375-104">Ein Director ist ein Server mit Skype für Business Server Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="b8375-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="b8375-105">Diese Rolle ist optional, würde der Bereitstellung eines Directors in den folgenden zwei Szenarien werden sollen:</span><span class="sxs-lookup"><span data-stu-id="b8375-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="b8375-106">Wenn Sie Zugriff durch externe Benutzer durch die Bereitstellung von Edge-Server aktivieren, sollten Sie auch einen Director bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8375-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="b8375-107">In diesem Szenario der Director externe Benutzer authentifiziert und anschließend übergibt den Datenverkehr an interne Server.</span><span class="sxs-lookup"><span data-stu-id="b8375-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="b8375-108">Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet es Front-End-Poolserver der Aufwand für das Ausführen der Authentifizierung von romotebenutzern einhergeht.</span><span class="sxs-lookup"><span data-stu-id="b8375-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="b8375-109">Darüber hinaus werden interne Front-End-Pools bösartigem Datenverkehr wie Denial-of-Service-Angriffen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="b8375-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="b8375-110">Wenn das Netzwerk mit ungültigen externen Datenverkehr in einem solchen Angriff bereits ist, endet dieser Datenverkehr den Director.</span><span class="sxs-lookup"><span data-stu-id="b8375-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="b8375-111">Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, durch Hinzufügen eines Directors in dieser Website können Authentifizierungsanfragen optimieren und die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="b8375-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="b8375-112">In diesem Szenario werden alle Anforderungen ersten den Übermittler, die sie dann auf dem richtigen Front-End-Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="b8375-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

