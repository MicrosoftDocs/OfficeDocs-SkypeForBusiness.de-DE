---
title: Migrieren eines XMPP-Partnerverbunds
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität steht nicht mehr zur Verfügung #a0 in Skype for Business Server 2019 veraltet. Wenn Sie mit der XMPP-Funktionalität fortfahren möchten, kann dies in der coexitence-Umgebung mit Legacy Version (Skype for Business Server 2015/lync Server 2013) genutzt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird.'
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237793"
---
# <a name="migrating-xmpp-federation"></a>Migrieren eines XMPP-Partnerverbunds

In früheren Versionen wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Serverrolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. Die XMPP-Funktionalität steht nicht mehr zur Verfügung und ist in Skype for Business Server 2019 veraltet. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können Sie dies in einer Koexistenz-Umgebung mit einer Legacy Version (Skype for Business Server 2015 oder lync Server 2013) tun. Die XMPP-Funktionalität ist in zwei Teilen installiert: als XMPP-Proxy, der auf dem Legacy-Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf dem Legacy-Front-End-Server ausgeführt wird. 
  
Aus Migrations Sicht sollten Benutzer, die das XMPP-Feature in Anspruch nehmen möchten, auf dem Legacy Server verbleiben und nicht in einen Skype for Business Server 2019-Pool verschoben werden, sondern weiterhin das Legacy-XMPP-Gateway verwenden. Dies ist nur möglich, wenn der XMPP-Verbundpartner in Skype for Business Server 2015 oder lync Server 2013 konfiguriert ist. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, sollten Sie den Legacy Edge-Server nicht zu Skype for Business Server 2019 migrieren. Sie können jedoch die Koexistenz des Legacy-Edgeserver (mit XMPP-Proxy) und des Skype for Business 2019-Edgeserver aufweisen.
  

    

