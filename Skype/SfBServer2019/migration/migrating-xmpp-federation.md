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
description: 'In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden konnte, um partnerverbundene XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität ist & in Skype for Business Server 2019 nicht mehr verfügbar. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, kann dies in der Coexitence-Umgebung mit der Legacyversion (Skype for Business Server 2015/ Lync Server 2013) verwendet werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem älteren Edgeserver ausgeführt wird, und als XMPP-Gateway, das auf dem älteren Front-End-Server ausgeführt wird.'
ms.openlocfilehash: f1dc49a9f93d87bf2b253963cf0955594b337f9bd186c3034ac7780cb50ccddb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303429"
---
# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

In früheren Versionen wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Serverrolle bereitgestellt werden konnte, um partnerverbundene XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität ist nicht mehr verfügbar und in Skype for Business Server 2019 veraltet. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, können Sie dies in einer Koexistenzumgebung mit einer älteren Version (Skype for Business Server 2015 oder Lync Server 2013) tun. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem älteren Edgeserver ausgeführt wird, und als XMPP-Gateway, das auf dem älteren Front-End-Server ausgeführt wird. 
  
Aus Migrationsperspektive sollten Benutzer, die das XMPP-Feature nutzen möchten, auf dem Legacyserver verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, sondern weiterhin das ältere XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder Lync Server 2013 konfiguriert ist. Sie sollten den älteren Edgeserver nicht zu Skype for Business Server 2019 migrieren, wenn Sie mit der XMPP-Funktionalität fortfahren möchten. Sie können jedoch eine Koexistenz des älteren Edgeservers (mit XMPP-Proxy) und des Skype for Business 2019-Edgeservers haben.
  

    

