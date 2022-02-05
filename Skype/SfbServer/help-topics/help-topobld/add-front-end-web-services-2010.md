---
title: Hinzufügen von Front-End-Webdiensten – 2010
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 'Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .'
---

# <a name="add-front-end-web-services-2010"></a>Hinzufügen von Front-End-Webdiensten – 2010
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .
  
Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienstpools für einen Standard Edition Server nicht außer Kraft setzen. Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom Pool-FQDN unterscheiden muss und z. B. intern sein\<your base URL\> kann).
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Ihre interne Domäne lautet `contoso.net`beispielsweise , aber Ihr externer Domänenname lautet `contoso.com`. Zur Definition der externen Basis-URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Sofortnachrichten und Anwesenheitsinformationen ist ein HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

