---
title: Migrieren von XMPP-Verbund
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'In früheren Versionen wurde ein extensible messaging und Anwesenheit Protocol (XMPP)-Gateways, die als eine separate Serverrolle zum Erstellen eines Verbunds mit XMPP-Bereitstellungen zulassen bereitgestellt werden konnte. Die XMPP-Funktionalität ist nicht mehr verfügbar und veraltete in Skype für Business Server 2019. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können werden er besitzt, unterstellt in Coexitence-Umgebung mit Legacyversion (Skype für Business Server 2015 / Lync Server 2013). XMPP-Funktionalität in zwei Teile installiert ist: als eine XMPP-Proxy, der auf die Legacy Edge-Server und des XMPP-Gateways, die ausgeführt wird ausgeführt wird, auf dem Front-End-Legacyserver.'
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029867"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="8fe0c-106">Migrieren von XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="8fe0c-106">Migrating XMPP federation</span></span>

<span data-ttu-id="8fe0c-107">In früheren Versionen wurde ein extensible messaging und Anwesenheit Protocol (XMPP)-Gateways, die als eine separate Serverrolle zum Erstellen eines Verbunds mit XMPP-Bereitstellungen zulassen bereitgestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8fe0c-108">Die XMPP-Funktionalität ist nicht mehr verfügbar und ist in Skype für Business Server 2019 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="8fe0c-109">Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können in einer Umgebung mit einer älteren Version (Skype für Business Server 2015 oder Lync Server 2013) möchten.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="8fe0c-110">XMPP-Funktionalität in zwei Teile installiert ist: als eine XMPP-Proxy, der auf die Legacy Edge-Server und des XMPP-Gateways, die ausgeführt wird ausgeführt wird, auf dem Front-End-Legacyserver.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="8fe0c-111">Migration bestehen Benutzer, die die XMPP-Funktion nutzen möchten sollten verbleiben in der Legacyserver und sollte nicht in einer Skype für Business Server 2019 Pool verschoben werden jedoch weiterhin ältere XMPP-Gateway verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="8fe0c-112">Dies ist möglich, nur, wenn der XMPP-Verbundpartner in Skype für Business Server 2015 oder Lync Server 2013 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="8fe0c-113">Sie sollten nicht Edgeserver der Vorversion zu Skype für Business Server 2019 migrieren, wenn Sie XMPP-Funktionalität fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="8fe0c-114">Sie können jedoch Koexistenz von Edgeserver der Vorversion (mit XMPP-Proxy) und die Skype für Business 2019 Edge-Server haben.</span><span class="sxs-lookup"><span data-stu-id="8fe0c-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

