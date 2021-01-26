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
description: Sie erstellen einen neuen Server für beständigen Chat oder einen Pool für den Server für beständigen Chat mit dem Assistenten zum Definieren eines neuen Pools für beständigen Chat. Wählen Sie entweder die Option Pool mit mehreren Computern oder Pool mit einem Computer. Wenn Sie einen Pool mit einem einzelnen Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818445"
---
# <a name="define-persistent-chat-fqdn"></a>Definieren des FQDN für beständigen Chat
 
Sie erstellen einen neuen Server für beständigen Chat oder einen pool für den Server für beständigen Chat mit dem Assistenten zum Definieren eines neuen Pools für **beständigen Chat.** Wählen Sie entweder die Option **Pool mit mehreren Computern** oder **Pool mit einem Computer**. Wenn Sie einen Pool mit einem einzelnen Computer auswählen und später einen Pool mit mehreren Computern benötigen, müssen Sie den Pool mit einem Computer entfernen und dann einen Pool mit mehreren Computern definieren.
  
Außerdem müssen Sie einen **Pool-FQDN für** den Server für beständigen Chat oder den Pool für den Server für beständigen Chat definieren. Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools für einen einzelnen Computer muss mit dem FQDN des Computers identisch sein, aus dem der Pool mit einem einzelnen Server ist. Bei einem Pool mit mehreren Computern muss der FQDN der Name sein, den Sie für diesen Pool mit mehreren Computern auswählen. Er wird in DNS durch einen Host-A-Eintrag (und AAAA, wenn IPv6 verwendet wird) definiert.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
