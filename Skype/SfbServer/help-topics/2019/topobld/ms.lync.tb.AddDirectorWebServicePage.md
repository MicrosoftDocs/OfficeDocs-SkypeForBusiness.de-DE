---
title: Hinzufügen eines Director-Webdiensts
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ROBOTS: NOINDEX, NOFOLLOW
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools `https://pool01.contoso.net` lautet, lautet die Basis-URL `pool01.contoso.net` .
ms.openlocfilehash: f1c41deebe928119c47c3a7acba3a91a1936af61
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742451"
---
# <a name="add-director-web-service"></a>Hinzufügen eines Director-Webdiensts
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools `https://pool01.contoso.net` lautet, lautet die Basis-URL `pool01.contoso.net` .
  
Wenn nur ein Director bereitgestellt wird, können Sie den vollqualifizierten Domänennamen (FQDN) des internen Webdienstepools nicht außer Kraft setzen. Wenn Sie einen DNS-Lastenausgleich (Domain Name System) für einen Pool von Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom Pool-FQDN unterscheiden muss und z. B. intern sein kann. \<your base URL\>
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Ihre interne Domäne lautet beispielsweise `contoso.net` , aber Ihr externer Domänenname lautet `contoso.com` . Sie würden die externe Basis-URL mithilfe der `contoso.com domain name` definieren. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. 
  

