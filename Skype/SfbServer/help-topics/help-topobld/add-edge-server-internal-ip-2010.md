---
title: Hinzufügen der internen IP-Adresse des Edgeservers – 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) des Edgeservers angeben.
ms.openlocfilehash: 45a0d731ace90677ade72ddb6a37ae39b7d697c4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776405"
---
# <a name="add-edge-server-internal-ip-2010"></a>Hinzufügen der internen IP-Adresse des Edgeservers – 2010

Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) des Edgeservers angeben.

Der angegebene FQDN muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter [Configure DNS for Edge Support.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)