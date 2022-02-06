---
title: Hinzufügen von Front-End-Webdiensten
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
  - ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 'Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .'
---

# <a name="add-front-end-web-services"></a>Hinzufügen von Front-End-Webdiensten
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet, lautet `https://pool01.contoso.net``pool01.contoso.net`die Basis-URL .
  
Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienstpools für einen Standard Edition Server nicht überschreiben. Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben, die sich vom Pool-FQDN unterscheiden muss (z. B. intern-\<your base URL\>).
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Ihre interne Domäne lautet `contoso.net`beispielsweise , aber Ihr externer Domänenname lautet `contoso.com`. Sie würden die externe Basis-URL mithilfe des Domänennamens `contoso.com` definieren. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Sofortnachrichten und Anwesenheitsinformationen ist ein HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

