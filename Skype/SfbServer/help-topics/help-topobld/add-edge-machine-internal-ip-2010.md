---
title: Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Edgeserver angeben.
ms.openlocfilehash: 53b4a3d7d7347a151cc34195236f50d492206825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304716"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010

Auf dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Edgeserver angeben.

- Geben Sie unter **interne IPv4-Adresse**die IP-Adresse des Edge-Servers ein, der dem Pool hinzugefügt werden soll.

- Geben Sie im **internen FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers ein, den Sie dem Pool hinzufügen möchten.

Der von Ihnen angegebene FQDN muss mit dem Computernamen identisch sein, der auf dem Server konfiguriert ist. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein DNS-Suffix (Domain Name System) für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll, der nicht zu einer Domäne gehört. Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter [Konfigurieren von DNS für Edge-Unterstützung](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx) .


