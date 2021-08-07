---
title: Definieren des FQDN für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Sie erstellen einen neuen Pool für den Server für beständigen Chat oder den Serverpool für beständigen Chat mithilfe des Assistenten zum Definieren eines neuen Pools für beständigen Chat. Wählen Sie entweder die Option Pool mit mehreren Computern oder Pool mit einem Computer. Wenn Sie einen Pool mit einem Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
ms.openlocfilehash: 8c900574b84f2780bc3556242949bf7dce4e72b499acc53e514b1924b99ecabb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305457"
---
# <a name="define-persistent-chat-fqdn"></a>Definieren des FQDN für beständigen Chat
 
Sie erstellen einen neuen Pool für den Server für beständigen Chat oder den Serverpool für beständigen Chat mithilfe des Assistenten zum Definieren eines neuen Pools **für beständigen Chat.** Wählen Sie entweder die Option **Pool mit mehreren Computern** oder **Pool mit einem Computer**. Wenn Sie einen Pool mit einem Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
  
Sie müssen auch einen **Pool-FQDN** für den Server für beständigen Chat oder den Serverpool für beständigen Chat definieren. Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools für einen einzelnen Computer muss mit dem FQDN des Computers übereinstimmen, der den Einzelserverpool darstellt. Bei einem Pool mit mehreren Computern muss der FQDN der Name sein, den Sie auswählen, um diesen Pool mit mehreren Computern darzustellen, und wird in DNS durch einen Host-A-Eintrag (und AAAA, wenn IPv6 verwendet wird) definiert.
  
## <a name="see-also"></a>Siehe auch

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
