---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität ist nicht mehr verfügbar & veraltet in Skype for Business Server 2019. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, können Sie diese in der coexitence-Umgebung mit der Vorgängerversion (Skype for Business Server 2015/lync Server 2013) nutzen. Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy Front-End-Server ausgeführt wird.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752647"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="9da94-106">Migrieren eines XMPP-Partnerverbunds</span><span class="sxs-lookup"><span data-stu-id="9da94-106">Migrating XMPP federation</span></span>

<span data-ttu-id="9da94-107">In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9da94-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="9da94-108">Die XMPP-Funktionalität ist nicht mehr verfügbar und ist in Skype for Business Server 2019 veraltet.</span><span class="sxs-lookup"><span data-stu-id="9da94-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="9da94-109">Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, können Sie dies in einer Koexistenz-Umgebung mit einer älteren Version (Skype for Business Server 2015 oder lync Server 2013) tun.</span><span class="sxs-lookup"><span data-stu-id="9da94-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="9da94-110">Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy Front-End-Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9da94-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="9da94-111">Aus Migrations Sicht sollten Benutzer, die das XMPP-Feature in Anspruch nehmen möchten, auf dem vorversions Server verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, aber weiterhin das Legacy-XMPP-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="9da94-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="9da94-112">Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder lync Server 2013 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9da94-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="9da94-113">Sie sollten die Legacy Edgeserver nicht auf Skype for Business Server 2019 migrieren, wenn Sie mit der XMPP-Funktionalität fortfahren möchten.</span><span class="sxs-lookup"><span data-stu-id="9da94-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="9da94-114">Sie können jedoch eine Koexistenz der Legacy Edgeserver (mit XMPP-Proxy) und der Skype for Business 2019 Edgeserver haben.</span><span class="sxs-lookup"><span data-stu-id="9da94-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

