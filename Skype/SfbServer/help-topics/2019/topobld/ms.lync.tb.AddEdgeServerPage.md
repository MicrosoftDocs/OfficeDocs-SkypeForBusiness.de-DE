---
title: Hinzufügen eines Edgeservers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
ROBOTS: NOINDEX, NOFOLLOW
description: Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor der Veröffentlichung einer Topologie, die den Edgeserver oder Edgeserverpool umfasst, und der Installation von Skype for Business Server sollten Alle Voraussetzungen für die Bereitstellung des Externen Benutzerzugriffs erfüllt sein. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter Preparing for Installation of Servers in the Perimeter Network in der Bereitstellungsdokumentation.
ms.openlocfilehash: 7b0fedfe7468f2d1468c53835fc9873940d7eab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800915"
---
# <a name="add-edge-server"></a>Hinzufügen eines Edgeservers

Um einen Edgeserver oder Edgeserverpool in Ihren Topologieentwurf zu integrieren, müssen Sie den vollqualifizierten Domänennamen des Servers angeben, auf dem der Edgeserver oder Edgeserverpool bereitgestellt werden soll. Vor der Veröffentlichung einer Topologie, die den Edgeserver oder Edgeserverpool umfasst, und der Installation von Skype for Business Server sollten Alle Voraussetzungen für die Bereitstellung des Externen Benutzerzugriffs erfüllt sein. Ausführliche Informationen zu diesen Voraussetzungen finden Sie unter [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) in der Bereitstellungsdokumentation.

> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Sie müssen ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver oder Edgeserverpool bereitgestellt werden soll und nicht Mitglied einer Domäne ist.

> [!TIP]
> Wenn Sie die Implementierung eines Edgeserverpools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern**. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut zum Definieren des neuen Poolmitglieds, veröffentlichen Sie die neue Topologie und richten Sie dann das neue Edgeserverpoolmitglied über den Skype for Business Server-Bereitstellungs-Assistenten ein. Zudem müssen Sie das neue Poolmitglied zu den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen. Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver dem richtigen Lastenausgleich hinzufügen.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder nach der Bereitstellung hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern oder Edgeserverpools zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in der Edgeserver-Bereitstellungsdokumentation.


