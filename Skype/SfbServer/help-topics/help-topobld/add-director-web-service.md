---
title: Hinzufügen eines Director-Webdiensts
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219466"
---
# <a name="add-director-web-service"></a>Hinzufügen eines Director-Webdiensts
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.
  
Wenn nur ein Director bereitgestellt wird, können Sie den vollqualifizierten Domänennamen (FQDN) des internen Webdienstepools nicht außer Kraft setzen. Wenn Sie einen Domain Name System (DNS) Lastenausgleich für Pool of Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und beispielsweise Internal sein kann \<your base URL\> ).
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com". Zur Definition der externen Basis-URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. 
  

