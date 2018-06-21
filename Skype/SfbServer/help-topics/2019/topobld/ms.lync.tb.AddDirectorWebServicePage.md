---
title: Hinzufügen von Director-Webdiensts
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
ms.openlocfilehash: 507e99d82ee4203bfcb0fd553ce6b2fdd65a6076
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979820"
---
# <a name="add-director-web-service"></a>Hinzufügen von Director-Webdiensts
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
  
Den internen Webdienste Pool vollqualifizierten Domänennamen (FQDN) kann nicht überschrieben werden, wenn nur einen einzelnen Director bereitgestellt wird. Wenn Sie eine Domain Name System (DNS) Lastenausgleich für den Pool von Directors konfigurieren, können Sie einen anderen internen Basis-URL angeben (der FQDN des Pools unterscheidet und konnte sein, beispielsweise internen -\<Basis-URL\>).
  
Sie können einen externen Basis-URL, die sich unterscheidet angeben von Ihrer internen Basis-URL um Domänennamen zu unterscheiden. Beispielsweise die interne Domäne ist contoso.net, aber der externen Domäne "contoso.com" lautet. Sie würden die externe base-URL mit den Domänennamen "contoso.com" definieren. Dies ist wichtig für Reverseproxyserver für eine edgebereitstellung. Der externe URL-Domäne Basisnamen sollte die den Domänennamen des vollqualifizierten Domänennamens des Reverseproxys identisch sein. 
  

