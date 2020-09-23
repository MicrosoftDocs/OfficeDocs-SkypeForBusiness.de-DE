---
title: Definieren des FQDN für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Sie erstellen einen neuen Serverpool für beständigen Chat oder beständigen Chat mit dem Assistenten neuen Pool für beständigen Chat definieren. Wählen Sie entweder die Option Pool mit mehreren Computern oder Pool mit einem Computer. Wenn Sie einen Pool mit einem einzelnen Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool für einen einzelnen Computer entfernen und dann einen Pool mit mehreren Computern definieren.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217550"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="0672c-105">Definieren des FQDN für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="0672c-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="0672c-106">Sie erstellen einen neuen Serverpool für beständigen Chat oder beständigen Chat mit dem Assistenten **neuen Pool für beständigen Chat definieren** .</span><span class="sxs-lookup"><span data-stu-id="0672c-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="0672c-107">Wählen Sie entweder die Option **Pool mit mehreren Computern** oder **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="0672c-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="0672c-108">Wenn Sie einen Pool mit einem einzelnen Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool für einen einzelnen Computer entfernen und dann einen Pool mit mehreren Computern definieren.</span><span class="sxs-lookup"><span data-stu-id="0672c-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="0672c-109">Sie müssen auch einen **Pool-FQDN** für den Serverpool für beständigen Chat oder den Pool für beständigen Chat definieren.</span><span class="sxs-lookup"><span data-stu-id="0672c-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="0672c-110">Der vollqualifizierte Domänenname (FQDN) für einen Pool mit einem einzelnen Computer muss mit dem FQDN des Computers identisch sein, der den Pool mit einem einzelnen Server bildet.</span><span class="sxs-lookup"><span data-stu-id="0672c-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="0672c-111">Für einen Pool mit mehreren Computern muss der FQDN der Name sein, den Sie für die Darstellung dieses Pools mit mehreren Computern auswählen und der in DNS von einem Host a (und AAAA, wenn IPv6 verwendet wird) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0672c-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0672c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0672c-112">See also</span></span>

[<span data-ttu-id="0672c-113">Planen des Servers für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0672c-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0672c-114">Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="0672c-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
