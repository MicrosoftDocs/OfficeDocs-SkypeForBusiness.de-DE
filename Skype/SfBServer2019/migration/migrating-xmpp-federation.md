---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität ist nicht mehr verfügbar & veraltet in Skype for Business Server 2019. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, können Sie diese in der coexitence-Umgebung mit der Vorgängerversion (Skype for Business Server 2015/lync Server 2013) nutzen. Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy Front-End-Server ausgeführt wird.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752647"
---
# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität ist nicht mehr verfügbar und ist in Skype for Business Server 2019 veraltet. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, können Sie dies in einer Koexistenz-Umgebung mit einer älteren Version (Skype for Business Server 2015 oder lync Server 2013) tun. Die XMPP-Funktionalität wird in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy Front-End-Server ausgeführt wird. 
  
Aus Migrations Sicht sollten Benutzer, die das XMPP-Feature in Anspruch nehmen möchten, auf dem vorversions Server verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, aber weiterhin das Legacy-XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder lync Server 2013 konfiguriert ist. Sie sollten die Legacy Edgeserver nicht auf Skype for Business Server 2019 migrieren, wenn Sie mit der XMPP-Funktionalität fortfahren möchten. Sie können jedoch eine Koexistenz der Legacy Edgeserver (mit XMPP-Proxy) und der Skype for Business 2019 Edgeserver haben.
  

    

