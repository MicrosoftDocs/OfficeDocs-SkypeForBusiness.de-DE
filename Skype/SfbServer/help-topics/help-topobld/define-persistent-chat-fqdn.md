---
title: Definieren des FQDN für beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Sie erstellen einen neuen Persistent Chat Server oder Persistent Chat Server Pool mit dem Assistenten Definieren neuer Pool für beständigen Chat. Wählen Sie einen Pool mit mehreren Computern oder einen Pool mit einem Computer. Wenn Sie einen Pool mit einem Computer wählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
ms.openlocfilehash: b4fbeb54c926573e908b361e7556fab9d87da848
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="624ad-105">Definieren des FQDN für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="624ad-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="624ad-106">Sie erstellen einen neuen Persistent Chat Server oder Persistent Chat Server Pool mit dem Assistenten **Definieren neuer Pool für beständigen Chat** .</span><span class="sxs-lookup"><span data-stu-id="624ad-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="624ad-107">Wählen Sie entweder die Option **Pool mit mehreren Computern** oder **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="624ad-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="624ad-108">Wenn Sie einen Pool mit einem Computer wählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.</span><span class="sxs-lookup"><span data-stu-id="624ad-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="624ad-109">Sie müssen auch einen **Pool-FQDN** für den beständigen Chat-Server oder Persistent Chat Server Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="624ad-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="624ad-110">Der Pool vollqualifizierten Domänennamen (FQDN) für einen Pool mit einem Computer muss identisch mit den FQDN des Computers, der die einzelnen Serverpool bildet.</span><span class="sxs-lookup"><span data-stu-id="624ad-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="624ad-111">Für einen Pool mit mehreren Computern muss der vollqualifizierte Domänenname den Namen auswählen, die in diesem Pool mit mehreren Computern darstellen und wird vom Host A (und AAAA Wenn IPv6 verwendet wird) in DNS definiert Datensatz.</span><span class="sxs-lookup"><span data-stu-id="624ad-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="624ad-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="624ad-112">See also</span></span>

#### 

[<span data-ttu-id="624ad-113">Planen Sie für Persistent Chatserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="624ad-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="624ad-114">Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="624ad-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

