---
title: Hinzufügen von Edgeservern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor dem Veröffentlichen einer Topologie, die den Edge-Server oder den Edge-Serverpool umfasst, und die Installation von Skype for Business Server sollten Sie alle Voraussetzungen für die Bereitstellung des Zugriffs auf externe Benutzer erfüllt haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie in der Bereitstellungsdokumentation unter Preparing for Installation of Servers in the Perimeter Network.
ms.openlocfilehash: db38c01b87c0595f9157da93c91ec24de256029b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302810"
---
# <a name="add-edge-server"></a>Hinzufügen von Edgeservern

Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor dem Veröffentlichen einer Topologie, die den Edge-Server oder den Edge-Serverpool umfasst, und die Installation von Skype for Business Server sollten Sie alle Voraussetzungen für die Bereitstellung des Zugriffs auf externe Benutzer erfüllt haben. Ausführliche Informationen zu diesen Voraussetzungen finden Sie in der Bereitstellungsdokumentation unter [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx).

> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Sie müssen ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver oder Edgeserverpool bereitgestellt werden soll und nicht Mitglied einer Domäne ist.

> [!TIP]
> Wenn Sie die Implementierung eines Edgeserverpools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern**. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut definieren, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Edge-Serverpool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. Zudem müssen Sie das neue Poolmitglied zu den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver dem richtigen Lastenausgleich hinzufügen.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder nach der Bereitstellung hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern oder Edgeserverpools zu einer vorhandenen Topologie finden Sie in der Edgeserver-Bereitstellungsdokumentation unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


