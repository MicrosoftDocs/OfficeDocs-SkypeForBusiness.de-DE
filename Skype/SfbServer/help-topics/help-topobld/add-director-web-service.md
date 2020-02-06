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
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 0cdec8e371d7803bdcac781209b0fd9e55cb82be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821177"
---
# <a name="add-director-web-service"></a>Hinzufügen eines Director-Webdiensts
 
Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
  
Wenn Sie nur einen einzigen Director bereitstellen, können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienste-Pools nicht überschreiben. Wenn Sie einen DNS-Lastenausgleich (Domain Name System) für den Pool von Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und beispielsweise Internal-\<ihre Basis-\>URL sein kann).
  
Sie können eine externe Basis-URL angeben, die von ihrer internen Basis-URL abweicht, um die Domänenbenennung zu unterscheiden. Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com. Sie würden die externe Basis-URL mit dem contoso.com-Domänennamen definieren. Dies ist wichtig für Reverse-Proxy Server für eine Edge-Bereitstellung. Der Domänenname der externen Basis-URL sollte mit dem Domänennamen des FQDN des Reverse-Proxy identisch sein. 
  

