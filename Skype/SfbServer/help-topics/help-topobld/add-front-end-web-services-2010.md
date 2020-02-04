---
title: Hinzufügen von Front-End-Webdiensten – 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685128"
---
# <a name="add-front-end-web-services-2010"></a>Hinzufügen von Front-End-Webdiensten – 2010
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
  
Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für einen Standard Edition-Server nicht außer Kraft setzen. Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und\<beispielsweise Internal\>-ihre Basis-URL sein kann).
  
Sie können eine externe Basis-URL angeben, die von ihrer internen Basis-URL abweicht, um die Domänenbenennung zu unterscheiden. Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com. Sie würden die externe Basis-URL mit dem contoso.com-Domänennamen definieren. Dies ist wichtig für Reverse-Proxy Server für eine Edge-Bereitstellung. Der Domänenname der externen Basis-URL sollte mit dem Domänennamen des FQDN des Reverse-Proxy identisch sein. Für Sofortnachrichten und Anwesenheitsinformationen ist HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

