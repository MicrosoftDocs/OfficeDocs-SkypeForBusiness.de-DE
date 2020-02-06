---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität steht nicht mehr zur Verfügung #a0 in Skype for Business Server 2019 veraltet. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, kann dies in der coexitence-Umgebung mit Legacy Version (Skype for Business Server 2015/lync Server 2013) genutzt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird.'
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813433"
---
# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität steht nicht mehr zur Verfügung und ist in Skype for Business Server 2019 veraltet. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können Sie dies in einer Koexistenz-Umgebung mit einer Legacy Version (Skype for Business Server 2015 oder lync Server 2013) tun. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird. 
  
Aus Migrations Sicht sollten Benutzer, die das XMPP-Feature in Anspruch nehmen möchten, auf dem Legacy Server verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, sondern weiterhin das Legacy-XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder lync Server 2013 konfiguriert ist. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, sollten Sie den Legacy Edge-Server nicht zu Skype for Business Server 2019 migrieren. Sie können jedoch die Koexistenz des Legacy-Edgeserver (mit XMPP-Proxy) und des Skype for Business 2019-Edgeserver aufweisen.
  

    

