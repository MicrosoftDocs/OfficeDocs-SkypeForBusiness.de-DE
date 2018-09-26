---
title: Migrieren von XMPP-Verbund
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'In früheren Versionen wurde ein extensible messaging und Anwesenheit Protocol (XMPP)-Gateways, die als eine separate Serverrolle zum Erstellen eines Verbunds mit XMPP-Bereitstellungen zulassen bereitgestellt werden konnte. Die XMPP-Funktionalität ist nicht mehr verfügbar und veraltete in Skype für Business Server 2019. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können werden er besitzt, unterstellt in Coexitence-Umgebung mit Legacyversion (Skype für Business Server 2015 / Lync Server 2013). XMPP-Funktionalität in zwei Teile installiert ist: als eine XMPP-Proxy, der auf die Legacy Edge-Server und des XMPP-Gateways, die ausgeführt wird ausgeführt wird, auf dem Front-End-Legacyserver.'
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029867"
---
# <a name="migrating-xmpp-federation"></a>Migrieren von XMPP-Verbund

In früheren Versionen wurde ein extensible messaging und Anwesenheit Protocol (XMPP)-Gateways, die als eine separate Serverrolle zum Erstellen eines Verbunds mit XMPP-Bereitstellungen zulassen bereitgestellt werden konnte. Die XMPP-Funktionalität ist nicht mehr verfügbar und ist in Skype für Business Server 2019 veraltet. Wenn Sie die XMPP-Funktionalität fortsetzen möchten, können in einer Umgebung mit einer älteren Version (Skype für Business Server 2015 oder Lync Server 2013) möchten. XMPP-Funktionalität in zwei Teile installiert ist: als eine XMPP-Proxy, der auf die Legacy Edge-Server und des XMPP-Gateways, die ausgeführt wird ausgeführt wird, auf dem Front-End-Legacyserver. 
  
Migration bestehen Benutzer, die die XMPP-Funktion nutzen möchten sollten verbleiben in der Legacyserver und sollte nicht in einer Skype für Business Server 2019 Pool verschoben werden jedoch weiterhin ältere XMPP-Gateway verwenden. Dies ist möglich, nur, wenn der XMPP-Verbundpartner in Skype für Business Server 2015 oder Lync Server 2013 konfiguriert ist. Sie sollten nicht Edgeserver der Vorversion zu Skype für Business Server 2019 migrieren, wenn Sie XMPP-Funktionalität fortsetzen möchten. Sie können jedoch Koexistenz von Edgeserver der Vorversion (mit XMPP-Proxy) und die Skype für Business 2019 Edge-Server haben.
  

    

