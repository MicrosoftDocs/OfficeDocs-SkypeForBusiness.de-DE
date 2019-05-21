---
title: Definieren des FQDN für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Sie erstellen einen neuen beständigen Chat Server oder einen beständigen Chat Serverpool mit dem Assistenten zum Definieren des neuen beständigen Chat Pools. Wählen Sie entweder die Option Pool mit mehreren Computern oder Pool mit einem Computer. Wenn Sie einen Pool mit einem Computer wählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305872"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="f0132-105">Definieren des FQDN für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="f0132-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="f0132-106">Sie erstellen einen neuen beständigen Chat Server oder einen beständigen Chat Serverpool mit dem Assistenten zum **Definieren des neuen beständigen Chat Pools** .</span><span class="sxs-lookup"><span data-stu-id="f0132-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="f0132-107">Wählen Sie entweder die Option **Pool mit mehreren Computern** oder **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="f0132-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="f0132-108">Wenn Sie einen Pool mit einem Computer wählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.</span><span class="sxs-lookup"><span data-stu-id="f0132-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="f0132-109">Darüber hinaus müssen Sie einen **Pool-FQDN** für den Serverpool für beständigen Chat oder persistenten Chat definieren.</span><span class="sxs-lookup"><span data-stu-id="f0132-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="f0132-110">Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) für einen einzelnen Computerpool muss mit dem FQDN des Computers identisch sein, auf dem sich der Pool des einzelnen Servers befindet.</span><span class="sxs-lookup"><span data-stu-id="f0132-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="f0132-111">Bei einem Pool mit mehreren Computern muss der FQDN der Name sein, den Sie zum darstellen dieses Pools mit mehreren Computern auswählen und der in DNS von einem Host a (und AAAA, wenn IPv6 verwendet wird) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0132-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0132-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0132-112">See also</span></span>

[<span data-ttu-id="f0132-113">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f0132-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="f0132-114">Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie</span><span class="sxs-lookup"><span data-stu-id="f0132-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
