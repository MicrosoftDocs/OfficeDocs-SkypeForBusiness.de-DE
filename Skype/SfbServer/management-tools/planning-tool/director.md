---
title: Director (Planungstool)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Ein Director ist ein Server mit Skype für Business Server 2015 Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a><span data-ttu-id="c0b54-103">Director (Planungstool)</span><span class="sxs-lookup"><span data-stu-id="c0b54-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="c0b54-104">Ein Director ist ein Server mit Skype für Business Server 2015 Communications-Software, die Benutzeranfragen authentifizieren kann, jedoch ist kein Homeserver für alle Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="c0b54-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="c0b54-105">Diese Rolle ist optional, würde der Bereitstellung eines Directors in den folgenden zwei Szenarien werden sollen:</span><span class="sxs-lookup"><span data-stu-id="c0b54-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="c0b54-106">Wenn Sie Zugriff durch externe Benutzer durch die Bereitstellung von Edge-Server aktivieren, sollten Sie auch einen Director bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0b54-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="c0b54-107">In diesem Szenario der Director externe Benutzer authentifiziert und anschließend übergibt den Datenverkehr an interne Server.</span><span class="sxs-lookup"><span data-stu-id="c0b54-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="c0b54-108">Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet es Front-End-Poolserver der Aufwand für das Ausführen der Authentifizierung von romotebenutzern einhergeht.</span><span class="sxs-lookup"><span data-stu-id="c0b54-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="c0b54-109">Darüber hinaus werden interne Front-End-Pools bösartigem Datenverkehr wie Denial-of-Service-Angriffen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="c0b54-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="c0b54-110">Wenn das Netzwerk mit ungültigen externen Datenverkehr in einem solchen Angriff bereits ist, endet dieser Datenverkehr den Director.</span><span class="sxs-lookup"><span data-stu-id="c0b54-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="c0b54-111">Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, durch Hinzufügen eines Directors in dieser Website können Authentifizierungsanfragen optimieren und die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="c0b54-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="c0b54-112">In diesem Szenario werden alle Anforderungen ersten den Übermittler, die sie dann auf dem richtigen Front-End-Pool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c0b54-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

