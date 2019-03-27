---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Geben Sie den vollqualifizierten Domänennamen (FQDN) des Front-End-Pools, die Sie erstellen. Sie können den FQDN eines Pools nach dem Veröffentlichen der Topologie mit den Front-End-Pool nicht ändern. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool zu löschen und fügen Sie einen neuen Pool mit dem neuen vollqualifizierten Domänennamen.
ms.openlocfilehash: 28e831df0cdf86620eefc1a22ced199507026c46
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884252"
---
# <a name="add-front-end-pool-fqdn"></a>Hinzufügen des FQDN des Front-End-Pools
 
Geben Sie den vollqualifizierten Domänennamen (FQDN) des Front-End-Pools, die Sie erstellen. Sie können den FQDN eines Pools nach dem Veröffentlichen der Topologie mit den Front-End-Pool nicht ändern. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool zu löschen und fügen Sie einen neuen Pool mit dem neuen vollqualifizierten Domänennamen.
  
> [!TIP]
> Wenn Sie einen Front-End-Pool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie später weitere Computer zum Pool hinzufügen möchten, führen Sie die Topologie-Generator erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und dann das neue Mitglied der Front-End-Pool über die Skype für Business Server-Bereitstellungsassistenten einrichten. Sie müssen auch den neuen Pool Member für die entsprechenden Lastenausgleich für den Pool, Domain Name System (DNS) zum Lastenausgleich oder Hardwaregerät zum Lastenausgleich hinzufügen. In vielen Fällen müssen Sie beide Systeme direkten-Lastenausgleich. Stellen Sie sicher, dass Sie sowohl den neue Mitgliedsserver hinzugefügt werden müssen. 
  

