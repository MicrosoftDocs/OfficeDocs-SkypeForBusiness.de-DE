---
title: Hinzufügen eines Edgeservers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Bevor Sie eine Topologie veröffentlichen, die den Edgeserver oder Edgeserverpool enthält, und Skype for Business Server installieren, sollten Sie alle Voraussetzungen für die Bereitstellung des Externen Benutzerzugriffs erfüllt haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter Preparing for Installation of Servers in the Perimeter Network in der Bereitstellungsdokumentation.
ms.openlocfilehash: 6f905b24a0ca0da499cf94acda57404fabe289bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592661"
---
# <a name="add-edge-server"></a>Hinzufügen eines Edgeservers

Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Bevor Sie eine Topologie veröffentlichen, die den Edgeserver oder Edgeserverpool enthält, und Skype for Business Server installieren, sollten Sie alle Voraussetzungen für die Bereitstellung des Externen Benutzerzugriffs erfüllt haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) in der Bereitstellungsdokumentation.

> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Sie müssen ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver oder Edgeserverpool bereitgestellt werden soll und nicht Mitglied einer Domäne ist.

> [!TIP]
> Wenn Sie die Implementierung eines Edgeserverpools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern**. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut erstellen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue Edgeserverpoolmitglied über den Skype for Business Server Bereitstellungs-Assistenten einzurichten. Zudem müssen Sie das neue Poolmitglied zu den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver dem richtigen Lastenausgleich hinzufügen.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder nach der Bereitstellung hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern oder Edgeserverpools zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in der Edgeserver-Bereitstellungsdokumentation.