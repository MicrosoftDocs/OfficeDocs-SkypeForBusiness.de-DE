---
title: Hinzufügen von Front-End-Webdiensten
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools https://pool01.contoso.net lautet, ist die Basis-URL pool01.contoso.net.
ms.openlocfilehash: b82cc8383efc32a92b46b798503a7780df82aad8c235c3d75561f895e13cdc02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314491"
---
# <a name="add-front-end-web-services"></a>Hinzufügen von Front-End-Webdiensten
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools https://pool01.contoso.net lautet, ist die Basis-URL pool01.contoso.net.
  
Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienstpools für einen Standard Edition Server nicht überschreiben. Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben, die sich vom Pool-FQDN unterscheiden muss (z. B. intern- \<your base URL\> ).
  
Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com". Zur Definition der externen Basis-URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Sofortnachrichten und Anwesenheitsinformationen ist ein HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

