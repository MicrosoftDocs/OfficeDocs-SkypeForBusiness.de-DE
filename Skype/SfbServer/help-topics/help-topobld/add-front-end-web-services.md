---
title: Hinzufügen von Front-End-Webdiensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 6e5f9211f35f4e58621deb0a714df8587675f26c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820787"
---
# <a name="add-front-end-web-services"></a>Hinzufügen von Front-End-Webdiensten
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
  
Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für einen Standard Edition-Server nicht außer Kraft setzen. Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben, die sich vom FQDN des Pools unter\<scheiden soll (\>beispielsweise Internal-ihre Basis-URL).
  
Sie können eine externe Basis-URL angeben, die von ihrer internen Basis-URL abweicht, um die Domänenbenennung zu unterscheiden. Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com. Sie würden die externe Basis-URL mit dem contoso.com-Domänennamen definieren. Dies ist wichtig für Reverse-Proxy Server für eine Edge-Bereitstellung. Der Domänenname der externen Basis-URL sollte mit dem Domänennamen des FQDN des Reverse-Proxy identisch sein. Für Sofortnachrichten und Anwesenheitsinformationen ist HTTP-Zugriff auf den Front-End-Pool erforderlich.
  

