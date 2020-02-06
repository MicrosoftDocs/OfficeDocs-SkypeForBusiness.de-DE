---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität steht nicht mehr zur Verfügung #a0 in Skype for Business Server 2019 veraltet. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, kann dies in der coexitence-Umgebung mit Legacy Version (Skype for Business Server 2015/lync Server 2013) genutzt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird.'
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813433"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="614b3-106">Migrieren eines XMPP-Partnerverbunds</span><span class="sxs-lookup"><span data-stu-id="614b3-106">Migrating XMPP federation</span></span>

<span data-ttu-id="614b3-107">In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="614b3-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="614b3-108">Die XMPP-Funktionalität steht nicht mehr zur Verfügung und ist in Skype for Business Server 2019 veraltet.</span><span class="sxs-lookup"><span data-stu-id="614b3-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="614b3-109">Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können Sie dies in einer Koexistenz-Umgebung mit einer Legacy Version (Skype for Business Server 2015 oder lync Server 2013) tun.</span><span class="sxs-lookup"><span data-stu-id="614b3-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="614b3-110">Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="614b3-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="614b3-111">Aus Migrations Sicht sollten Benutzer, die das XMPP-Feature in Anspruch nehmen möchten, auf dem Legacy Server verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, sondern weiterhin das Legacy-XMPP-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="614b3-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="614b3-112">Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder lync Server 2013 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="614b3-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="614b3-113">Wenn Sie die XMPP-Funktionalität fortsetzen möchten, sollten Sie den Legacy Edge-Server nicht zu Skype for Business Server 2019 migrieren.</span><span class="sxs-lookup"><span data-stu-id="614b3-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="614b3-114">Sie können jedoch die Koexistenz des Legacy-Edgeserver (mit XMPP-Proxy) und des Skype for Business 2019-Edgeserver aufweisen.</span><span class="sxs-lookup"><span data-stu-id="614b3-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

