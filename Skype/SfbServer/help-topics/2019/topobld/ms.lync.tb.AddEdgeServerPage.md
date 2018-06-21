---
title: Hinzufügen von Edgeservern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor dem Veröffentlichen einer Topologie, die der Edge-Server oder Pool für Edge-Server enthält, und Skype für Business Server installieren, sollten Sie alle erforderlichen Komponenten für die Bereitstellung von Zugriff durch externe Benutzer abgeschlossen haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter Vorbereiten der Installation von Servern im Umkreisnetzwerk in der Bereitstellungsdokumentation.
ms.openlocfilehash: d5021404bc9e8445433f1acdae2c022045f45628
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987368"
---
# <a name="add-edge-server"></a>Hinzufügen von Edgeservern
 
Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor dem Veröffentlichen einer Topologie, die der Edge-Server oder Pool für Edge-Server enthält, und Skype für Business Server installieren, sollten Sie alle erforderlichen Komponenten für die Bereitstellung von Zugriff durch externe Benutzer abgeschlossen haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter [Preparing for Installation of Servers in das Umkreisnetzwerk](http://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in der Bereitstellungsdokumentation.
  
> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Sie müssen ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver oder Edgeserverpool bereitgestellt werden soll und nicht Mitglied einer Domäne ist. 
  
> [!TIP]
> Wenn Sie die Implementierung eines Edgeserverpools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern**. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie die Topologie-Generator erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und dann das neue Mitglied der Edge-Server-Pool über die Skype für Business Server-Bereitstellungsassistenten einrichten. Zudem müssen Sie das neue Poolmitglied zu den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver dem richtigen Lastenausgleich hinzufügen. 
  
Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder nach der Bereitstellung hinzufügen. Ausführliche Informationen zum Hinzufügen von Edge-Server oder Pool auf eine vorhandene Topologie Edge-Server finden Sie unter [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in der Dokumentation zur Bereitstellung der Edge-Server.
  

