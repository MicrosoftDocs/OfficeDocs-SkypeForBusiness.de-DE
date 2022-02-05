---
title: Hinzufügen eines Director-Webdiensts
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .'
---

# <a name="add-director-web-service"></a>Hinzufügen eines Director-Webdiensts
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .
  
Wenn nur ein Director bereitgestellt wird, können Sie den vollqualifizierten Domänennamen (FQDN) des internen Webdienstepools nicht außer Kraft setzen. Wenn Sie einen DNS-Lastenausgleich (Domain Name System) für einen Pool von Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom Pool-FQDN unterscheiden muss und z. B. intern sein\<your base URL\> kann).
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Ihre interne Domäne lautet `contoso.net`beispielsweise , aber Ihr externer Domänenname lautet `contoso.com`. Sie würden die externe Basis-URL mithilfe der `contoso.com domain name`definieren. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. 
  

