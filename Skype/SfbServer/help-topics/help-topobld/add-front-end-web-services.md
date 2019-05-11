---
title: Hinzufügen von Front-End-Webdiensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
ms.openlocfilehash: fc67ed792ab121bc4a9aaa0c72bcf764a2dadf1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897685"
---
# <a name="add-front-end-web-services"></a>Hinzufügen von Front-End-Webdiensten
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
  
Den internen Webdienste Pool vollqualifizierten Domänennamen (FQDN) für einen Standard Edition-Server kann nicht überschrieben werden. Wenn Sie Domain Name System (DNS) des Lastenausgleichs für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie angeben, dass einen anderen internen Basis-URL der FQDN des Pools unterscheidet sein muss (beispielsweise internen -\<Basis-URL\>).
  
Sie können einen externen Basis-URL, die sich unterscheidet angeben von Ihrer internen Basis-URL um Domänennamen zu unterscheiden. Beispielsweise die interne Domäne ist contoso.net, aber der externen Domäne "contoso.com" lautet. Definieren Sie die externe base-URL, die mit dem Domänennamen "contoso.com". Dies ist wichtig für Reverseproxyserver für eine edgebereitstellung. Der externe URL-Domäne Basisnamen sollte die den Domänennamen des vollqualifizierten Domänennamens des Reverseproxys identisch sein. Sofortnachrichten und Anwesenheit ist HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

